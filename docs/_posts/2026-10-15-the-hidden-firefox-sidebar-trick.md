---
layout: post
title: "The Hidden Firefox about:config Trick for a Permanent Web Sidebar"
date: 2026-10-15
---
This time, I am on time with my current post schedule!


So, basically, I discovered that you can set the browser.ml.chat.provider Firefox parameter to any URL you want.


We’ve all been there: you want your task manager, your team chat, or your email constantly visible on the side of your screen while you browse, without installing heavy, resource-hogging extensions.

By hijacking Firefox's built-in, experimental AI chatbot panel, you can turn it into a permanent, native web wrapper for your favorite productivity apps. Here is exactly how to do it.

The Secret: Hijacking the AI Chat Provider

Firefox recently introduced native AI sidebar integrations. To make this work, Mozilla created a configuration flag that tells the sidebar which AI URL to load inside its panel.

But here is the trick: the sidebar doesn’t actually care if the URL is an AI or not. It will try to render whatever web address you feed it.

How to set it up:

Open a new tab in Firefox and type about:config into the address bar. Accept the warning to proceed.
In the search bar at the top, paste this exact preference name:
browser.ml.chat.provider
Click the pencil icon on the right side of the screen to edit the string.
Replace the default AI link with the web app of your choice. (For example, to load Gmail/Google Workspace, paste: https://mail.google.com).
Press Enter or click the checkmark to save.
Now, open your Firefox Sidebar, switch the panel view to your AI chat provider, and watch your custom web app load natively right next to your active tabs!

Why This Works (And the Catch)

Why hasn't anyone told you about this before? Because technically, we are "misusing" an API meant for LLMs.

Because it’s a standard web frame, you might run into a security feature called X-Frame-Options. Many major sites (like Todoist or Notion) explicitly block themselves from being loaded inside frames to prevent security exploits. If you see a blank gray screen, that website's security policy is blocking the trick.

Fortunately, major communication hubs like Google Workspace (Gmail, Google Chat) have flexible enough framing rules that they work beautifully, giving you a sleek, native-feeling side panel layout.
