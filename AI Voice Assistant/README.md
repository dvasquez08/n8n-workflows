# AI Voice Assistant

Welcome! Here are my templates needed for the AI Voice Assistant, the parent workflow and all of the sub-workflows that are called by the parent. This is a great assistant that you can use to help you become more efficient, and make your day to day life easier.

This is a completely scalable and customizable setup that you can really make your own. Feel free to grab all of these templates from me.

Watch how I set this up right here: [Watch my YouTube Video](https://youtu.be/7MMKqgMsmKQ)

If you have any questions, feel free to leave me a comment on my video, and I'll help you as best as I can.

## What this is

This is a setup that is all orchestrated by one parent AI agent. This AI agent is connected to other sub-workflows, each with their own AI agent as tools. Each tool has a specific duties. For example, one workflow focuses only on Calendar tasks, it is called when anything needs to be done on your Google Calendar. Another workflow is for Notion, being called only when Notion related tasks are being requested.

You communicate with the parent agent via Telegram, using text or your voice. The parent agent then replies with its output with a voice, chosen by ElevenLabs.

## Watch Part 1 of this setup

Make sure you watch this video for part 1 of this entire setup: [Multi-Agent Workflow](https://youtu.be/LVD8DrvVspw)

This is where I show you how to configure a multi-agent setup, get your Telegram Bot created, and also create the Notion and Calendar sub-workflows.

## Setting Up This Template

First, make a folder in your n8n account to keep your workflows organized. Open each JSON file above, copy it to a text file, and then save it as a JSON file. You can do that my renaming the file to whatever you like, followed by ".JSON" and the file will be saved as a JSON file.

In n8n, you would then click on the three dots on the top right, select "Import by File," and then choose the JSON you copied, making sure that each JSON file has its own n8n workflow as well, making sure not to put them all into one.

## Good to know

I mentioned this in the tutorial, but make sure you grab your Telegram Chat ID and set it up in the Simple Memory node, and the the Send an Audio file. I've added placeholders there to let you know where to enter the ID.

You can get your ID by executing the Telegram trigger on its own, and send any message. The Chat ID will show up in the output. Copy that and replace the ID placeholders with that Chat ID

Make sure you are on the latest version of n8n if you are using a self-hosted version. If you are using n8n cloud, this should have been updated for you already.

When creating your sub-workflows, make sure to publish them, otherwise they will not be picked up when called upon.
