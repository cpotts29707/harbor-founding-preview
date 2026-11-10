# Harbor V8 — Natural Voice Integration Plan

Status: planning and testing. The live Harbor V7 site is unchanged. The V8 preview currently stores voice preferences but **does not play OpenAI-generated speech**.

## Founding voices
Cedar, Marin, Onyx, Coral, Sage, Ash.

## Sample script (identical text for fair comparison)
"Welcome to Harbor. I'm glad you're here. Whatever today has brought your way, you don't have to figure everything out at once. We can take this one moment at a time."

## Stage 1: Six prerecorded previews
- Generate the six sample clips using an authorized speech-generation account and a supported speech model.
- Check the current provider's model/voice compatibility and terms before generation; a playground preview alone does not prove API availability.
- Use the same words and similar speaking instructions for all clips; compare perceived warmth, clarity, pacing, and accessibility.
- Save only nonpersonal prerecorded audio files in the public site, for example `v8-preview/audio/cedar.mp3`.
- Display an explicit AI-generated audio disclosure and captions/transcript; include pause/stop, volume and no-audio choice.
- Do not substitute browser speech for a premium voice without labeling it.

## Stage 2: Secure dynamic speech (not implemented)
- Public GitHub Pages JavaScript calls a separate authenticated/rate-limited serverless backend over HTTPS.
- The backend holds provider credentials in secret configuration, never in this repository or browser.
- Ask for informed opt-in before sending any text to a speech provider. Make the text destination, retention policy, costs and limits understandable.
- Avoid sending names, contacts, private plans, or free-text check-ins by default. The prototype is not a crisis-response service.
- Set strict request size, spend limits, abuse prevention, error handling, and fallback to readable text.
- Honor voice choice and speed only if the actual speech model supports them; otherwise disable or explain the control.
- Do not promise that selected voices can be used until current API support is verified.

## Testing checklist
- [x] Six profile choices appear in V8 preview.
- [x] Selection persists after refresh (manual test).
- [x] Browser receives the selected speaking rate (manual test).
- [ ] Audible browser speech rate changes (not confirmed; device voice may ignore).
- [ ] Six genuine prerecorded premium voice samples added.
- [ ] Play, pause, stop, transcript and no-audio controls verified on Windows Chrome and iPhone Safari.
- [ ] Privacy, accessibility, consent and cost reviewed.
- [ ] Dynamic backend implemented and tested (optional later phase).

## Important deployment notes
The `v8-preview/` directory is the public test site on `main`. The `harbor-v8-voice-studio` branch and draft PR #1 contain proposed root-site V8 changes and must not be merged until tested. Any audio sample should be licensed/authorized for hosting.
