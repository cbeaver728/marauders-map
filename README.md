# The Marauder's Map

A living plan of Hogwarts Castle, drawn in ink on parchment, with everybody presently
walking about in it.

**Live:** https://cbeaver728.github.io/marauders-map/

One self-contained HTML file. No build step, no dependencies, no server — open
`index.html` in any browser, or visit the link above on a phone.

---

## What it does

Eight levels of the castle, each drawn procedurally on a canvas: hand-jittered wall
lines, double-line corridors with doorway gaps, fold creases, foxing stains and a
scorched torn edge. Rooms are furnished — four house tables in the Great Hall, cauldrons
in Potions, tombs in the Old Crypt, the Mirror of Erised in a disused third-floor
classroom, hoops on the Quidditch pitch.

Around seventy inhabitants walk it in real time. The castle is a graph of rooms and
corridors, so people genuinely path from where they are to where they are going, taking
staircases between floors, leaving footprints that ink in and fade over about six
seconds. Prints differ by who is walking: school shoes for the human beings, cat paws,
hippogriff claws, centaur hooves, dotted ghost soles, a serpent's slither trail.

### Levels

Grounds · Dungeons · Ground Floor · First · Second · Third · Fifth · Seventh and Towers

### Timetables

Everyone runs on **US Central Time**, shown in the clock at the top right.

| Time | Where people are |
| --- | --- |
| 07:00–08:00 | Breakfast in the Great Hall |
| 09:00–12:00 | Lessons — Potions, Transfiguration, Charms, Defence, Herbology, History |
| 12:00–13:00 | Luncheon in the Great Hall |
| 13:00–17:00 | Lessons |
| 17:00–19:00 | Courtyards, the lake, the library, then dinner |
| 19:00–23:00 | Common rooms and the library |
| 23:00–06:00 | Dormitories — and Filch and Mrs Norris patrolling the corridors |

Weekends move people onto the grounds, the lake and the road to Hogsmeade. Staff keep
their own hours: Snape teaches Potions and haunts his office and the store rooms,
Hagrid goes into the Forest after dark, Madam Pince never really leaves the library.
Everyone re-rolls their position each time the page is opened.

## Controls

| | |
| --- | --- |
| Move about | drag, or arrow keys |
| Look closer | pinch, scroll, or `+` / `-` |
| Change floor | the tabs down the right edge, or keys `1`–`8` |
| Identify someone | tap their name |
| Find someone | the search box, bottom left |
| Put it away | *Mischief Managed* |

## Things worth finding

- Tap the title three times for Messrs Moony, Wormtail, Padfoot and Prongs' compliments
  to Professor Snape.
- Rare cameos, each with its own odds: Peter Pettigrew in Gryffindor Tower, Padfoot on
  the grounds after dark, Tom Riddle near the Chamber entrance, Bartemius Crouch Jr,
  R.A.B. in the dungeons, Nicolas Flamel at the front gates. Tap one to find out why the
  map should not be showing it.
- The Room of Requirement appears only about half the time.
- Astronomy really is taught at midnight on Wednesdays. Look at the tower then.
- The moon phase is calculated from the real date. On a full moon at night, Professor
  Lupin goes to the Shrieking Shack — the passage under the Whomping Willow is on the map.
- The One-Eyed Witch connects to the road to Hogsmeade, by way of a cellar.
- Trevor is lost somewhere different every time.
- **Tap a room**, not just a person. Around fifty of them have something to say: the
  Great Hall's ceiling shows the real sky for the hour, the gargoyle gives today's
  password, the Fat Lady gives this week's, the Astronomy Tower reports the actual moon
  phase, the Entrance Hall tallies house points. Don't tap the Whomping Willow.
- **The Golden Snitch** darts about the Quidditch pitch, and now and then slips off to
  wander another floor. It is very small. Tap it to catch it.
- **Peeves** leaves ink behind him — CRASH!, Wheee! — and people mutter to themselves as
  they walk. Errol occasionally lands. Badly.
- Rarer faces: Lockhart, Umbridge, Quirrell (look at him closely), Krum and Fleur down by
  the lake, Tonks, Madam Rosmerta on the Hogsmeade road, the owls, and — after dark —
  Dementors at the gates, who leave no footprints at all.
- **Dates the castle remembers**, in Central Time: thirteen birthdays (look for a star
  over the ribbon), the first of April (the twins swap names), Hallowe'en (troll in the
  dungeons; Nick's Deathday party in the crypt), the first of September, Valentine's Day,
  the second of May, and Christmas.

### Spells

Type one into the search box and press Enter.

| | |
| --- | --- |
| *Lumos* / *Nox* | Bring the lamps up, or go dark with only your wand for light |
| *Homenum Revelio* | Reveal everyone on the floor, and count them |
| *Alohomora* | Light up the secret passages and hidden rooms |
| *Accio* + a name | Fly to them. *Accio Snitch* works too |
| *Expecto Patronum* | Send a silver stag across the floor |
| *Wingardium Leviosa* | Float every name |
| *Riddikulus* | Give the boggarts their makeovers |
| *Petrificus Totalus* | Freeze the whole castle |
| *Obliviate* | Forget every footprint |
| *Finite Incantatem* | End them all |

The Unforgivable Curses are recognised. They are not rewarded.

## Technical notes

Everything is one canvas. Static geometry for each floor is baked once into a handful of
`Path2D` objects grouped by line weight, so a frame is a few stroke calls rather than
thousands. Room labels and name banners are drawn in screen space with greedy
decluttering, so they stay legible at any zoom. Movement uses Dijkstra over a room graph
with staircase edges joining the levels; paths are cached. The only external resource is
the Google Fonts stylesheet for IM Fell English — a genuine seventeenth-century punchcut,
and the closest thing to the lettering in the films.

---

*Mischief managed.*
