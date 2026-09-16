# Terms of Service — Clipping Agent

_Last updated: 16 September 2026_

Clipping Agent is an open-source command-line tool, part of the
[editorvideo-ai](https://github.com/metiu1/editorvideo-ai) repository, that runs
on the user's own computer. It cuts short-form video clips from footage the user
supplies and, on the user's explicit instruction, publishes them to social
platforms (including TikTok, through the TikTok Content Posting API) using the
user's own accounts.

## 1. License

The software is released under the MIT License (see the repository `LICENSE`
file). It is provided "as is", without warranty of any kind. The authors are not
liable for any damage arising from its use.

## 2. Self-hosted operation

There is no hosted service. Every part of the tool — video processing,
authorization with social platforms, publishing — runs locally on the machine
where the user installs it. The authors do not operate servers for this tool
and never receive the user's videos, tokens or account data.

## 3. User responsibilities

By using the tool you agree that:

- you own, or have the right to use and publish, all footage and audio you
  give to the tool;
- content you publish through the tool complies with the terms and community
  guidelines of the platform you publish to (for TikTok: the TikTok Terms of
  Service and Community Guidelines) and with any campaign rules you take part in;
- you are responsible for the accounts you connect and for every post the tool
  makes on your instruction;
- you will not use the tool for spam, for posting the same content across
  multiple accounts, or for any unlawful purpose.

## 4. Platform APIs

The tool calls the official APIs of third-party platforms (TikTok, YouTube,
Instagram) with credentials that you obtain and authorize yourself. Your use of
those APIs is governed by the respective platform's developer and user terms.
Platform features may change or be withdrawn by the platform at any time.

## 5. Revoking access

You can stop the tool from accessing a platform account at any time by revoking
the authorization on the platform (for TikTok: *Settings → Security →
Manage app permissions*) or by running `clipping-agent auth tiktok --revoke`,
which revokes the token with TikTok and deletes it from your machine.

## 6. Changes

These terms may be updated in the repository; the version published at
<https://github.com/metiu1/editorvideo-ai/blob/main/clipping_agent/TERMS.md>
is the current one.

## 7. Contact

Open an issue at <https://github.com/metiu1/editorvideo-ai/issues>.
