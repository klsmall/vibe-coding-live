# Sales Call Note Builder Prototype

## Goal

Create a simple Salesforce Lightning Web Component prototype that helps a sales representative prepare for and take notes during an early-stage sales call.

The prototype should be suitable for an Opportunity Lightning record page.

## Component Name

- Component name: Sales Call Note Builder Prototype
- Component bundle name: salesCallNoteBuilderPrototype
- Location: Opportunity Lightning record page
- Supported devices: Desktop and phone

## Build Process

This prototype will be created using Plan mode. The implementation plan should follow these steps in order.

### Step 1: Add the Required Custom Field

Before building the component, check whether the required Opportunity field exists in the Salesforce project. If it does not exist, create it first with these details:

- Object: Opportunity
- Field label: Sales Call Responses JSON
- Field name: `Sales_Call_Responses_JSON__c`
- Field type: Long Text Area
- Maximum length: 131,072 characters
- Visible lines: 10
- Purpose: Store the complete sales-call note as JSON

This is the only custom field required for the prototype. Do not create a separate Salesforce field for each question or answer.

### Step 2: Build the Prototype Component

After the custom field is available, build the Sales Call Note Builder Prototype using the requirements below.

## Implementation Style

Build this prototype using a simple, modern Lightning Web Component pattern:

- Use Lightning Data Service and standard LWC utilities such as `getRecord`, `getFieldValue`, and `updateRecord`.
- Keep component state minimal, explicit, and easy to follow.
- Safely initialize every value used by the template.
- Normalize loaded JSON before displaying it.
- Treat a blank saved-note field as a normal first-use case, not an error.
- Use modern `lwc:if`, `lwc:elseif`, and `lwc:else` conditional rendering.
- Prefer direct, standard field access with `getFieldValue` instead of custom field-access helper logic.
- Avoid custom abstractions unless they are clearly necessary.
- Avoid deeply nested reactive state, fragile state coupling, or clever rendering shortcuts.
- Optimize for clarity and reliability over flexibility.
- Keep the JavaScript understandable for beginner and intermediate Salesforce developers.
- Do not use Apex for this prototype.

## Loading Salesforce Data

Use Lightning Data Service to load the Opportunity, its related Account details, and the saved JSON field.

Use Salesforce schema references for fields instead of entering field API names as unverified text in the JavaScript.

Use `updateRecord` to save the JSON back to the Opportunity.

Use `ShowToastEvent` for standard Salesforce success and error messages.

The component should not depend on a particular Opportunity stage.

## Technical Implementation Guardrails

Use a small, explicit state model:

- `isLoading` represents the initial Salesforce record load.
- `loadError` represents a Salesforce record-loading failure.
- The note mode is exactly one of edit, view, or invalid JSON after loading completes.
- `isSaving` represents a save or update in progress while the component remains in edit mode.

Loading and load-error states must prevent note content from rendering. Do not render view-mode content until the record has loaded and saved data has been parsed and normalized.

Do not switch from edit mode to view mode until a save succeeds. A failed save must leave the user in edit mode with their current answers still visible.

Initialize text values as empty text, question and section collections as empty collections, and loading or saving values as false unless the action is active. The template should never read properties from null or undefined values.

Do not assume Salesforce data will be available when the component first appears. The component should remain stable while data is loading or being refreshed.

Prevent repeated save requests while a save or update is already in progress.

## Safe JSON Handling

When the component loads a saved note:

- Treat a blank field as a new note and open edit mode.
- Show the invalid-JSON warning only when parsing or validating nonblank saved JSON actually fails.
- Parse saved JSON safely without allowing an error to crash the component.
- Confirm that sections and questions are usable collections before rendering them.
- Convert missing Prep Notes, questions, and answers into safe empty values.
- Preserve the version, section names, question text, answers, and saved timestamp.
- Show a friendly recovery option if the saved JSON cannot be read.

