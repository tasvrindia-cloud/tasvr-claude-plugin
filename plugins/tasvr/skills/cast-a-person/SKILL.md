---
name: cast-a-person
description: Choose who appears in a TASVR image, with authentic regional representation. Use whenever a shot has a person in it and their community, region, age or look has to be settled, or when someone asks for "an Indian woman", "a person from Karnataka", "a local farmer" or "any face".
---

# Cast a person

Every person in a TASVR image comes from a real community in the catalog.
The point is to get the person right, not to guess.

## Never pick a community silently

- If the person hasn't said where the subject is from, ask before you
  generate. Offer two or three real options that suit the brief and the
  place. Don't decide for them.
- Never infer a community from someone's name, surname, religion or
  language, or from a stereotype about a job or place.
- "Any face", "surprise me" or "you choose" is the one case where you may
  pick. Say which one you picked, before you render.
- If `generate_image` stops and asks who should be in the photo, put that
  question to the person as it stands. Don't answer it yourself.

## Find the right community

1. If a state is named, call `list_ethnicities_by_state` for it. If no state
   is named, call `list_ethnicity_states` and ask which region fits.
2. If `get_brand_profile` has target states or preferred communities, show
   those first. They're still only suggestions.
3. Use the catalog's own label for a community, exactly as written. Don't
   shorten it, translate it or swap in a word of your own.
4. Pass the chosen id as the person's `ethnicityKey`. One key per person.

## Then the rest of the look

- **Age and gender**: ask if they matter and weren't stated. Don't assume
  from the job.
- **Wardrobe**: `search_presets` with category `wardrobe`. Match it to the
  place and the occasion, such as everyday cotton for a market or silk for
  a wedding. For a festival scene, take the wardrobe `get_scene_bundle`
  lists under that role.
- **Expression and pose**: vary them across a set. A pose preset is an
  action, such as pouring, laughing or walking past.

## When the catalog falls short

If a community, region or dress the person needs isn't there, tell them
plainly, offer the nearest real option, and send `submit_feedback` with
exactly what was asked for. Don't approximate with a different community.

## Own faces and avatars

To feature a specific real person, such as the founder or a model they
have rights to, use their saved reference from `list_reference_images`.
Never use a celebrity or public figure.
