# Gemini generation for Song Prompt Studio v1.1.047

The app's optional Gemini features run in the private online Studio:
https://song-prompt-studio-gemini.tinysiren10.chatgpt.site

The GitHub Pages site and downloaded HTML remain usable without Gemini. Those
copies link to the online Studio because GitHub Pages cannot run a secret-bearing
server endpoint. Use Save/Open to move a project between the two environments.

## Server contract

`gemini-api.mjs` exports `handleGemini(request, env)` for POST `/api/gemini`.
It requires a server runtime secret named `GEMINI_API_KEY`. No key belongs in
HTML, browser storage, project JSON, GitHub variables committed as source, or logs.
The deployment wraps this module with the HTML page and the Sites owner-only
access boundary. Do not expose this handler as an anonymous public API; add
server-side authorization and durable usage controls before a public rollout.

Supported tasks:

- `artist`: reference `artist` name and optional `notes`. Returns an editable
  `description`, a qualification `note`, and a `recognized` flag.
- `lyrics`: `lyricPrompt`, `style`, ordered `sections` with names/directions and
  `instrumental`. Returns the same ordered structure with original lyric text.

The gateway uses Gemini 3.5 Flash-Lite through the Interactions API, with optional conversation storage disabled (`store:false`).
Requests are validated and capped at 40 KB. No automatic retries or paid-model
fallbacks are made. Rate-limit failures leave all existing form and Workshop
text intact. An API key inherits its Google project's billing status; this app
does not enable or change billing.

## Private preview deployment

Sites project: `appgprj_6ad296a1dc6481919b52480c316ff0ee`.
The server secret is managed separately in Sites. Source and artifact packaging
use the Sites Worker ESM workflow, retaining the owner-only access policy.
The worker bundles this handler and the reviewed `index.html`; its API route
runs on the same origin. A future update must preserve this access boundary.

## Review behavior

Artist suggestions are drafts; they do not replace a description until applied.
Form autofill is optional and preserves the user's register and accent choices.
Lyrics use the current generated lyric prompt and style. Applying a lyric draft
archives previous Workshop sections; Save/Open preserves applied text and the
archive. Unapplied generation previews are temporary. Generated lyrics are
reviewed with the existing word/line and rhyme checks; target compliance is not
guaranteed by the model.