When a user edits an existing note, rebuild the editable form from the prototype's current hard-coded questions. Restore saved answers by question key first and use exact question text as a fallback match.

Starting a new note after invalid JSON should update only local component state until the user chooses to save.

## JSON Storage Contract

Store a simple, versioned JSON document in `Opportunity.Sales_Call_Responses_JSON__c`.

The saved document must contain:

- `version`: The numeric value 1 for this prototype.
- `prepNotes`: The Prep Notes text, including an empty value when nothing was entered.
- `sections`: A collection containing all four note sections in their displayed order.
- `lastSavedAt`: The date and time of the save in ISO format.

Each saved section must contain:

- A stable section key.
- The exact section label shown to the user.
- A collection of its questions.

Use these section keys:

- `businessContext`
- `currentChallenges`
- `desiredOutcomes`
- `nextSteps`

Each saved question must contain:

- A predictable key made from the section key and question position.
- The exact question text displayed to the user.
- The answer, including an empty value when no answer was entered.

When saving an edit, regenerate the complete JSON document from current component state, update `lastSavedAt`, and replace the previous field value.

Before calling Salesforce, confirm that the serialized note fits within the custom field's 131,072-character limit. If it does not fit, keep the user in edit mode and show a clear error message.

## Opportunity and Account Summary

Show a compact summary at the top of the prototype so the sales representative has useful context during the call.

Include these Opportunity details when available:

- Opportunity Name
- Stage
- Type
- Lead Source
- Amount
- Close Date
- Probability
- Next Step

Include these related Account details when available:

- Account Name
- Industry
- Website
- Phone

Hide information that is blank. Do not display null or undefined values. Make the Account website clickable.

Use standard Salesforce display components to format dates, numbers, percentages, websites, and phone numbers.

## Prep Notes

Include a Prep Notes area where the sales representative can enter research, background information, referral context, or goals for the conversation.

## Sales Call Questions

For this prototype, place the following questions directly in the component. The questions do not need to be configurable.

### Business Context

- What is the business hoping to accomplish?
- Why is this a priority right now?
- Who is most affected by the current process?

### Current Challenges

- How does the current process work today?
- Where does the team experience the most difficulty?
- What is the impact of these challenges on the business?

### Desired Outcomes

- What would a successful outcome look like?
- Which capabilities are most important to the team?
- How will the business measure success?

### Next Steps

- Who else should be involved in the evaluation?
- What follow-up actions should happen after this call?
- What timing is the customer working toward?

Display every question as a standard Salesforce text area. No answer should be required.

## Saving the Note

Use the `Sales_Call_Responses_JSON__c` Opportunity field created in the first step.

Save the following information together as JSON in that field:

- A version number
- Prep Notes
- The four section names
- Every question
- Every answer
- The date and time the note was saved

Allow partially completed notes to be saved. When an edited note is saved, replace the previous JSON with the updated note.

## View and Edit Experience

When no saved note exists, open the prototype in edit mode.

After a note is saved, display it in an easy-to-read view mode. Include an Edit Note button that returns to the form and restores the saved Prep Notes and answers.

Keep the Account and Opportunity summary available in both modes.

## Out-of-the-Box Salesforce UX

Use out-of-the-box Lightning base components before considering custom HTML or custom controls.

Use standard Salesforce components for:

- The main card
- Responsive layout
- Text areas
- Buttons
- Icons
- Formatted values
- Loading spinners
- Success and error messages

Use SLDS utilities for spacing, layout, alignment, and text styles. Verify that every SLDS utility, icon, or styling hook exists before using it.

Use custom CSS only when a Lightning base component or SLDS utility cannot meet the need. Do not override SLDS classes. Do not hard-code colors, spacing, or typography. If custom styling is necessary, use verified SLDS styling hooks and component-specific class names.

Keep the layout clean and responsive. It should remain readable in wide and narrow record-page regions and on phone screens.

## Loading and Saving Feedback

Use an out-of-the-box Lightning spinner whenever:

