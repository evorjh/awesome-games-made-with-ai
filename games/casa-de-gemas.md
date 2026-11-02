# Casa de Gemas

**[▶ Play Casa de Gemas](https://amusehall.com/games/casa-de-gemas/?utm_source=github&utm_medium=game-file&utm_campaign=awesome-games-made-with-ai)** · [Original post](https://github.com/deepujain/casadegema)

<a href="https://amusehall.com/games/casa-de-gemas/?utm_source=github&amp;utm_medium=game-file&amp;utm_campaign=awesome-games-made-with-ai"><img src="https://media.amusehall.com/casa-de-gemas/preview.webp?v=ebd5748ba7" alt="Casa de Gemas by @deepujain" width="100%"></a>

- **Made with:** Claude Opus 5.5
- **Creator:** [@deepujain](https://github.com/deepujain)
- **Genre:** Puzzle, Cozy
- **Plays on:** Computer and phone
- **Price:** Free
- **Controls:** Mouse (click, hold and drag), or tap and drag on phones
- **Likes on the original post:** Unknown

A watercolor-style courtyard of a Spanish house where you water, shake and tap things to find five hidden gems in each of four seasons.

## Play notes

The garden starts bare: you pick up the watering can and hold the mouse button to pour, and a hot-pink bougainvillea grows out of the tree bed. Each season hides five gems, found by actions like tapping the little speaker to start the music, shaking a branch until its petals fall or picking a new petal color from the paint palette. Oli the owl on the tower roof gives a hint when you tap him. The creator says a full year takes 10 to 15 minutes and ends with a birthday message rising from the chimney; it was made as a gift for the creator&#39;s daughter, and a name can be added to the link. The creator also shared the full prompt for rebuilding it. Works on phones and computers.

## Prompt

```text
Build a single self-contained index.html (pure JavaScript + Canvas 2D, no libraries, no
images, no build step) called "Casa de Gemas" — a little garden of hidden gems, made as a
birthday gift for a daughter and shared as a link (mostly opened on phones).

SCENE
- Soft watercolor illustration on warm cream paper. Fixed 1200×950 logical stage scaled to
  fit the window (letterboxed on laptops; phones get a zoomed camera, see TOUCH). Pre-render static
  art into offscreen layers using layered low-alpha deformed polygons plus paper grain.
- A whitewashed Spanish house: a tower with a terracotta roof, blue shutters and wall pots,
  a main house with a tiled roof, a chimney, an arched wooden door with blue-tile surround
  and steps, a balcony with iron railing, a barred window with flowers, exposed brick
  patches, two lanterns beside the door.
- In the courtyard: a round brick tree bed on the right of the house (no pot for the main
  tree; it stands clear of the facade), two small pots, a wooden bench/table with two jars
  and a little pink speaker, a wooden paint palette on the ground, a twig lying on the
  ground, a chalkboard easel on the left in front of the tower with a stick of chalk on its
  ledge, a cute watering can, and a little girl seen from behind holding a heart balloon on a
  string, with a bow on the back of her dress.
- Custom cursor: a butterfly in the current petal color, with sparkles. It perches (slow
  wings) on whatever tool you hold. When the pointer is away it flies to the girl's dress
  and rests there as her bow, full size, still fluttering.

GROWTH
- The garden starts bare. Pick up the watering can (click), click-and-hold to pour — water
  drops, splashes and a pouring sound. Watering the bed grows a bougainvillea tree
  (procedural segments with stable spring physics; grabbing a branch bends its parent
  chain). Watering each pot grows a small plant. Every tree uses a different petal color,
  bright and saturated so it pops against the cream walls: hot pink for the main tree, then
  vivid purple, sunny gold, coral and sky blue (blush and ivory stay soft). Each petal has a
  deeper rim in its own color and a small white sheen; a soft mint wash sits behind the
  main tree instead of pink.
  Put the can back by clicking its spot or pressing Esc; it also returns by itself when
  everything is planted.
- Petals: shaking a branch hard detaches petals that flutter side to side as they fall
  (gravity wins; only a light breeze, stronger in autumn) and settle on the ground near
  their tree, then slowly fade; bare spots regrow.

A YEAR IN FOUR SEASONS (about 10–15 minutes)
- Spring, summer, autumn, winter. A counter at the top-left shows four season dots, the
  season name, "n/5" and one gem icon per gem of the current season (five every season). Each
  discovery pops a gem at that spot which then flies to the counter and lights it up.
- When a season's gems are all found, Oli says goodbye to it and the next season arrives
  on its own element, changing the garden as it passes (every effect stays subtle): summer
  on a soft, faint rising sun with a few gentle motes, whose light
  spreads out from the top-right corner, autumn on a gust of wind that blows leaves across
  from the left (trees sway in it), winter on a snowfall that settles from the top down.
  Trees, bushes, geraniums and window boxes change color where the element has reached;
  the color grade cross-fades, the counter resets and Oli introduces the next season.
- Trees and plants match the season; only spring has flowers on the trees. Spring:
  mostly blossoms with a few fresh green leaves (under a tenth leaves), green bushes, red geraniums.
  Summer: warm golden grade, trees are full of deep green leaves and no flowers, brighter
  geraniums. Autumn: amber grade, every tree and bush turns orange, red and gold with
  leaf-shaped sprites, leaves drift down on their own. Winter: cool blue grade; as the
  snowfall passes the last leaves drop and the branches go bare, then snow slowly builds up
  over about 45 seconds as small clumps on the twigs and white lines along the tops of the
  flatter branches (shaking a branch knocks snow off). Plants turn grey-green with white
  dabs; snow covers the roofs, sills, steps and courtyard, and flakes keep falling.
- ?season=summer|autumn|winter starts there with everything before it done.

OLI THE OWL
- Oli perches on the tower roof from the start and speaks in a small speech bubble:
  an intro and a goodbye for each season, a short reaction to most discoveries, and a hint
  for the next gem when you tap him (which also sends the feather there). He only hoots at
  night and wears a red scarf in winter.

WALL-POT VISITORS
- Every season one of the seven blue wall pots on the tower hides a little visitor (a
  different pot each season); finding it is that season's fifth gem. Tapping a pot mostly
  just puffs a few petals — the visitor needs an action. Spring: water the pots with the can,
  a nest of chicks; they burst into chirps when they appear, then peep in small bursts
  every few seconds with their beaks opening in time (`Music.chirp`). The nest stays in
  its pot for the rest of the year (`nook.nest`, drawn by `drawNest`, snow on its rim in
  winter; later visitors never pick that pot) and the chicks chirp whenever the cursor
  butterfly or a butterfly friend comes near. The chicks grow a little each season. In
  winter they wait out the long night; once it is light again (`nightLv < .3`, at least
  7 s into winter, or after 60 s regardless) `nest.fly` is set and they take off 0.8 s
  apart with a chirp each, small yellow birds flapping up and away to the upper left
  (`fledgling`). Oli says they are off somewhere warm; the empty nest keeps its snow. Summer: water the pots or rest the butterfly
  cursor still on one (holding the can is fine), a ladybug crawls onto the rim. Autumn: a little tail curls over the rim of the mouse's pot
  and that pot rustles now and then; tap it (or press and wiggle it) for a field mouse nibbling an acorn.
  Winter: tap or brush the pots with the held twig (any part of it) to knock the snow off,
  a robin. Every pot the twig touches sheds a little snow.

LANTERNS (all year)
- Tap a lantern — it goes out and its fireflies fly off to hang in the tree canopy (or the
  balcony railing if there's no tree); relighting calls them back. One lantern off = sunset
  tint, both off = night with stars, moon and a warm balcony glow. Relighting one =
  early-morning tint, both = day. No sun, no "good morning" text.

SPRING GEMS (5)
1. Music: tap the speaker on the bench. Nothing else starts music.
2. Shake: shake a branch.
3. Pots: grow every plant.
4. Butterfly: tap the palette, pick a new petal color (panel closes itself after picking).
5. Nest: the wall-pot visitor.

SUMMER GEMS (5)
- When summer begins, a smaller little sister (pigtails) walks out of the front door,
  facing us with a smiling face while she walks, then turns to face the house and holds
  the girl's left hand for the rest of the year. She dresses for the season: yellow dress
  in summer, orange dress with tights in autumn, red coat with scarf and knit hat in
  winter.
1. Kite: a colorful diamond kite with a bow tail is tangled in the right side of the main
   tree's canopy (the open courtyard side, `placeKite`); shake the tree
   and it rises into the sky on a string held in the girl's raised hand.
2. Sunflower: water a seed mound next to the little pot by the tower; a sunflower grows tall, with a
   bee circling it. It stays for the rest of the year (drooping in autumn, snow on it in
   winter).
3. Friends: tap the blue jar on the bench; its cork pops and three small butterflies fly
   out and follow the cursor (or flit around the girl). They fly away when winter comes.
4. Balloon: pick up the twig and pop the balloon with its tip (a mouse hover never pops
   it; in spring the balloon just bobs away from the twig). "pop!" + shards; the twig
   floats back home slowly; the girl's arm lowers to rest; the balloon does not return.
   Balloon is sky blue so it never matches the butterfly.
5. Ladybug: the wall-pot visitor.

AUTUMN GEMS (5)
1. Leaves: fallen leaves cover the courtyard. Pick up the rake (a held tool); its tines
   stay on the ground and follow the pointer with a little lag and chatter. A small heap of
   leaves already sits at the girl's feet. Sweep any way you like: every leaf the tines
   touch skitters along the stones onto that heap, which visibly grows into a pile. The tines
   also scratch settled petals off the stones. Raking makes a dry scraping sound with leaf
   crunches (when music is on). When most leaves are in, the rest follow, the whole
   courtyard is swept clean, she hops into the pile and leaves burst up; the trees then
   drop only the odd leaf.
2. Umbrella: tap the grey cloud (it has a sleepy face) to make it rain — streaks,
   splashes, a darker grade, pitter-patter sound; then tap the umbrella leaning by the wall
   and it opens in her raised hand, dome up like a real umbrella, tilted over her little
   sister so it keeps them both dry (rain splashes on the canopy). When the rain stops she lowers it and it
   leans by the wall again (and goes back up if it rains again). Tapping the umbrella
   before the rain makes Oli nudge you toward the cloud.
3. Pumpkin: water a patch of soil in front of the small pot; a vine grows and a pumpkin
   swells.
4. Night: turn both lanterns off; Oli hoots and flies one loop around the tree, then lands
   back on the tower.
5. Mouse: the wall-pot visitor.

WINTER GEMS (5)
- Winter opens on a long night: both lanterns are out and their fireflies rest in the bare
  tree. Relighting them brings the day back.
1. Snowman: tap three snowy mounds; each rolls a growing snowball that stacks at the right
   edge of the courtyard. Once all three are stacked his carrot nose pops on by itself (he has coal eyes,
   twig arms and a blue scarf).
2. Hearth: tap the cold chimney; smoke puffs rise and every window glows warmly.
3. Lights: tap the balcony railing; colorful fairy lights string themselves along it and
   twinkle, brighter at night.
4. Name: pick up the chalk from the easel's ledge, tap the board, type a name (DOM input
   over the board), Enter. The name is written on the board in chalk. ?name= in the URL
   pre-fills it, and then this gem lights up by itself a few seconds into winter.
5. Robin: the wall-pot visitor.

HINTS
- A small feather roams the garden on a gentle path. It never hints right away. After a
  random 18–48 s without a discovery (and a few seconds idle), it flies to the next gem's
  location for 10 s (or to the tool that gem needs first).
- A cute pink alarm clock stands on the ground at the bottom-right of the house: a gold
  wedge and a single hand sweep down to zero, with a small seconds number; it rings and
  wobbles when the hint arrives. Tapping it rings the hint early.
- Coco, a cute puppy with perky ears (folded tips that wiggle the whole time he is out
  and flick as he pops up), peeks from behind the casa every 25–40 s (over the chimney, over
  the roof ridge, around the tower, or around the far corner above the clock), stays about
  5 s, then ducks back. He says a soft "woof woof" each time he pops up
  (even before the music is on). The first time, Oli whispers that someone is peeking. Tapping him
  woofs again, he pants happily, and he sniffs out every gem still hidden this season, one every ~1.3 s, doing each gem's own action
  where possible, so the season can finish.

ENDING
- After the last winter gem: "Happy Birthday," and the name on a second line come
  out of the chimney letter by letter. Each letter puffs out with a little smoke, starts
  small and tilted, and floats up and over to its place in the line, in a script font
  with a pink-to-orange gradient. At the same time colorful balloons on thin strings
  squeeze out of the chimney (small at first, growing as they come out), about one every
  0.4 s for the first 7 s and then now and then, drifting out to either side of the words
  and floating up and away with a gentle sway (`partyBalloons`, drawn behind the letters).
  Floating hearts follow, while Oli says "Every season she
  grew a little more, just like our tree." It fades after ~22 s and the snowy garden stays
  calm. The finished message sits just below the title, clear of it.

TITLE
- On load, "Casa de Gemas" in a script font with "a little garden of hidden gems" under
  it fades in at the top center (with padding so the swashes aren't clipped) and stays
  there for the whole game. On short screens (phones in landscape) it is smaller and sits
  in the top-right corner, clear of the house.

SOUND (Web Audio, all generated, silent until the speaker is tapped, except the puppy's woof)
- Gentle Andalusian cadence Am–G–F–E: soft pads, plucked notes, chimes, convolution
  reverb. Petal-flutter notes only while your hand is shaking a branch (short notes that
  fade within ~0.6 s of letting go — never loop), water pour and rain, pop, owl hoots,
  lantern chimes. Build the audio engine silently on the first tap and resume it on touchend so
  iOS allows sound.

TOUCH
- Works with fingers: taps snap to the nearest interactive thing within fingertip reach
  (including every seasonal object), bigger branch/balloon hit areas, no double-tap zoom,
  no text selection, no stuck hover glows. Keep interactive objects inside the phone crop.
- On phones the garden opens zoomed in to a finger-friendly size in either orientation:
  drag on the garden to look around, pinch to zoom, and hints and the finale glide the
  view to where to look. The finger never hides what it moves: the butterfly sits just
  above the fingertip, the watering can pours just above it, and the twig, rake and chalk
  ride above it too. Taps and put-downs still land under the finger. Carrying a tool to
  the screen edge pans that way. Oli's bubble stays readable and on screen.

KEYS: Esc drops the held tool, M toggles music, R starts the year over from spring.
```

[Where the creator shared it](https://github.com/deepujain/casadegema/blob/main/SKILL.md#the-full-prompt)

<sub>The game and its prompt belong to @deepujain. Preview recorded by us. [Ask for a change or removal](https://github.com/evorjh/awesome-games-made-with-ai/issues/new?template=change-or-removal.yml).</sub>
