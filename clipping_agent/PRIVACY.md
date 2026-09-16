# Privacy Policy — Clipping Agent

_Last updated: 16 September 2026_

Clipping Agent is an open-source command-line tool that runs entirely on the
user's own computer. This policy describes what data the tool handles and where
it goes. Everything below can be verified in the source code at
<https://github.com/metiu1/editorvideo-ai/tree/main/clipping_agent>.

## 1. Who operates the tool

Nobody but you. The authors do not run a hosted service, do not operate
servers that the tool talks to, and do not receive any data from your
installation. There is no telemetry, no analytics, no crash reporting and no
usage tracking of any kind.

## 2. Data the tool handles, and where it is stored

All of the following stays on your machine, under directories you control:

| Data | Where | Why |
|---|---|---|
| Video and audio files you supply, and the clips cut from them | `campaigns/<campaign>/` on your disk | Editing and publishing |
| Campaign brief and rules you point the tool at | `campaigns/<campaign>/campaign_spec.json` | Deciding how to cut and caption clips |
| Processing state and event log (step status, post IDs, public URLs of posts you made, timestamps) | `campaigns/<campaign>/agent/state.json` and `agent/events.jsonl` | Resuming after an interruption and verifying results |
| TikTok authorization data obtained via TikTok Login Kit: access token, refresh token, expiry times, your TikTok `open_id`, display name and the scopes you granted | `~/.clipping_agent/tokens/tiktok/<account>.json`, readable only by your user account | Publishing to your TikTok account on your instruction and renewing the token without asking you to log in every day |
| Optional Chromium browser profile, if you configure `browser.profile_dir` | The directory you choose | Keeping you logged in to campaign websites you submit to |

Secrets (tokens, API keys, client secrets) are never written to log files:
the logger redacts them.

## 3. Data sent to third parties

The tool sends data only to the platforms you explicitly connect and only when
you run a publishing or authorization command:

- **TikTok** (`open.tiktokapis.com`, `www.tiktok.com`): during authorization,
  the OAuth request with your app's client key; during publishing, the video
  file, its caption/title and privacy setting, and requests to read the status
  and public URL of the posts it created. Scopes used: `user.info.basic`
  (to identify which account a token belongs to), `video.publish`,
  `video.list`.
- **YouTube** and **Instagram** (Google / Meta APIs), if you configure them:
  the video file and its metadata, with tokens you provide.
- **Campaign websites** you point the tool at (for example Content Rewards):
  reading the campaign page and, on your instruction, submitting the public URL
  of a post you made.

Nothing is shared with anyone else. The tool contains no advertising, no
third-party SDKs and no cookies of its own.

## 4. TikTok data specifically

Through TikTok Login Kit the tool receives your `open_id`, display name, the
tokens described above and the list of scopes you granted. It uses them solely
to publish videos you ask it to publish and to read back the status and share
URL of those videos. It does not read your other videos, followers, messages or
any other TikTok data, and it does not store TikTok data anywhere except the
local token file described in section 2.

## 5. Retention and deletion

Data stays on your disk until you delete it. To remove TikTok data:

- run `clipping-agent auth tiktok --revoke` (revokes the token with TikTok and
  deletes the local token file), or delete
  `~/.clipping_agent/tokens/tiktok/` yourself; and/or
- revoke the app on TikTok under *Settings → Security → Manage app permissions*.

Campaign folders and logs can be deleted like any other files.

## 6. Children

The tool is not directed at children and requires accounts on third-party
platforms that have their own age requirements.

## 7. Changes

Updates are published in the repository; the current version is
<https://github.com/metiu1/editorvideo-ai/blob/main/clipping_agent/PRIVACY.md>.

## 8. Contact

Open an issue at <https://github.com/metiu1/editorvideo-ai/issues>.
