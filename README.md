# candid-cat-charm

Rank cat pictures by their unselfconscious charm — the presence of a natural, unposed moment that feels alive with authentic cat behavior.

## Overview

The internet is full of cat pictures, but we instinctively know that some are better than others. Not better in resolution or composition — better in the way that matters: the presence of something honest. `candid-cat-charm` exists to find those moments and elevate them. It ranks cat images not by photographic merit, but by how genuinely they capture a cat being itself — a kitten curled into an impossibly small ball, a cat caught mid-leap with all four legs splayed, a cat kneading a blanket with half-closed eyes lost in private contentment.

A blurry snapshot of a cat startled into an absurd posture will outrank a polished studio portrait, because the function does not care about the camera. It cares about the cat.

## Input

The function accepts an **array of cat images** (minimum 2) and produces a probability distribution ranking them by unselfconscious charm.

```json
{
  "type": "array",
  "description": "A collection of cat pictures to rank by unselfconscious charm.",
  "minItems": 2,
  "items": {
    "type": "image",
    "description": "A picture of a cat to evaluate for the naturalness and authenticity of the captured moment."
  }
}
```

## Output

A **vector** — an array of numbers that sum to approximately 1, where each value represents the relative candid charm of the corresponding input image. Higher values indicate images with more genuine, unselfconscious charm. The output preserves input order: `output[i]` is the charm score for `input[i]`.

## Use Cases

- **Content platforms**: Surface the most delightful cat content from millions of uploads, prioritizing the candid over the curated
- **Animal shelters**: Select adoption photos that show cats as they truly are — relaxed, curious, themselves — rather than stiff and frightened in a sterile cage
- **Personal photo libraries**: Sort so the truly magical moments rise to the top — the ones you forgot you captured, the ones that make you laugh or ache with tenderness years later
- **Content curation**: Filter and rank user-submitted cat content for newsletters, social feeds, or community galleries based on authentic charm rather than production value
- **Creative projects**: Identify reference images that capture genuine feline behavior for artists, writers, or filmmakers seeking authentic cat moments

## What It Evaluates

The function decomposes candid cat charm into three distinct qualities, each handled by a dedicated sub-function. The final ranking is a weighted blend of all three evaluations.

### 1. Authenticity of Behavior

**Sub-function:** [`rank-cat-authenticity`](https://github.com/ObjectiveAI-claude-code-1/rank-cat-authenticity)

The most foundational evaluation. This sub-function ranks images by whether the cat's behavior feels genuine — arising from the animal's own instincts and impulses rather than being arranged for the camera. It distinguishes between a cat expressing its own nature (kneading, leaping, stalking, sleeping in absurd positions, grooming) and a cat being used as a prop for human cleverness (costumed, held up, posed). The critical question: *does this cat's behavior feel real, the kind of thing it would do whether or not anyone was watching?*

**Ranks higher:** A cat caught mid-sneeze. A cat wedged into a box three sizes too small. A cat batting at dust motes in a sunbeam.
**Ranks lower:** A cat in a costume held to mimic a human pose. A cat placed on a prop for a staged photo. Any image where the cat is a vehicle for human contrivance rather than a subject in its own right.

### 2. Emotional Resonance of the Moment

**Sub-function:** [`cat-photo-emotional-resonance`](https://github.com/ObjectiveAI-claude-code-1/cat-photo-emotional-resonance)

This sub-function scores each image individually for how much genuine emotional power lives within the captured moment — and whether that power arises from the moment itself or from artificial packaging layered on top. It asks whether the image would still move you if you stripped away every caption, filter, and text overlay. Images where the feeling is inseparable from the moment score highest. Images that rely on embellishments to simulate resonance they don't inherently possess score lowest.

**Scores higher:** A cat asleep with its tongue slightly protruding. A cat curled protectively around a kitten. The visible relaxation of a cat choosing to be close to its person.
**Scores lower:** A heavily filtered image with overlaid "relatable" text. An image whose emotional appeal depends entirely on its caption. Content engineered for viral shareability rather than genuine feeling.

### 3. Quality of Witnessing

**Sub-function:** [`rank-cats-by-witnessing`](https://github.com/ObjectiveAI-claude-code-1/rank-cats-by-witnessing)

The most subtle evaluation. This sub-function ranks images by whether they feel like moments that were *discovered and caught* rather than *deliberately produced*. It looks for the texture of accident, spontaneity, and fortunate timing — signs that someone was present, paying attention, and recognized something worth preserving. It also evaluates the sense of impermanence: the feeling that this fleeting instant was almost lost but was, through luck and attention, saved.

**Ranks higher:** A cat mid-yawn with every tooth on display. A kitten's first encounter with snow. An imperfectly framed shot of a cat in a sunbeam on a cluttered desk. Anything that says *"look what I was lucky enough to see."*
**Ranks lower:** Studio-lit pet portraits. Images with controlled backdrops and deliberate composition. Anything that announces its own production — the unmistakable air of a photoshoot rather than a life lived alongside a cat.

## Philosophy

The best cat pictures feel like small acts of witnessing rather than staged productions. They say: *look, here is this creature doing what it does, and isn't it wonderful that we get to see it.* Cats do not perform — they simply are. The best pictures of them honor that by simply watching, and being grateful for what they see. This function exists to find those pictures and place them where they belong: at the top.