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

Before you start: this uses `about:config` and an experimental, undocumented Firefox feature, so it can change or stop working entirely in a future Firefox release without notice. It's also not a supported use of the feature, so proceed at your own risk.

How to set it up:

0. Make sure the AI Chatbot sidebar tool is enabled first — open the Firefox Sidebar and confirm an AI Chatbot entry is available. If it isn't, re-enable/restore it in Settings before continuing.
1. Open a new tab in Firefox and type about:config into the address bar. Accept the warning to proceed.
2. In the search bar at the top, paste this exact preference name:
browser.ml.chat.provider
3. Click the pencil icon on the right side of the screen to edit the string.
4. Replace the default AI link with the web app of your choice. (For example, to load Gmail/Google Workspace, paste: https://mail.google.com).
5. Press Enter or click the checkmark to save.
6. Now, open your Firefox Sidebar, switch the panel view to your AI chat provider, and watch your custom web app load natively right next to your active tabs!

**Privacy note:** this field is still the AI chat provider slot, so Firefox may still send selected text, page titles, prompts, or page content to whatever URL you put there if you trigger a built-in AI prompt action (e.g. "Ask AI" from a context menu) while a non-AI app is loaded there. Only point this at trusted HTTPS URLs, avoid loading anything with sensitive/confidential data in it this way, and don't use Firefox's built-in AI prompt actions while a non-AI app is loaded in that slot.

Why This Works (And the Catch)

Why hasn't anyone told you about this before? Because technically, we are "misusing" an API meant for LLMs.

Framing restrictions can still block the trick: a site can refuse to be embedded via the `X-Frame-Options` header or a CSP `frame-ancestors` policy (and Firefox loads the provider URL in a XUL `<browser>` element here, not a plain HTML `<iframe>`, so behavior isn't guaranteed to match what you'd expect from embedding in a regular page). Many major sites (like Todoist or Notion) block this kind of embedding outright. If you see a blank gray screen, that website's policy is blocking the trick.

Google Workspace (Gmail, Google Chat) worked for me without issues, giving a sleek, native-feeling side panel layout — but whether a given site works can depend on your Firefox version and that site's own policies, so your results may vary.
