# AURION - Chase the Light (AI Spec Brand Film)

A 20-second cinematic spec commercial for a fictional electric sedan brand, shot as a
dawn-to-golden-hour journey through Cairo. Built to study continuity techniques in
generative video: one hero car held consistent across four distinct scenes.

**Watch:** `film1_aurion_20s.mp4` - 1920x1080, 24 fps, exactly 20.0s, silent.

## Structure

| # | Scene | Source clip | Notes |
|---|-------|-------------|-------|
| 1 | Dawn on the Nile corniche | PixVerse V6 text-to-video (576p, upscaled) | Anchor scene: establishes the car |
| 2 | Old Cairo street | Vidu Q4 image-to-video (1080p) | Anchored to a frame of scene 1; first 2.25s trimmed (model re-rendered the corniche before transitioning) |
| 3 | Desert highway aerial | Vidu Q4 reference-to-video (540p, upscaled) | Anchored to the same car frame |
| 4 | Golden-hour hero shot | Vidu Q4 reference-to-video (540p, upscaled) | Same anchor; briefed as night, rendered golden-hour - kept for the dawn-to-dusk arc |
| - | End card | ffmpeg drawtext | Fictional brand lockup, original tagline "Chase the Light" |

## Continuity technique

Text-to-video with repeated descriptors produced a different car every generation
(and once a real-brand lookalike, rejected). The fix: generate one clean anchor frame,
then drive every later scene with image/reference-to-video from that frame. Car
identity (light bar, silhouette, wheel design) holds across all four scenes; frames
were inspected for real badges - none present.

## Post

- Assembled with ffmpeg: lanczos upscale to 1080p, one unifying grade
  (contrast/saturation/vignette), hard cuts, fade to end card.
- No frame interpolation or looping; the trimmed head was absorbed by the end-card
  length so the final runtime stays exactly 20s.

## Rights and disclosure

- All footage is AI-generated (PixVerse V6, Vidu Q4); the tools' watermarks are
  retained on purpose.
- AURION is a fictional brand. No endorsement by or affiliation with any real
  carmaker. Any resemblance to a real production vehicle is unintended.
- Personal portfolio / work-sample use only. Not for sale or commercial reuse.

`qa-grid.png` shows five frames across the four scenes and the end card.
