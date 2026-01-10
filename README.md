# Welcome to my n8n Workflow Repository

Here, you will see a list of the JSON files for the workflows that I share out. These should be plug-and-play to get you going right away but of course, you can modify them to your liking so they fit your needs.

If you would like to implement automation into your business to solve any problems or improve efficiency, feel free to reach out to me at dvasquez@davtek.io for any business inquiries.

## What You Will Find Here

I'll do a quick overview of each workflow below, a screenshot of what it looks like upon importing it. Each workflow has a note with basic setup instructions.

If you have any questions. Feel free to reach out on my socials.

[X](https://x.com/Dave53v) | [Instagram](https://www.instagram.com/david.vasq1/) | [YouTube](https://www.youtube.com/@davtekio) | [Davtek Website](https://davtek.io)

For business inquiries: dvasquez@davtek.io

## Table of Contents

- [Daily Notion Briefing](#notion-daily-briefing)
- [CRM Lead Capture](#crm-lead-capture)
- [X Post Generator](#x-post-generator)
- [BlueSky Post Automation](#bluesky-post-automation)
- [Automated URL Uptime and Error Logging](#automated-url-uptime-and-error-logging)
- [YouTube Video Upload Automation](#youtube-video-upload-automation)
- [Azure Employee Onboarding](#azure-employee-onboarding)
- [Social Media Manager Text Only](#social-media-manager-text-only)
- [Multi-Agent AI Assistant](#multi-agent-ai-assistant)

## Notion Daily Briefing

![daily-notion-briefing1](https://github.com/user-attachments/assets/a7cf7680-3ec7-4f4c-8cc6-fef3259b72bd)

This workflow runs on a daily schedule every morning. It checks through a Notion database, then sends you an email with the pages listed on that database. For example, it can be your to-do list, goals, or items needed to be done on a project.

After the schedule trigger, the pages from a database of your choosing are collected from the Notion node, then it's sent to the aggregate node puts each page into a single item so that the next node, the Set Fields node can check that one item and see all the pages at once, which will turn them into a list in preperation for the email. Finally, the email node sends out the output of the Set Fields node to an email address of your choosing.

## CRM Lead Capture

![crm-lead-capture1](https://github.com/user-attachments/assets/923ced12-31ab-4e31-98ed-f896eb6ec05c)

This one captures contact information from leads that submit a form. It automatically sends them a welcome email and also an alert to you via Telemgram of the events to keep you in the loop.

The trigger is a form submission, which then adds all the information into Hubspot and saves it into your list of contacts. Then, the next node gets the email and sends it a welcome message which is pre-determined within this node. After that, it alerts you via Telegram that this new contact has been added and that a new welcome message has been sent.

## X Post Generator

![x auto generator](https://github.com/user-attachments/assets/bcdda0d7-20a1-422e-b4f9-441691d40092)

Don't have enough time in your day to think of what to post on X, then post regularly? This is what this workflow helps you with. It is scheduled to generate a post, then send it to your X account.

The scheudle trigger is set to 3 days, feel free to change that to your liking. It activates the AI Agent. This AI Agent, using Gemini 2.5 Pro (which can be replaced with whatever you want), will first check a Google Sheet which contains the post history to avoid repeating posts or sounding too repetitive. After that, it writes a post talking about Davtek, it's services and how to sound like. Make sure to replace that but keep the step where you ask the agent to reference the Google sheet for the post history.

After that, it goes to the X node where it posts the text it generated, followed by a Sheet node where the same text is logged for keeping history (the same sheet used in the tool for the AI Agent). Finally, it updates you via Dicord that a post has been written on your X account. If it fails, it logs the errors in a log Sheet, then sends you the error via Discord.

## BlueSky Post Automation

![BlueSkyAuto](https://github.com/user-attachments/assets/fbaae88f-ad0f-4d12-bf67-63cfcc12d4a3)

Much like the X post generator, this workflow does the same thing, but with BlueSky. n8n does not have a official BlueSky node, but that's not a big deal. You just need a couple of HTTP nodes, one to get your user ID, and the one after that to post the text output from the AI, to Bluesky. This one is scheduled every monrning. The AI Agent does checks for the Google Sheet docs for the post history, then it writes a question of the day, which is passes to the HTTP nodes and then it gets posted to BlueSky. It will then update the Google Sheets for the post history and send its notification to Discord.

## Automated URL Uptime and Error Logging

What this workflow will do is it will take a list of URLs or IP addresses, loop through them and ping each address. When they are successful, the results are logged into a Google Sheet. If there are errors, it is also logged in a Google Sheet where it logs the errors. After that, the results are grouped into successful replies and failed replies. Each group of results are sent to an email for reporting. You can use this to check the uptime of networking equipment, servers, printers, website, etc.

![url-uptime-logging](https://github.com/user-attachments/assets/899b776d-8519-4e2f-acaf-77bfe4baea4b)

## YouTube Video Upload Automation

This one was one of my favorites to build. It's a hands-free automation where an AI agent thinks of a prompt to send to Veo 3, creates an appropriate title and description, then passes that information on. The prompt is sent to Veo 3 where it is then combined with the title and description. All information is sent to the YouTube node where it is uploaded to a YouTube channel. The last step is a notification on Discord, letting me know that the video was uploaded.

One thing to keep in mind. Is that if you want to change the aspect ratio, this breaks the Gemini node, but you can easily change it on the YouTube mobile app. This is also very expensive. Approximately $6 per video. I signed up for free credits up to $400 dollars, so this will be good for a while, but keep that in mind. Third party video generators such as Wavespeed AI come to about the same.

![youtube-automation](https://github.com/user-attachments/assets/f9964cd5-e0a1-40b4-9958-8b1757842c16)

## Azure Employee Onboarding

Being an IT Administrator, I know that often tiems there are steps that are missed when it comes to onboarding a new employee. Their user account is not created yet, their laptop hasn't been setup yet because the team that sets up the laptops had no idea the employee was starting, I've seen it all!

This inspired me to do this automation in n8n. This is executed by a form submission. Once the form is submitted, it triggers the Entra ID nodes to create an account, add to any security groups, creates the uer in Jira and sends a welcome email. It also schedules an orientation meeting in their calendar with their new manager and sends a Teams message to a channel which can be the IT Team for example, letting them to know a new person has stated, and they will probably need a laptop. Give it a try, and hopefully you find it helpful!

![azure-employee-onboarding](https://github.com/user-attachments/assets/66fb7443-ab67-47d6-a194-53bbc73d4eea)

## Social Media Manager (Text-Only)

This section is composed of two parts, as I made two different versions of this workflow.

### Telegram Trigger Version

![Telegram Bot Social Media Workflow](https://github.com/user-attachments/assets/41a3a50e-8250-4496-b0be-f8db900e177f)

The first one here, is the Telegram Social Media Manager. This allows you to post a single message, across multiple social media platforms. In this template, you can send a post to X, LinkedIn, and BlueSky at once with a single message to a Telegram bot, which executes the flow, sends its output to the social media platforms which make your post, using that message. It finally sends you a confirmation in your Telegram chat when it is complete.

This is great for those who want to automate their social media, but with control. They can still decide exactly what they want to post with their own words, just across mulitple platforms at once, instead of logging into each app and posting it multiple times.

### AI Agent Version

![Social Media AI Agent](https://github.com/user-attachments/assets/9adef872-7ecf-4727-bb60-1b081a4f4a30)

This version accomplishes the same goal as the last workflow, it uses the exact same nodes with the same settings but the key difference is that it is using an AI Agent instead of a Telegram bot. Unlike the Telegram bot, the AI Agent decides what topic to post about by using it's RSS feed tool, and then decides what to say about that topic. Then, just like the Telegram bot, it sends its output to the social media nodes, posting the message all at once. This runs on a schedule so that it is fully autaomomous and hands free.

This is great for those who struggle to find ideas of what to post and how to say their message, or simply do not want to take the time to log into each platform, think of what to say and post a message there. The AI Agent can completely handle the idea creation, the text for the post, then sends it to the rest of the workflow.

You can have a hybrid setup where you use both of these at once. You can have the AI Agent post 1 or 3 times a week, then you can post on other days of the week so you maintain authenticity, and some control of what is on your socials.

### Multi-Agent AI Assistant

![multi-agent workflow - parent agent](https://github.com/user-attachments/assets/6f634281-5c9e-4946-96de-e23708af7ea9)

This is a workflow that uses multiple AI Agents. Each agent has its own workflow and one AI agent acts as the parent agent which takes all queries from the user via Telegram using a Telegram bot. The parent agent has two tools which are the child workflows that are called upon depending on the task given to the parent agent. Each sub-workflow''s agent has specific tools and a specialty that is called if they are needed for the task.

The first sub-workflow is a calendar agent. Whenever anything calendar related needs to be done such as, "check my events for this date," or "please create an event for this date," this tool will be called and the sub-workflow's agent will call it's Google calendar tools in order to complete this task.

![multi-agent-workflow - calendar agent](https://github.com/user-attachments/assets/c1539c71-5bd3-4c65-914c-01c2df46c28f)

The second sub-workflow is a Notion agent. This workflow is called when anything Notion related is being requested such as, "please get me the pages for my Notion database," or "Add this page to my Notion database."

![multi-agent workflow - notion agent](https://github.com/user-attachments/assets/843c2369-e634-4df7-a810-950b018896b1)

### AI Voice Assistant

img

This setup is similar to the multi-agent workflow where it calls sub-workflows for specific tasks, only this time you can talk to your assistant using your voice, and get a voice reply from your agent using ElevenLabs. This also uses a Telegram bot, you can text to it or use the microphone feature in Telegram to send an audio file. The agent proceses your message, calls the tools that it needs for the specific request, and then it sends it's reply through Telegram, sending an audio file of its reply with a voice. The voice can be picked from ElevenLabs' large voice library, which you can use to set a specific language of your choosing.
