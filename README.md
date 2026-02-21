# candid-cat-charm

Ranks cat pictures by their unselfconscious charm — surfacing natural, unposed moments that feel alive with authentic cat behavior, and letting contrived or staged content sink.

## How It Works

Given a collection of cat photographs, `candid-cat-charm` produces a ranking that reflects how much genuine, unposed life each image contains. It evaluates every image across three qualities — behavioral authenticity, emotional resonance, and spontaneous aliveness — then combines those evaluations into a single weighted ranking. The result is a probability distribution over the input images: higher values mean more candid charm.

## Input

An array of **2 or more cat images**. Each element is an image of a cat to be evaluated. The images can be of any quality, style, or origin — professional photography, phone snapshots, accidental captures, or staged portraits. The function handles them all and places each on the spectrum from contrived to candid.

## Output

An array of numbers (one per input image) that sum to 1, representing a probability distribution. Each number reflects the relative candid charm of the corresponding image. Higher scores indicate images with more authentic, emotionally resonant, and spontaneously alive moments.

## What It Evaluates

The function decomposes candid charm into three sub-evaluations, each handled by a dedicated sub-function:

### 1. Behavioral Authenticity

[`{{ .Task0 }}`](https://github.com/{{ .Owner }}/{{ .Task0 }})

Scores each cat image individually for the genuineness of the cat's observed behavior. Examines body language, posture, and physical state for signs of real feline behavior — the boneless limpness of true sleep, the committed wildness of a mid-leap body, the half-closed eyes of contented kneading, the alert crouch before a pounce. Penalizes signs of staging: costumes, constructed sets, treats luring the cat's gaze, or poses that feel physically unnatural. Human presence does not reduce authenticity when the interaction feels mutual and genuine.

**Type:** Mapped scalar — each image is evaluated independently, then scores are normalized into a distribution.

### 2. Emotional Resonance

[`{{ .Task1 }}`](https://github.com/{{ .Owner }}/{{ .Task1 }})

Ranks the full set of images by the emotional weight each captured moment carries. Looks for vulnerability made visible (a kitten trusting enough to sleep exposed, a cat surrendering to affection), feline comedy and absurdity (a cat wedged into a too-small box, the dignified outrage of mild inconvenience), and any moment that stirs genuine feeling. Recognizes that charm operates across many emotional registers — warmth, humor, tenderness, surprise — and rewards images where we feel we are witnessing something true about who the cat is.

**Type:** Vector — images are ranked relative to one another, because emotional impact is inherently comparative.

### 3. Spontaneous Aliveness

[`{{ .Task2 }}`](https://github.com/{{ .Owner }}/{{ .Task2 }})

Ranks the full set of images by how much each photograph feels like a seized moment of serendipity rather than a planned composition. Looks for hallmarks of spontaneity: motion blur, imperfect framing, natural lighting, and backgrounds showing the ordinary texture of real life. Penalizes overproduction: studio lighting, meticulous composition, and artificially curated settings. Rewards the sense of temporal urgency — the feeling that the shutter clicked just in time.

**Type:** Vector — images are ranked relative to one another, because spontaneity is best judged by comparison.

## Use Cases

- **Social media curation:** Surface the most genuinely charming cat content from a large pool, prioritizing honest moments over engagement-optimized posts.
- **Animal shelter showcases:** Select photographs that capture who shelter cats really are — their personalities, their quirks, their unguarded moments — rather than stiff, staged portraits.
- **Personal collections:** Sort through a camera roll of cat photos to find the keepers — the ones that feel alive and worth sharing.
- **Community platforms:** Power ranking and discovery features that reward authenticity over production value in cat photo communities.
- **Gift and print selection:** Identify the images from a set that would make the most meaningful prints, cards, or gifts — the ones that make people stop and smile.

## Philosophy

`candid-cat-charm` encodes a simple belief: the best cat pictures are not the most polished or the most viral, but the most true. They are small acts of witnessing — moments where a camera happened to catch a creature being fully, unselfconsciously itself. The function privileges honesty over production value, feeling over technique, and the unrehearsed over the performed. It exists to find those moments of truth and lift them up where they can be seen.