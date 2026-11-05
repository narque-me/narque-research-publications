# A tiny GIF acceptance checklist
## Context
OpenAI introduced Images 2.6 on November 4, 2026, including GIF creation. The cat used here is an actual account-generated result: 358 × 358 pixels, 12 frames, about 1.68 seconds per loop. One output is not a benchmark or a guarantee for every account or image.

## A small, reproducible file check
```python
from PIL import Image, ImageSequence

with Image.open("sample.gif") as image:
delays = [frame.info.get("duration", 0)
for frame in ImageSequence.Iterator(image)]
print({"format": image.format, "size": image.size,
"frames": len(delays), "loop_seconds": sum(delays) / 1000})
```

## Acceptance criteria
- Confirm the file format and multiple frames.
- Sum frame delays; do not infer processing speed from frame count.
- Inspect loop continuity and anatomy separately.
- Keep account authorization and publication permission separate.

The kitten is an actual generated result. Birthday and waving-character scenes are original use-case illustrations. Interface excerpts are screenshots, not a continuous recording. This does not establish accurate likeness preservation for personal photos.

Source: https://openai.com/index/introducing-images-2-6/

AI-assisted writing. File metadata checks do not replace visual review.
