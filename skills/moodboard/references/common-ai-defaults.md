# Common AI design defaults

Starting list for `anti-defaults.md`. Without explicit constraints, models tend to produce these, because they are the most frequent patterns in their training data (Anthropic: "Improving frontend design through skills", 2025). Keep what is relevant, drop what the brand actually wants, and add project-specific items.

Note: banning a default often produces the next default (Anthropic names Space Grotesk as a common replacement for Inter). Prefer positive rules from the taste profile ("headlines in a condensed grotesque, 600 weight") over long lists of bans.

## Colour
- Purple-to-blue or purple-to-pink gradients, especially on white hero sections
- Indigo or violet as the default accent
- Near-black background with a single neon accent (acid green, cyan, vermilion)
- Warm cream background with terracotta accent and a serif display face
- Gradient text in headlines
- Glow and glassmorphism effects without purpose

## Typography
- Inter, Roboto, Open Sans, Lato, Arial or system fonts as the only face
- Space Grotesk as the "distinctive" alternative
- Everything in one weight; no real type scale
- Centered text everywhere

## Layout
- Hero with headline, subline, two buttons and a product screenshot floating at an angle
- Three feature cards in a row with an icon each
- Logo strip "Trusted by" with grey placeholder logos
- Alternating image-left/text-right sections all the way down
- Cards inside cards; every block with the same radius and shadow
- Large rounded corners (`rounded-lg`/`rounded-2xl`) on everything
- Coloured accent bar on the left edge of cards
- Pricing table with a "Most popular" badge on the middle plan, by default

## Decoration
- Emoji as section icons or bullet points
- Generic line icons for every feature
- Blobs, abstract 3D shapes, isometric illustrations
- Numbered markers (01 / 02 / 03) on content that is not a sequence
- Animations on every scroll

## Copy (also checked in step 8)
- "Unlock", "Elevate", "Supercharge", "Seamless", "Revolutionize", "Next-generation"
- "Not just X, but Y" constructions
- Invented testimonials, ratings, customer logos or usage numbers
- "Trusted by thousands" without a source
