# Create Agentforce Vibes IDE Playground

We are using a special Agentforce Vibes IDE Playground because Agentforce Vibes is not available in every Trailhead Playground. This custom playground provides a compatible, preconfigured Salesforce environment with access to the browser-based IDE and the development tools needed for the workshop. Using the designated playground also helps ensure that everyone starts with a consistent environment.

1. Create a new **Agentforce Vibes IDE Playground** using the following link: [https://trailhead.salesforce.com/content/learn/projects/quick-start-troubleshoot-code-with-dev-agent/create-your-local-development-environment](https://trailhead.salesforce.com/content/learn/projects/quick-start-troubleshoot-code-with-dev-agent/create-your-local-development-environment)

   **NOTE:** Wait until the playground has finished being created before continuing.

> **Image placeholder:** Agentforce Vibes IDE Playground project page.

> **Image placeholder:** Trailhead screen for creating the Agentforce Vibes IDE Playground.

2. Once your Agentforce Vibes IDE Playground is created, launch the Playground using the **Launch** button

> **Image placeholder:** Completed playground showing the **Launch** button.

# Launch Agentforce Vibes

Agentforce Vibes is an AI-powered Salesforce development assistant available in Visual Studio Code and the web-based Agentforce Vibes IDE. It can help generate code from natural-language prompts, suggest code as you work, create unit tests, explain existing logic, and assist with documentation and troubleshooting.

1. Click on the Gear icon to open the Setup Menu, then select the **Agentforce Vibes** option

> **Image placeholder:** Salesforce Setup menu with **Agentforce Vibes** selected.

2. If prompted, **accept** the Agentforce Vibes Terms & Conditions

> **Image placeholder:** Agentforce Vibes Terms & Conditions prompt.

3. When prompted to trust the author of files in the folder, click on the **“Yes, I trust the authors”** button. This step is *REQUIRED* before you can start vibe coding. 

> **Image placeholder:** Workspace trust prompt showing the **Yes, I trust the authors** button.

4. Now, you should be able to access the Agentforce Vibes side panel\! Check the **“I agree to the terms”** checkbox, then click on the **“Enable Agentforce”** button.

> **Image placeholder:** Agentforce Vibes side panel with the terms checkbox and **Enable Agentforce** button.

# Vibe Code the Sales Note Builder LWC and a Custom Field

1. Perform the following steps:
   1. Use the **File icon** to upload the markdown file for this workshop: [sales_call_note_builder_prototype_requirements.md](./markdown_files/sales_call_note_builder_prototype_requirements.md)
   2. Paste in [**Prompt #1**](./prompts/prompt_1.txt)
   3. Enable **Plan Mode**

> **Image placeholder:** Agentforce Vibes chat showing the uploaded requirements file, Prompt 1, and Plan Mode enabled.

2. Click on the **blue arrow** to start the chat with Agentforce Vibes

> **Image placeholder:** Agentforce Vibes chat showing the blue send arrow.

3. Agentforce Vibes will generate an Implementation Plan that you should review before moving forward. You may want to resize the panel to get a better view of the plan.

> **Image placeholder:** Generated implementation plan in the Agentforce Vibes panel.

4. Once you have reviewed the entire plan, scroll down to the bottom of the plan, and click on the **Approve Plan** button

> **Image placeholder:** Bottom of the implementation plan showing the **Approve Plan** button.

5. Agentforce Vibes will begin implementing the plan, but will ask for approval before running any commands / search. Carefully review what Agentforce Vibes wants to do before approving.

   **IMPORTANT:** In real projects, do not blindly approve commands or searches, and do not enable features that automatically approve them for you. Automatic approval removes an important safety checkpoint and could result in unintended changes, deleted files or metadata, exposure of sensitive information, or destructive commands being executed in your environment.

> **Image placeholder:** Agentforce Vibes command approval prompt.

6. Agentforce Vibes will finish implementing the plan, and new files for both the new custom field and the LWC should be created. You will be able to review and approve each file related to the project.

> **Image placeholder:** Generated custom-field and Lightning Web Component files ready for review.

# Permission Set & Deployment

7. Next, send [**Prompt #2**](./prompts/prompt_2.txt) to create a permission set for the new field, deploy the metadata, and assign that new permission set to yourself (this does not have to run in plan mode)

> **Image placeholder:** Agentforce Vibes chat with Prompt 2 entered.

8. Agentforce Vibes may ask for approval before running anything else. Review the requested changes, type out your approval in the chat window, then send the message.

> **Image placeholder:** Agentforce Vibes requesting typed approval to continue.

9. A dry-run of the deployment process will begin. During the dry-run, Agentforce Vibes will check and try to resolve any deployment errors that occur. Each time a deployment issue is resolved, you may have to approve to rerun the deployment.

> **Image placeholder:** Targeted deployment dry-run progress and results.

10. Once all deployment errors are resolved, you can run the full deployment.

> **Image placeholder:** Successful dry run followed by the full deployment step.

11. Once the deployment succeeds, you be able to run the permission set assignment right within the chat

> **Image placeholder:** Permission-set assignment command and result in the chat.

12. Once Agentforce Vibes is done, you will be able to review a summary of the work completed

> **Image placeholder:** Agentforce Vibes summary of completed work.

# Deployment Verification and LWC Testing

13. In a different browser tab, navigate to Setup and verify that you have been assigned to the new permission set. You can also verify that access to the new “Sales Call Responses JSON” field has been granted through the permission set.

> **Image placeholder:** Salesforce permission-set assignment verification page.

> **Image placeholder:** Permission set showing access to the Sales Call Responses JSON field.

14. Navigate to a random Opportunity record in your org, then select the option to **Edit Page**

> **Image placeholder:** Opportunity record menu showing the **Edit Page** option.

15. Search for the “Sales Call Note Builder Prototype” LWC. Try adding the new component to the page.

> **Image placeholder:** Lightning App Builder search results showing the Sales Call Note Builder Prototype component.

**NOTE:** If there are any errors during this stage, take a screenshot of the error, navigate back to Agentforce Vibes, and ask it to resolve the error for you. Once the error is resolved and the fix is deployed, refresh the page with the error, then try adding the component to the Opportunity Lightning Page again.

> **Image placeholder:** Example component error to capture and troubleshoot in Agentforce Vibes.

16. Test out your brand new LWC on the Opportunity record page\!

> **Image placeholder:** Completed Sales Call Note Builder Prototype on an Opportunity record page.

# Troubleshooting

You may be prompted to download the recommended Salesforce extensions. If so, please click on the **Install** button to begin the installation. Once the extensions are installed, you should be able to access Agentforce Vibes.

> **Image placeholder:** Recommended Salesforce extensions prompt showing the **Install** button.

If you run into any network errors, try refreshing the page, then try running the prompt again

> **Image placeholder:** Example network error in Agentforce Vibes.

If you run into component errors, try switching the model

> **Image placeholder:** Model selector used when troubleshooting component errors.

Also, if there are too many errors, try asking Agentforce Vibes to completely rebuild the component using a “simpler modern implementation”  
