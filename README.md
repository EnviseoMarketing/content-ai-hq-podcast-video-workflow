# Content AI HQ — Three-Person Podcast / Video Workflow

This is a reusable browser-automation playbook for **Content AI HQ**. It adapts the orchestration approach of the `ai-playbooks/historical-documentary-video-workflow` baseline to create a 16:9 YouTube podcast/video with three recurring virtual hosts:

- **Alex Mercer** — host and practical moderator
- **Maya Chen** — AI strategist and optimistic systems thinker
- **Jack Reynolds** — experienced business owner and constructive skeptic

The workflow is deliberately designed to minimize manual editing:

1. CloneVoice generates labeled speaker audio.
2. A manifest identifies each audio segment and its intended visual treatment.
3. TalkingPhotos generates only selected lip-sync/on-camera clips.
4. Timestamped source or webinar clips provide evidence and demonstrations.
5. VideoExpress fills genuine visual gaps with B-roll, graphics, captions, and 16:9 timeline assembly.
6. A human performs final quality control in VideoExpress (or DaVinci Resolve only when a finishing pass is genuinely needed).

It is not a standalone application or API integration. It is an instruction set for a browser-capable production agent working in the visible interfaces of CloneVoice, TalkingPhotos, and VideoExpress.

## What is different from a normal video podcast

The workflow does **not** place a talking avatar on screen for every line. The presenters remain narrative anchors, but the default visual rhythm is:

`on-camera host → proof/demo clip or generated visual → voice-over continues → another host or group reset`

That keeps the finished video visually useful, reduces TalkingPhotos generation time, and avoids constant hard cuts between three faces.

## Required inputs

- A podcast brief or approved script with speaker labels.
- Locked CloneVoice assignments: Alex = **Oliver Bennet**, Maya = **Maya Linwood**, Jack = **Lachlan Mercer**.
- Existing 16:9 Alex, Maya, and Jack assets in TalkingPhotos under **Human → Previous Characters**.
- Any source/webinar videos with clip timestamps and the right to use them.
- A filled production manifest based on [`templates/production-manifest.yaml`](templates/production-manifest.yaml).
- 16:9 as the output ratio (this playbook is optimized for YouTube landscape).

## Main deliverables

- CloneVoice audio clips named and labeled by speaker.
- TalkingPhotos clips only for `talking_head` segments in the manifest.
- A VideoExpress project with all audio, demo clips, on-camera clips, B-roll, simple graphics, and captions assembled.
- An EDL-style manifest recording the timeline order, source clips, and asset links.
- A saved/export-ready 16:9 YouTube video; do not publish or share it unless explicitly asked.

## Quick start

1. Read [`SYSTEM_PROMPT.md`](SYSTEM_PROMPT.md) as the operating instructions.
2. Copy and complete [`templates/production-manifest.yaml`](templates/production-manifest.yaml).
3. Give the agent the approved script, source assets, host images, and manifest.
4. Let the agent generate assets and assemble the project.
5. Review the saved project and export only after confirming that the audio/visual handoffs are correct.

## Recommended video structure

For a 8–12 minute episode, aim for 30–45% visible hosts, 25–35% source/demo clips, 15–25% generated B-roll or graphics, and a small amount of title/caption treatment. These are guardrails, not quotas.

## Guardrails

- Preserve the baseline repository; this workflow is a separate adaptation.
- Keep original webinar/source clips traceable in the manifest and use only material the producer is authorized to use.
- Do not use an avatar to claim personal actions it did not perform. Prefer “we tested,” “the team found,” or “here’s what happened.”
- Do not create, publish, share, or change public visibility without explicit authorization.
- Do not let the system make unsupported claims about features, costs, performance, or monetization.
- Verify specific app capabilities in the live UI; interfaces change.

## Baseline acknowledgement

This playbook is conceptually derived from the public `ai-playbooks/historical-documentary-video-workflow` structure: visible-browser production, a persistent system prompt, asset reuse, guarded assembly, and final verification. It replaces the historical-documentary requirements with a three-host, source-evidence, and EDL-driven podcast/video format.
