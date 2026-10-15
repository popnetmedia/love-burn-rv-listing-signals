# Method

## Scope

Every Outdoorsy listing returned by Outdoorsy's search within 50 miles of Virginia Key (25.7365,
-80.1548) on 2026-10-01, in the RV types Class A, Class B, Class C, travel trailer, fifth wheel,
camper van, folding trailer and toy hauler (utility trailers excluded). The search reported 209
listings and returned 209. 207 carry a read of the owner's text and are counted here; the read is
kept only for listings that were judged, so the other 2 have no answers and are left out of every
count.

## What was read

Two kinds of field, kept apart:

1. **Structured fields, copied as published.** Whether the host ticked the festival friendly box,
   the Burning Man friendly box, listed vehicle length, fresh, grey and black tank sizes, generator,
   solar and host delivery. No model touches these. A tank size of zero or none is counted as blank.
2. **The owner's own text,** meaning the listing's name, description and house rules, read by a
   language model (TypeSafe System One, `jev-1.13.0`) against five fixed questions:
   - `festival`: does the text allow festival or event use, allow it only with approval, a fee or a
     deposit, prohibit it, or not address it? A ban on a narrower thing, such as parties inside the
     RV, is not a festival ban.
   - `needsHookups`: does the text say the RV needs shore power, water or sewer hookups to work?
   - `campgroundOnly`: does it require overnight stays at a campground with hookups, or forbid dry
     camping?
   - `loveBurn`: does it name The Love Burn, Luv Burn or Virginia Key?
   - `eventDeposit`: does it state an extra fee or deposit for festival or event use?

   The model returns probabilities, not verdicts. The questions are fingerprinted (`questionsHash`
   `e38c7c811301`); changing their wording forces every listing to be read again.

A listing's text is read again only when the text or the questions change. The 2026-10-01 pull
re-copied every structured field and found every owner's text unchanged, so every text answer in
this set dates from 2026-09-22. That is why `meta.owner_text_read_on` differs from `measured_on`.

## Thresholds

The same thresholds loveburnrentals.com uses on each listing card, so a count here never disagrees
with the site:

- A festival answer is used only when the model puts 0.6 or more on it. Below that it counts as
  `silent`.
- A yes/no answer counts as yes at 0.8 or more.
- Each listing gets one status, in this order: `ruled out` (prohibits festivals, needs hookups, or
  requires a campground), `ask first` (approval, fee or deposit), `names Love Burn`, `welcome`
  (allows festival use), `not stated` (everything else).

This is why 84 ticked listings have a `silent` festival answer and 82 are `not stated`: of the 84,
one names The Love Burn and one says it needs hookups.

## Length brackets

The event's RV pass prices, as its ticket page reads on 2026-10-15: "Oversized Vehicles and RVs
under 24 feet: $195 plus tax and fees", "25 to 39 feet: $295 plus tax and fees", "longer than 40
feet: $395 plus tax and fees". Listed lengths from 24 ft up to 25 ft, and over 39 ft up to 40 ft,
are counted in their own rows because that wording places neither. The page may still describe the
2026 event; re-read it for the 2027 brackets. A listed length is the host's figure, not a
measurement.

## Privacy

No listing id, URL, host name, owner text or quotation is in this set, and no cell is finer than a
whole status or a length bracket. Individual Outdoorsy hosts are private individuals and their
listings change after any read, so the set publishes counts only.

## Limits

- A model's reading of text can be wrong. This set does not record a hand check of each judgment.
- `not stated` means the owner's text does not address festivals. It is not a refusal.
- What Outdoorsy's festival friendly box commits a host to is not stated in the listing data, and
  this set does not say.

## Columns

| Column | Meaning |
|---|---|
| `section` | Which count: which box was ticked; the status the owner's text earns; the raw festival answer; the yes/no flags; length by pass bracket; tank sizes; power and delivery |
| `population` | `all listings` (207), `box ticked` (93, either box), `box not ticked` (114), or `box ticked, rules not stated` (82) |
| `category` | The value counted |
| `value` | The count, or for a median the number in `unit` |
| `unit` | `listings` or `gallons` |
| `population_size` | The denominator |
| `measured_on` | Date the listings were pulled |
