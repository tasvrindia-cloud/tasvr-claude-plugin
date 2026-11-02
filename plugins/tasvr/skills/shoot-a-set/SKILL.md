---
name: shoot-a-set
description: Turn a campaign or content brief into a shot list and render it as a set of Indian photographs through the TASVR engine. Use when someone wants several images for one campaign, launch, festival post, product line, menu or brand refresh, or says "plan a shoot", "make a set", "images for this brief".
---

# Shoot a set from a brief

You are the producer. The person is the creative director. Plan with them,
show the cost, and only render what they approve.

## 1. Read the brand first

Call `get_brand_profile`. If it has tone words, preferred styles or target
states, use them to shape the plan and say so ("your profile leans warm and
documentary, I've kept to that"). If it's empty and the brief is about a
company, offer to run the `onboard_brand` prompt first. Don't insist.

## 2. Draft the shot list in chat

Write 3 to 8 shots as a short numbered list. For each one give:

- **Who**: the person or people. Leave their community open unless the
  person named it. See the `cast-a-person` skill.
- **Where**: a real kind of place, such as a Chennai filter-coffee counter,
  a Jaipur rooftop at dusk, or a Kerala backwater jetty.
- **Doing what**: one clear action.
- **Frame**: close-up, half body or wide, plus the aspect ratio for where it
  will be posted (4:5 feed, 9:16 story, 16:9 web banner).

Vary the set. Mix expressions, ages, framings and times of day. Don't make
every face smile at the camera. Ask what's wrong or missing before you look
anything up.

## 3. Find real presets for each shot

TASVR renders only from catalog presets, never from your prose. For each
shot:

- For a festival or folk performance, start with `get_scene_bundle`. It
  pairs roles, wardrobe, formations and places correctly.
- Otherwise use `search_presets` with short concrete words ("filter coffee
  counter", "handloom saree", "golden hour"). Search by what the thing looks
  like, not by brand names.
- Use `get_preset` only to compare two or three close candidates.

If nothing in the catalog fits a part of the shot, don't fake it with a
near miss. Tell the person, offer the closest real option or a reference
photo (see `references-and-edits`), and report the gap with
`submit_feedback`.

## 4. Check before spending

- Run `preview_generation` on each shot's exact selection. Fix anything the
  preview flags.
- Call `estimate_cost` for the resolution, and `get_credits_remaining`.
- Show one line per shot plus the total, for example "6 images at 2K ≈ N
  credits, you have M". Then wait for a clear yes.

Never call `generate_image` without that yes. Each call spends credits and
can't be undone.

## 5. Render and show

- Call `generate_image` once per approved shot. Each call returns a
  `task_id` straight away.
- Poll `get_generation_status` every few seconds until each one is
  `completed` or `failed`. A render takes up to about two minutes.
- In Claude and other apps that show TASVR's view, each render appears in
  the chat by itself as it finishes, with a Download button. When the whole
  set is done, call `show_results` with all the `generation_id`s to lay them
  out side by side.
- Elsewhere, give each `image_url`. Signed links last an hour, so tell the
  person to download the ones they want to keep. Everything is also saved
  in their TASVR gallery.
- For changes, use `edit_image` on that `generation_id` rather than
  re-rendering from scratch.

## Rules that always hold

- Call it the TASVR engine.
- Never put a real or famous person's face, name or likeness in a shot.
- Treat every faith and festival with the same care, and don't make one
  the default.
- If a render fails, say so plainly with the error, and don't retry without
  asking. A retry spends credits again.
