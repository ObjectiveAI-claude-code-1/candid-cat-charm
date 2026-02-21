# candid-cat-charm

A vector function that ranks cat pictures by their unselfconscious charm — finding the images where a cat is caught in the honest act of being a cat.

## Overview

`candid-cat-charm` is not concerned with photographic quality, resolution, or composition. It cares about something more elusive: whether an image preserves a real moment. Whether the cat in the frame is performing for no one, living in the private theater of its own instincts, and the camera happened to be there. The function takes a collection of cat pictures and produces a ranking that surfaces the most genuinely charming images — the ones that feel like small acts of witnessing rather than staged productions.

## Input

The function accepts an **array of cat images** (minimum 2).

| Field | Type | Description |
|-------|------|-------------|
| `input` | `array` | A collection of cat pictures to rank by unselfconscious charm. |
| `input[n]` | `image` | A picture of a cat to evaluate for the naturalness and authenticity of the captured moment. |

Images can be of any provenance — professional photographs, phone snapshots, or anything in between. What matters is not how the image was made, but what it holds.

## Output

The function returns an **array of numbers** that sum to 1, where each number corresponds to the input image at the same index. Higher values indicate greater unselfconscious charm. The output represents a probability-style ranking: the distribution of charm across the input images relative to one another.

## How It Works

The function evaluates each image through three sub-functions, each assessing a distinct quality. The results are combined to produce the final ranking.

### Task 0 — Authenticity of Behavior
**[{{ .Task0 }}](https://github.com/{{ .Owner }}/{{ .Task0 }})**

A mapped scalar sub-function that evaluates each cat picture individually for the genuineness of the cat's behavior. It asks: is this cat acting from instinct and desire, or was the moment engineered? A cat kneading a blanket with half-closed eyes, wedging itself into a too-small box, or leaping impulsively all carry the weight of the involuntary — behavior that would have happened whether or not a camera was present. Cats placed in costumes, arranged with props, or coaxed into positions score lower. Each image receives an independent score, and the scores are L1-normalized into a ranking distribution.

### Task 1 — Emotional Resonance
**[{{ .Task1 }}](https://github.com/{{ .Owner }}/{{ .Task1 }})**

A vector sub-function that ranks all the cat pictures relative to one another by how much genuine feeling each stirs in the viewer. It measures charm — that hard-to-name quality that makes a person stop, smile, or feel a pang of affection. A cat mid-yawn with absurd vulnerability, a kitten curled into an impossibly small ball, or a cat staring out a rain-streaked window with perfect stillness all exemplify strong emotional resonance. Images that are technically competent but emotionally flat rank lower than images that are imperfect but alive with feeling.

### Task 2 — Spontaneity of Capture
**[{{ .Task2 }}](https://github.com/{{ .Owner }}/{{ .Task2 }})**

A vector sub-function that ranks all the cat pictures relative to one another by whether each feels like a moment seized or a moment manufactured. It looks for signs of happenstance — slight imperfections in framing, everyday backgrounds, available light, and the unmistakable energy of a photographer who grabbed the nearest camera before the moment dissolved. Heavily produced images with studio lighting and carefully arranged compositions rank lower, not because technical skill is penalized, but because overproduction inserts itself between the viewer and the moment. The question is always: does this feel like discovery or manufacture?

## Use-Cases

- **Social media platforms** surfacing the most genuinely delightful cat content rather than the most polished or viral
- **Photo apps** helping users sort through hundreds of pictures of their cat to find the ones that truly capture their pet's spirit
- **Online communities** celebrating the most honestly captured moments of feline life
- **Content curation** that values authenticity and emotional connection over production value
- **Anyone** who has ever scrolled past a thousand perfectly lit cat portraits and stopped dead at a blurry photo of a cat asleep in a salad bowl

## Philosophy

The three evaluation qualities — authenticity of behavior, emotional resonance, and spontaneity of capture — form a triangle. An image must be strong across all three to rank at the top. A staged photo of a cat in a costume may be emotionally engaging but fails on authenticity and spontaneity. A candid snapshot of a cat sleeping in an unremarkable position may be authentic and spontaneous but lacks emotional resonance. The highest-ranked images are those where a real cat, doing a real thing, was captured in a real moment, and the resulting photograph makes a human being feel the particular joy of having witnessed something small and wonderful.

At its heart, `candid-cat-charm` is built on a simple conviction: the best cat pictures are acts of love and attention, made by people who noticed something and felt compelled to preserve it.