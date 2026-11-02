---
name: references-and-edits
description: Use a product photo, pose or style reference in a TASVR render, or change an image TASVR already made. Use when someone attaches a photo ("put our bottle in her hand", "match this pose"), wants to reuse a saved avatar or product, or asks to fix, add to or remove something in a finished image.
---

# References and edits

## Put a real photo into a render

1. **Upload it.** Call `upload_reference_image` with the file's bytes
   (`imageBase64`) or a link (`sourceUrl`). You get back a TASVR URL.
2. **Give it one role.** Call `list_reference_roles`, then pass the image in
   `generate_image`'s `references` with the single role it plays: the
   product, the pose, the camera angle, the jewelry. Only that one thing is
   taken from the photo, and the rest of the photo is ignored.
3. **Ask before keeping it.** Uploads are temporary. Ask if they want it in
   their library, and only then call `save_reference_to_library`.

To reuse something saved earlier, call `list_reference_images`.

To pull one thing out of a busy photo, such as a necklace from a wedding
picture, use `isolate_reference_item`. It spends credits, so confirm the
cost first.

## Change an image you already made

Use `edit_image` with the `generation_id` of the finished image. The
original is kept and the edit is saved as a new image.

- **edit**: a general change, or adding a non-person object ("make the sky
  overcast", "add two more goats behind her").
- **remove**: take something out ("remove the walking stick").
- **add**: put a new person in.
- **face**: change who an existing person is, using a reference photo.

Write the instruction as one specific change. Two small edits in a row work
better than one long list.

Edits spend credits like renders do. Show the cost, wait for a yes, then
poll `get_generation_status` for the result.

## Don't

- Don't upload photos of people the person hasn't said they have rights to
  use.
- Don't use a reference to copy a celebrity, a brand's ad or another
  photographer's work.
