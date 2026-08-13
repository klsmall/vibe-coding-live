# Create Agentforce Vibes IDE Playground

We are using a special Agentforce Vibes IDE Playground because Agentforce Vibes is not available in every Trailhead Playground. This custom playground provides a compatible, preconfigured Salesforce environment with access to the browser-based IDE and the development tools needed for the workshop. Using the designated playground also helps ensure that everyone starts with a consistent environment.

1. Create a new **Agentforce Vibes IDE Playground** using the following link: [https://trailhead.salesforce.com/content/learn/projects/quick-start-troubleshoot-code-with-dev-agent/create-your-local-development-environment](https://trailhead.salesforce.com/content/learn/projects/quick-start-troubleshoot-code-with-dev-agent/create-your-local-development-environment)

   **NOTE:** Wait until the playground has finished being created before continuing.

<img width="1305" height="250" alt="Screenshot 2026-08-13 at 4 20 52 PM" src="https://github.com/user-attachments/assets/d78d3768-cf3a-4930-8c62-51244c6c71fe" />

<img width="1306" height="526" alt="Screenshot 2026-08-13 at 4 21 54 PM" src="https://github.com/user-attachments/assets/c2fa6289-7d91-43c9-9afa-2a47d8481061" />

2. Once your Agentforce Vibes IDE Playground is created, launch the Playground using the **Launch** button

<img width="1306" height="261" alt="Screenshot 2026-08-13 at 4 22 15 PM" src="https://github.com/user-attachments/assets/5006a1b5-0cb6-4543-8b68-76f95f39ceb0" />

# Launch Agentforce Vibes

Agentforce Vibes is an AI-powered Salesforce development assistant available in Visual Studio Code and the web-based Agentforce Vibes IDE. It can help generate code from natural-language prompts, suggest code as you work, create unit tests, explain existing logic, and assist with documentation and troubleshooting.

1. Click on the Gear icon to open the Setup Menu, then select the **Agentforce Vibes** option

<img width="1306" height="301" alt="Screenshot 2026-08-13 at 4 23 14 PM" src="https://github.com/user-attachments/assets/808c360a-fb82-4163-ac8f-0d952f90d7e0" />

2. If prompted, **accept** the Agentforce Vibes Terms & Conditions

<img width="1102" height="638" alt="Screenshot 2026-08-13 at 4 23 43 PM" src="https://github.com/user-attachments/assets/c31f05fb-fa6e-49b0-81ef-545cc777c201" />

3. When prompted to trust the author of files in the folder, click on the **“Yes, I trust the authors”** button. This step is *REQUIRED* before you can start vibe coding. 

<img width="1114" height="675" alt="Screenshot 2026-08-13 at 4 24 08 PM" src="https://github.com/user-attachments/assets/2f899665-93a3-43d6-ae28-7381aa68d018" />

4. Now, you should be able to access the Agentforce Vibes side panel\! Check the **“I agree to the terms”** checkbox, then click on the **“Enable Agentforce”** button.

<img width="1224" height="651" alt="Screenshot 2026-08-13 at 4 24 40 PM" src="https://github.com/user-attachments/assets/7b284a38-e359-4a26-9627-09ae2d6f361b" />

# Vibe Code the Sales Note Builder LWC and a Custom Field

1. Perform the following steps:
   1. Use the **File icon** to upload the markdown file for this workshop: [sales_call_note_builder_prototype_requirements.md](./markdown_files/sales_call_note_builder_prototype_requirements.md)
   2. Paste in [**Prompt #1**](./prompts/prompt_1.txt)
   3. Enable **Plan Mode**

<img width="478" height="833" alt="Screenshot 2026-08-13 at 4 25 23 PM" src="https://github.com/user-attachments/assets/83acce2e-7708-42f7-99b5-993afa8628f4" />

2. Click on the **blue arrow** to start the chat with Agentforce Vibes

<img width="971" height="344" alt="Screenshot 2026-08-13 at 4 26 19 PM" src="https://github.com/user-attachments/assets/c20d0693-3344-4122-a9fc-cbd86b5a3e94" />

3. Agentforce Vibes will generate an Implementation Plan that you should review before moving forward. You may want to resize the panel to get a better view of the plan.

<img width="752" height="753" alt="Screenshot 2026-08-13 at 4 26 46 PM" src="https://github.com/user-attachments/assets/dde2f573-8e38-43bc-9f78-a37102b51bfa" />

4. Once you have reviewed the entire plan, scroll down to the bottom of the plan, and click on the **Approve Plan** button

<img width="588" height="812" alt="Screenshot 2026-08-13 at 4 27 13 PM" src="https://github.com/user-attachments/assets/3b631715-8f75-474c-a282-e7b817bda635" />

5. Agentforce Vibes will begin implementing the plan, but will ask for approval before running any commands / search. Carefully review what Agentforce Vibes wants to do before approving.

   **IMPORTANT:** In real projects, do not blindly approve commands or searches, and do not enable features that automatically approve them for you. Automatic approval removes an important safety checkpoint and could result in unintended changes, deleted files or metadata, exposure of sensitive information, or destructive commands being executed in your environment.

<img width="1070" height="612" alt="Screenshot 2026-08-13 at 4 28 02 PM" src="https://github.com/user-attachments/assets/96d86cde-3616-4b3e-9fe6-a54d3027cb39" />

6. Agentforce Vibes will finish implementing the plan, and new files for both the new custom field and the LWC should be created. You will be able to review and approve each file related to the project.

<img width="1306" height="700" alt="Screenshot 2026-08-13 at 4 29 02 PM" src="https://github.com/user-attachments/assets/097a110b-693b-4027-8e01-1dccea2c6450" />

# Permission Set & Deployment

7. Next, send [**Prompt #2**](./prompts/prompt_2.txt) to create a permission set for the new field, deploy the metadata, and assign that new permission set to yourself (this does not have to run in plan mode)

<img width="460" height="820" alt="Screenshot 2026-08-13 at 7 02 51 PM" src="https://github.com/user-attachments/assets/31d6b3f4-16b9-47db-840b-440f9bfda095" />

8. Agentforce Vibes may ask for approval before running anything else. Review the requested changes, type out your approval in the chat window, then send the message.

<img width="602" height="722" alt="Screenshot 2026-08-13 at 7 04 19 PM" src="https://github.com/user-attachments/assets/e558e063-cd27-451a-ae68-9714de6e4362" />

9. A dry-run of the deployment process will begin. During the dry-run, Agentforce Vibes will check and try to resolve any deployment errors that occur. Each time a deployment issue is resolved, you may have to approve to rerun the deployment.

<img width="727" height="669" alt="Screenshot 2026-08-13 at 7 04 50 PM" src="https://github.com/user-attachments/assets/c32b3328-6712-48ad-93a5-5d661799f21c" />

10. Once all deployment errors are resolved, you can run the full deployment.

<img width="1201" height="330" alt="Screenshot 2026-08-13 at 7 05 45 PM" src="https://github.com/user-attachments/assets/c241dc11-3103-45a3-9d7d-2f1e08566c6d" />

11. Once the deployment succeeds, you be able to run the permission set assignment right within the chat

<img width="966" height="273" alt="Screenshot 2026-08-13 at 7 06 18 PM" src="https://github.com/user-attachments/assets/0b2acdd7-e2fd-47bb-8962-e0c68478c6a4" />

12. Once Agentforce Vibes is done, you will be able to review a summary of the work completed

<img width="569" height="686" alt="Screenshot 2026-08-13 at 7 06 54 PM" src="https://github.com/user-attachments/assets/d132d9fe-d8ca-4de0-a3d4-b275b5f3bcc5" />

# Deployment Verification and LWC Testing

13. In a different browser tab, navigate to Setup and verify that you have been assigned to the new permission set. You can also verify that access to the new “Sales Call Responses JSON” field has been granted through the permission set.

<img width="1169" height="334" alt="Screenshot 2026-08-13 at 7 07 18 PM" src="https://github.com/user-attachments/assets/89e57c62-8fc6-4b80-9ac7-bae7b194afad" />

<img width="1202" height="204" alt="Screenshot 2026-08-13 at 7 07 42 PM" src="https://github.com/user-attachments/assets/77358cae-ccec-4b09-ab4b-dd2ee4e1710a" />

14. Navigate to a random Opportunity record in your org, then select the option to **Edit Page**

<img width="1121" height="301" alt="Screenshot 2026-08-13 at 7 10 00 PM" src="https://github.com/user-attachments/assets/22408505-cc0d-499f-b4ca-68e85889cc59" />

15. Search for the “Sales Call Note Builder Prototype” LWC. Try adding the new component to the page.

<img width="1166" height="588" alt="Screenshot 2026-08-13 at 7 10 25 PM" src="https://github.com/user-attachments/assets/5eef87e2-4a86-4aa3-ad59-f5a12b8155bc" />

**NOTE:** If there are any errors during this stage, take a screenshot of the error, navigate back to Agentforce Vibes, and ask it to resolve the error for you. Once the error is resolved and the fix is deployed, refresh the page with the error, then try adding the component to the Opportunity Lightning Page again.

<img width="875" height="488" alt="Screenshot 2026-08-13 at 7 10 51 PM" src="https://github.com/user-attachments/assets/7f2758a5-53ee-4f2b-8830-75bf7c375e4d" />

16. Test out your brand new LWC on the Opportunity record page\!

<img width="1121" height="602" alt="Screenshot 2026-08-13 at 7 11 46 PM" src="https://github.com/user-attachments/assets/096d27cb-0305-45b9-9809-32447b4b983b" />

# Troubleshooting

You may be prompted to download the recommended Salesforce extensions. If so, please click on the **Install** button to begin the installation. Once the extensions are installed, you should be able to access Agentforce Vibes.

<img width="698" height="560" alt="Screenshot 2026-08-13 at 7 12 13 PM" src="https://github.com/user-attachments/assets/01b451ef-27db-453b-b097-0a9c257a7188" />

If you run into any network errors, try refreshing the page, then try running the prompt again

<img width="541" height="787" alt="Screenshot 2026-08-13 at 7 12 40 PM" src="https://github.com/user-attachments/assets/f8ca3244-d584-47df-96b8-adb04acac399" />

If you run into component errors, try switching the model

<img width="1051" height="232" alt="Screenshot 2026-08-13 at 7 13 03 PM" src="https://github.com/user-attachments/assets/32d6887b-d9c7-42a6-beed-0178f33cd0cb" />

Also, if there are too many errors, try asking Agentforce Vibes to completely rebuild the component using a “simpler modern implementation”  
