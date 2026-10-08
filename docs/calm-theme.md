# Calm (Low Stimulation) theme

A fourth colour theme, selectable anywhere the other three are: Settings › Appearance › Color
Theme, or `theme calm`. It persists as `theme = "calm"`.

## Why it exists

Premiere's three themes are one design at three lightnesses: a pure-black app background, three
near-identical blues (focus, accent, playhead, timecode), square corners, 4 px gaps. Calm is a
different tuning for sustained use by people for whom that density is a cost — ADHD and autistic
users in particular.

## What it changes

| | Dark | Calm |
|---|---|---|
| App background | pure black `#000000` | warm near-black `#121211` |
| Panels | neutral `#1d1d1d` | warm `#242422` |
| Blues in play | 4 (focus, accent, playhead, timecode) | 1, the accent `#85b7eb` |
| Render bar | saturated red / yellow / green | the same three, desaturated |
| Corners | square | 6 px |
| Panel gap | 4 px | 6 px |

## The half-fixed one

The render bar is a **colour-only** status cue: red, yellow and green bars with no shape or label
to tell them apart. Calm desaturates them so they stop shouting, but desaturating a colour-only
cue does not make it readable to someone who cannot separate those hues. The real fix is a shape
or a label per state, which is a widget change, not a token change. It is not done here.

Everywhere else, colour is paired with an icon or a label — **colour is never the sole carrier of
meaning**, which is the rule this theme is built around.

## Where the values come from

The surface, text and accent tokens are the dark half of the INT Digital design system
(warm-neutral greys with a faint warm bias, one semantic accent, a dark theme designed in its own
right rather than inverted from the light one).

## Adding to it

`Tokens::for_kind(ThemeKind::Calm)` in `crates/ui-egui/src/theme.rs` holds every override over
`dark`. Widgets read `Tokens`, so nothing else needs touching — if a widget hard-codes a colour,
that is the bug, not the theme.
