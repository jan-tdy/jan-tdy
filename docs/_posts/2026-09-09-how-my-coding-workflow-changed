---
layout: post
title: "How my coding workflow changed"
date: 2026-09-10
---

Hi all!
This article is about how my coding workflow (AI, Commit, PR, Releases, etc.) changed.

> **Disclosure:** This post describes my personal experience. I am not affiliated with the providers of the tools mentioned here, and they do not endorse this post.

![Just some stupid image]({{ "/assets/posts/chaos.png" | relative_url }})

## The start of my coding experience (end of 2024) - Commit system
In Slovakia, at the Astronomical Observatory in Kolonica, I made a simple Tkinter Python program to control a USB surge protector using AI. It worked; I added more features to it.
But I copy-pasted everything from an AI chat, and that AI was often "stupid." Coding a simple program was simply hard to do.

I was versioning by a number in the program title and downloading the latest from the main branch.

Prompt -> Wait -> Prompt -> Wait -> Commit -> Download -> Repeat


## Discovery of PRs and Claude Code (2026)
I wanted to add support for some Waste Collector to [mampfes/hacs_waste_collection_schedule](https://github.com/mampfes/hacs_waste_collection_schedule), and that is the first time I used Google Antigravity; I was amazed, but then I reached my limit.
That is approximately when I discovered PRs.
By the way, you can see the PR for this post here: https://github.com/jan-tdy/jan-tdy/pull/3

Then I continued contributing to [mampfes/hacs_waste_collection_schedule](https://github.com/mampfes/hacs_waste_collection_schedule) with [Google Gemini](https://gemini.google.com/),
and thanks to the amazing maintainers of mampfes/hacs_waste_collection_schedule, I discovered [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview), which changed everything!
Thank you very much @markvp and @bbr111!

So that is when everything changed.
- I started using pull requests for review and merging instead of managing changes directly.
- I made more and more programs with that amazing agentic AI, including [visual-astro](https://japysoft.bombol.space/info) (worth mentioning I discovered Lovable a few months before Claude Code)
- The AI (Claude Code) was smarter, worked with GitHub directly, and handled much more of the workflow on its own

Now I keep versions in some .json files and release using GitHub releases.

Prompt -> Wait -> Update -> Repeat

## Discovery of CodeRabbit (August 2026)
Then, in August 2026, I discovered CodeRabbit (yeah, AI started talking with AI under my eyes), an AI-powered code review rabbit...
It was free and found bugs in Claude Code, which was good, but now it is EVEN better.

Like I said, `Now I keep versions in some .json files and release using GitHub releases`, but in certain repos I have CHANGELOG.md and a GitHub action
Prompt -> Wait -> Release -> Update -> Repeat

Also worth mentioning that in August 2026 I discovered Vercel previews, which helped with my web apps like visual-astro - I no longer needed to merge to see if it looks like it should.

![Just some stupid image]({{ "/assets/posts/0212161.png" | relative_url }})

## The future
Is wild...
AI will review what other AI made (and they would talk to each other), and that will be reviewed by another AI, and the result will be reviewed by me.
Prompt -> Wait -> Review -> Update -> Repeat

