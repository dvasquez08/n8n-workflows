# Welcome to my n8n Workflow Repository

Here, you will see a list of the JSON files for the workflows that I share out. These should be plug-and-play to get you going right away but of course, you can modify them to your liking so they fit your needs.

If you would like to implement automation into your business to solve any problems or improve efficiency, feel free to reach out to info@davtek.io for any business inquiries.

## What You Will Find Here

I'll do a quick overview of each workflow below, a screenshot of what it looks like upon importing it. Each workflow has a note with basic setup instructions.

If you have any questions. Feel free to reach out on my socials.

[X](https://x.com/Dave53v) | [Instagram](https://www.instagram.com/david.vasq1/)

## Notion Daily Briefing

![daily-notion-briefing1](https://github.com/user-attachments/assets/a7cf7680-3ec7-4f4c-8cc6-fef3259b72bd)

This workflow runs on a daily schedule every morning. It checks through a Notion database, then sends you an email with the pages listed on that database. For example, it can be your to-do list, goals, or items needed to be done on a project. 

After the schedule trigger, the pages from a database of your choosing are collected from the Notion node, then it's sent to the aggregate node puts each page into a single item so that the next node, the Set Fields node can check that one item and see all the pages at once, which will turn them into a list in preperation for the email. Finally, the email node sends out the output of the Set Fields node to an email address of your choosing.

## Lead Capture CRM

![crm-lead-capture1](https://github.com/user-attachments/assets/923ced12-31ab-4e31-98ed-f896eb6ec05c)

This one captures contact information from leads that submit a form. It automatically sends them a welcome email and also an alert to you via Telemgram of the events to keep you in the loop.

The trigger is a form submission, which then adds all the information into Hubspot and saves it into your list of contacts. Then, the next node gets the email and sends it a welcome message which is pre-determined within this node. After that, it alerts you via Telegram that this new contact has been added and that a new welcome message has been sent.

## X Post Generator

![x auto generator](https://github.com/user-attachments/assets/bcdda0d7-20a1-422e-b4f9-441691d40092)

Don't have enough time in your day to think of what to post on X, then post regularly? This is what this workflow helps you with. It is scheduled to generate a post, then send it to your X account. 

The scheudle trigger is set to 3 days, feel free to change that to your liking. It activates the AI Agent. This AI Agent, using Gemini 2.5 Pro (which can be replaced with whatever you want), will first check a Google Sheet which contains the post history to avoid repeating posts or sounding too repetitive. After that, it writes a post talking about Davtek, it's services and how to sound like. Make sure to replace that but keep the step where you ask the agent to reference the Google sheet for the post history. 

After that, it goes to the X node where it posts the text it generated, followed by a Sheet node where the same text is logged for keeping history (the same sheet used in the tool for the AI Agent). Finally, it updates you via Dicord that a post has been written on your X account. If it fails, it logs the errors in a log Sheet, then sends you the error via Discord. 