- The Opportunity and saved note are loading.
- A new note is being saved.
- An existing note is being updated.

Give every spinner clear alternative text that explains the active operation.

While saving or updating:

- Disable the Save Note button.
- Prevent duplicate save requests.
- Keep the current answers visible.
- Do not switch to view mode until the save succeeds.

After a successful save, show a standard Salesforce success message and switch to view mode.

If loading or saving fails, show a friendly standard Salesforce error message and leave the user in a state where they can recover or try again.

## Error Handling and Workshop Troubleshooting

Do not silently ignore errors. Handle record-loading, JSON parsing, JSON normalization, and record-saving failures separately so the source of a workshop issue is easy to identify.

For every caught error:

- Log a clear operation-specific message with `console.error`.
- Include the Salesforce or JavaScript error object when it is available.
- Use a consistent component prefix in console messages so workshop attendees can find them quickly.
- Never log Prep Notes, answers, serialized JSON, or unrelated Opportunity and Account data.

Use friendly user-facing behavior for each failure type:

- Record load failure: Show an inline error state and log the technical error to the console.
- Invalid saved JSON: Show the recovery warning only for nonblank JSON that cannot be parsed or normalized, and log the parsing error to the console.
- Save or update failure: Show an error toast, log the technical error, keep the form and answers visible, stop the spinner, and re-enable the Save Note button.
- Save success: Show a success toast, stop the spinner, and then switch to view mode.

Use a small, understandable error-message helper to handle common Lightning Data Service error shapes and produce a useful toast message. If Salesforce does not provide a readable message, use a friendly fallback message.

Always clear saving state after a save attempt, whether the operation succeeds or fails. A failure must not leave the prototype stuck behind a spinner or disabled button.

## Basic Accessibility

- Give every field a clear visible label.
- Give every meaningful icon accessible alternative text.
- Do not use color as the only way to communicate status.
- Preserve normal keyboard navigation and focus behavior.
- Use headings in a logical order.
- Keep status and error messages understandable without technical language.

## Prototype Completion Checklist

The prototype is complete when:

- The required Opportunity custom field is included first.
- The component can be added only to an Opportunity Lightning record page.
- It shows available Opportunity and Account context without blank values.
- It always displays the four sections and the hard-coded questions listed above.
- A user can enter Prep Notes and answers.
- A partially completed note can be saved as JSON on the Opportunity.
- A saved note opens in view mode.
- A user can edit and save an existing note.
- Blank saved-note data opens as a new note without an error.
- Loaded JSON is normalized before it is rendered.
- Invalid saved JSON can be handled safely.
- The invalid-JSON warning appears only when nonblank JSON cannot be parsed or normalized.
- Saved JSON follows the defined versioned structure and remains within the field limit.
- Out-of-the-box Lightning components and SLDS are used wherever possible.
- A spinner is shown during loading, saving, and updating.
- Save controls are disabled while a save is active.
- Loading, saving, success, and error states are clear.
- Successful saves show a standard Salesforce success toast.
- Save failures show an error toast without losing the user's answers.
- Load, parse, normalization, and save failures are logged to the browser console with useful context.
- Console logs do not expose note contents or other record data.
- No error leaves the component stuck in a loading or saving state.
- Custom CSS is minimal and does not override SLDS.
- The implementation remains simple enough to explain during a workshop.

## Quality Check

Before considering the prototype complete:

- Review the component for modern LWC patterns and clear state handling.
- Check JavaScript formatting and common LWC code-quality issues.
- Validate SLDS usage and resolve all SLDS linter violations.
- Confirm that no unverified SLDS classes, icons, or styling hooks were introduced.
- Verify the blank-note, valid-note, invalid-JSON, record-load-error, save-success, and save-error paths.
- Confirm that spinners and disabled controls are always reset after errors.
- Confirm that browser console messages identify the failed operation without exposing note data.
- Confirm that no Apex, extra custom fields, or unnecessary abstractions were added.
