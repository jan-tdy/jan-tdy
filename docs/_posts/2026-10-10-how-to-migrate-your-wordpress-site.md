---
layout: post
title: "How to migrate your WordPress site using WPvivid"
date: 2026-10-10
---
First, sorry that this post is a bit late (I try to write one every week).
Also, you may see that this post is a bit different in style from the others, and that is right. Also, stay tuned for tech reviews in the future.

So this tutorial is about how to migrate your WordPress site using WPvivid, because it is a little complicated.

Ok, so let's get into this!

Please keep in mind that this guide assumes you have WPvivid already installed on both websites.

1. Generate an key
On the **DESTINATION** website, go to WPvivid -> Key.
Select an appropriate expiration time and click Generate.

2. Starting the transfer
On the **SOURCE** website, go to WPvivid -> Auto-Migration.
Paste the key generated on the destination website and click Save.
Select what you want to migrate, and click Clone and transfer.

3. Applying the "backup"
On the **DESTINATION** website, go to WPvivid -> Backup & Restore.
Click Restore on the latest backup (And read all disclaimers before doing so).

4. Done
Congratulations, you migrated your website!
Please keep in mind that the credentials have been migrated too.

Disclosure: This post describes my personal process. It's not sponsored content, and I have no affiliate relationship with WPvivid.

This guide describes what worked for me. Migrating a site can lead to data loss if something goes wrong (hosting incompatibility, WordPress/plugin version mismatch, database size, etc.). Always make your own backup before migrating, outside of WPvivid. I'm not responsible for data loss or downtime — proceed at your own risk and verify compatibility with your own hosting.

Steps/UI may differ in newer WPvivid versions — check the official docs for the current process." — since plugins change and your guide could go stale over time
