# AI Filmmaking Skills

**A practical guide to five AI filmmaking skills.** The installable files preserve the workflows from the source article, with the requested naming cleanup. The guide explains how to use them together.

## The short version

Treat the five skills as a production pipeline. You can also use any one by itself.

| Step | Skill | Output | Reach for it when… |
| --- | --- | --- | --- |
| 1. Define the world | **Story Bible Builder** | A reusable canon `SKILL.md` | Your series needs consistent premise, timeline, character behavior, factions, and visual rules. |
| 2. Lock the cast | **Castkit v1** | Face, outfit, and character reference stills | A character must remain recognizable across shots and styles. |
| 3. Build the place | **Scenecraft v1** | Environment plates, coverage, or a first frame | You need a coherent location, lighting, and camera viewpoint. |
| 4. Direct the shot | **Shotcaller v1** | Structured Seedance video prompt | You need staged action, dialogue, camera, sound, physics, and timing. |
| 5. Transfer motion | **Motiondojo v1** | Higgsfield Genjutsu prompt | You already have motion footage and want to preserve its body movement or camera path. |

**Choose Shotcaller or Motiondojo for the final motion step based on your input.** Shotcaller directs a Seedance generation. Motiondojo transfers motion from a separate reference video in Genjutsu. They are complementary, not mandatory sequential steps.

## QuickStart: install and make one shot

### 1. Install the five skills

**Claude on the web or desktop:** Extract the bundle. In Claude, open **Customize → Skills → + → Create skill → Upload a skill**. Upload each file in `install-zips/` **one at a time**, then make sure all five appear and are enabled. The outer `AI Filmmaking Skills.zip` is a distribution bundle, not a single skill upload. Claude requires each uploaded ZIP to contain one skill folder at its root. If skills or upload controls are unavailable, check **Settings → Capabilities → Code execution and file creation** and your workspace’s skill permissions. [Claude upload instructions](https://support.claude.com/en/articles/12512180-use-skills-in-claude) · [ZIP structure](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills)

**Claude Code:** Extract the bundle, then copy the five directories from `skills/` into `~/.claude/skills/` (personal) or your project’s `.claude/skills/` (project only). Keep Story Bible Builder’s supporting files in its folder. Run `/skills` to check discovery; invoke explicitly with `/story-bible-builder`, `/castkit-v1`, `/scenecraft-v1`, `/shotcaller-v1`, or `/motiondojo-v1`. [Claude Code skill locations and invocation](https://code.claude.com/docs/en/skills)

**Codex:** The `skills/` folders use `SKILL.md` with frontmatter. If you use a Codex setup that supports custom skills, add each folder through its supported skill installation route, then request it by `$name`. The workflows were written for Claude, so review model-specific instructions and adapt any Claude-only assumptions before relying on them in Codex. [OpenAI skills overview](https://developers.openai.com/codex/skills-and-plugins)

### 2. Run this small end-to-end example

Start with **one character, one location, one 10-second shot**. Save each approved output and attach it at the next step. The skills write prompts and reference plans; use your image/video generation tools to create the actual media.

1. **World — Story Bible Builder.** “Build a compact story bible for *Last Train*: a courier finds an impossible message on an empty platform. One main character, grounded sci-fi, no exposition. Interview me only for details needed for a 10-second teaser.” Save its generated project canon. You do not need a full series bible for this first test.
2. **Character — Castkit.** “Use the *Last Train* canon. Make a photoreal face lock for the courier: [your defining traits]. Then propose a raincoat outfit. Wait for my approval before generating the outfit.” Generate and approve the face and full-body outfit reference.
3. **Place — Scenecraft.** “Create an empty late-night subway platform plate for [your image model]. Damp concrete, one working fluorescent strip, deep perspective. Use the attached image for palette only. Make a matching first frame with the approved courier at the platform edge.” Generate and approve the plate and first frame.
4. **Shot — Shotcaller.** “Seedance [version], 10 seconds. Use the attached courier reference and platform first frame in this order. The courier notices a paper message sliding toward their shoe, picks it up, and looks toward the dark tunnel. No dialogue and no music. Give me the pre-prompt check, then a paste-ready prompt.” Approve the check, paste the prompt into Seedance, attach references in the same order, and generate.
5. **Optional motion-transfer branch — Motiondojo.** If you have a real reference clip of the pickup action, attach that clip separately in Genjutsu, plus a screenshot and the approved courier/platform stills. Ask: “Body Copy, New Camera. The only performer is the courier. Keep the exact bend, pickup, and weight shift from the attached motion transfer video. No speech.” Use this **instead of step 4** for the motion-transfer version, then compare results.

**Review before the next shot:** Does the face match the lock? Is the coat unchanged? Is the platform geometry consistent? Does the note contact the ground and hand naturally? Fix the earliest reference that drifted, then regenerate only the affected downstream output.

## A working sequence

1. **Create the canon.** Tell Story Bible Builder your working title, short premise, genre, cast size, existing material, and generation tools. It interviews you, then produces a project-specific skill. Keep that resulting canon file separate from the builder itself.
2. **Lock each character.** In Castkit, start with a face lock and declare photoreal or animated style. Approve the face before outfits. Generate a full-body outfit image and, if useful, a three-panel character sheet. Use neutral reference lighting so later scene lighting can change freely.
3. **Make location plates.** Give Scenecraft the target image model, location, time, mood, and labeled references. Ask for an empty environment, people in scene, matching coverage angles, or a precise edit. Approve the location’s geometry and light before asking for multiple shots.
4. **Make a shot plan.** Decide which characters and plates are inputs, the action beats, shot duration, dialogue or audio, and whether the shot is generated from references or transferred from a motion clip.
5. **Write the video prompt.** For Seedance, give Shotcaller the version, duration, ordered references, action, camera, and speaker-labeled dialogue. For Genjutsu, give Motiondojo the motion clip, a screenshot of it, character/location references, performer mapping, and the desired copy mode.
6. **Review continuity.** Compare identity, outfit, location geometry, lighting, left/right performer assignment, speech, and physical contact across outputs. Revise the relevant upstream reference when drift begins, then regenerate the affected shot.

## How to ask each skill

### Story Bible Builder — define what cannot drift

It conducts an interview, then creates a **new project-specific canon skill** containing world rules, timeline, visual eras, factions, locations, character voice and movement, relationships, plot engines, and production rules.

**Give it:** a title or working title, a rough pitch, genre, number of characters, what is already settled, and tools you plan to use. Say “just lock my characters” if you want a narrower interview. Provide an existing bible when updating canon.

> Build a story bible for a four-character sci-fi short series called *Signal House*. The core premise is [two sentences]. We’ll create reference stills and Seedance video. Start by identifying canon gaps, then interview me section by section.

### Castkit v1 — make stable character references

The five stations are **face lock → additions → outfit build → outfit replacement → character sheet**. Outfit work depends on an approved face; the sheet depends on an approved outfit. Its neutral gray, shadowless background keeps scene lighting out of the identity reference.

**Give it:** rendering style, defining facial traits, identity markers, and labeled inspiration images. For outfits, include garment references and approve the textual outfit proposal first.

> Create a photoreal face lock for Mara: [age range and traits], cropped chest-up. Keep the neutral reference background. After I approve the face, propose an outfit using the attached jacket and boots; do not build the outfit yet.

### Scenecraft v1 — make a location that can be filmed

Four modes: **A** empty environment (default), **B** people in scene / first frame, **C** matching coverage angles, **D** plate edit. State what each reference controls: palette, architecture, character, composition, or another specific feature. For edits, identify the exact change and what must stay fixed.

**Give it:** target image model, place, time of day, mood, lighting source, desired mode, and labeled references.

> For Seedream 5.0 Pro, make an empty diner plate at blue hour. The attached photo controls room geometry only; the second image controls palette only. Practical pendant lights are warm. Then plan a matching reverse angle without changing the booth layout.

### Shotcaller v1 — direct Seedance shots

Shotcaller uses a 16-part production structure for references, staging, first frame, lens/FOV, camera, lighting, atmosphere, timed action, physics, acting, audio, and continuity locks. It asks for the Seedance version and gives a brief pre-prompt check before the final paste-ready prompt. The author’s article lists **2.0: 9 references / 15 seconds** and **2.5: 50 references / 30 seconds**; verify limits in your own generation interface because platform limits can change.

**Give it:** version, duration, references in attach order, whether to use element tags or `@imageN`, action beats, camera, audio, and exact speaker-labeled dialogue. Say when a track is attached for lip sync; say “extend this clip” for an extension. The skill splits sequences exceeding the version cap.

> Seedance 2.5, 12 seconds. Use numbered `@imageN` references: image 1 Mara, image 2 Eli, image 3 diner first frame. They argue quietly across the booth. Script: MARA: “You knew before we arrived.” ELI: “I only knew the address.” Keep the table geometry and their screen positions stable. Show me the pre-prompt check first.

### Motiondojo v1 — transfer movement in Genjutsu

Pick **Body Copy** for the same body motion and camera, **Camera Copy** for only the camera path, or **Body Copy, New Camera** for preserved body motion with a rebuilt handheld camera. Its prompt locks mouth behavior. Attach the motion video separately; it is **not** tagged in the prompt. Character and location references use `<<<image_N>>>` in attach order. The source video does not define character identity or scene design.

**Give it:** motion video and a screenshot, character/location references, mapping of left/center/right performers, selected form, and exact transcript if someone speaks. Genjutsu audio is handled separately according to the author’s workflow.

> Body Copy, New Camera. Use the attached two-person dance clip. The left performer becomes Mara (`<<<image_1>>>`); the right performer becomes Eli (`<<<image_2>>>`). The rooftop (`<<<image_3>>>`) sets the location. No speech; mouths stay closed. Keep both performers’ foot contact and weight shifts believable.

## Install and use the bundle

The `skills/` directory has one folder per skill. Each folder has a canonical `SKILL.md`. Story Bible Builder also has three supporting Markdown files; keep those next to its `SKILL.md`.

For Claude’s skill upload, use the ready-made, single-skill ZIPs in `install-zips/`. In a filesystem-based setup, copy the directories under `skills/`. **Downloading this archive does not install or activate the skills automatically.**

The Story Bible Builder creates a *sixth*, project-specific `SKILL.md` after your interview. Install that generated canon separately, and update it as your project changes.

## Practical checks

- **Name every reference’s job.** A reference can control face, wardrobe, architecture, palette, first frame, or motion; say which.
- **Preserve approval points.** Lock the face, outfit, and plate before asking a video model to combine them.
- **Keep dialogue exact.** Paste speaker labels and literal lines. For silent shots, say there is no speech.
- **Watch interface drift.** Model limits and tag syntax may change; use the currently displayed generation interface as the final authority.
- **Review third-party skill instructions before installing.** These source files are text instructions. The bundle contains no executables; their instructions will influence an agent once installed.

## Contents

```text
AI Filmmaking Skills Guide.md
skills/
  story-bible-builder/      SKILL.md + 3 interview/reference files
  castkit-v1/               SKILL.md
  scenecraft-v1/            SKILL.md
  shotcaller-v1/            SKILL.md
  motiondojo-v1/            SKILL.md
install-zips/              five individually uploadable skill ZIPs
```

Source: [All My Claude Skills for Better Prompting, @joeysnoisygroup](https://higgsfield.ai/@joeysnoisygroup/blogs/all-my-claude-skills-for-better-prompting?fpr=joey), posted September 24, 2026 (article updated with an “as of October 2026” heading). The descriptions and workflow here summarize the source article and downloaded files; example prompts are newly written for this guide.
