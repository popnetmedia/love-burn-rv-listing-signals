# Love Burn RV listing signals

What Outdoorsy's festival friendly box says about an RV, set against what the owner's own written
rules say, for every Outdoorsy RV listed within 50 miles of Virginia Key, Miami, on 1 October 2026:
207 listings, counted by box, by what the owner's text says, by listed length against the event's RV
pass brackets, and by tank size, power and delivery. Counts only. No listing, host or owner text is
in this set.

Compiled by Love Burn Rentals, a finder for Outdoorsy RVs near Virginia Key. Listings pulled
2026-10-01; owner text read 2026-09-22 and unchanged on 2026-10-01 (see `METHOD.md`).

## What it shows

- **93 of the 207 listings had a festival friendly or Burning Man friendly box ticked, and in 82 of
  those 93 the owner's own description and house rules say nothing about festivals either way.**
  The box is a yes/no field on the listing. It carries no words, no conditions and no event rules.
- **None of the 93 ticked owners bans festivals in writing**, so the box is not contradicted. It is
  unsupported: 6 of the 93 owners write that festival use is welcome, 3 name The Love Burn, 1 asks
  for approval or an extra charge first, and 1 writes that the RV needs hookups, which rules it out
  on a key with none.
- **The length brackets leave gaps.** The event's page prices RV passes for "under 24 feet", "25 to
  39 feet" and "longer than 40 feet". Of the 82 ticked listings with no written festival rule, 6 list
  a length from 24 ft up to 25 ft and 1 lists a length over 39 ft up to 40 ft; that wording places
  neither.
- **30 of the same 82 leave the fresh water tank size blank.** Where it is listed (52), the median
  is 40 gallons.

What this means for a renter: treat the box as silence. Get the owner's yes for festival use, in
writing on Outdoorsy, along with the measured length, tank sizes and power, before you book.

## Files

| File | What it is |
|---|---|
| `data/listing-signals.csv` | 99 rows, one count each, 7 columns (described in `METHOD.md`) |
| `data/listing-signals.json` | The same rows, plus a `meta` block with dates, model, thresholds and licence |
| `METHOD.md` | How listings were pulled, how the owner text was read, the thresholds, what is left out |
| `SOURCES.md` | Every source with its date |

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Reuse it, with credit. The listing
fields are Outdoorsy's and its hosts'; this set is an aggregate count of them.

## How to cite

> Love Burn Rentals (2026). *Love Burn RV listing signals* [Data set]. Listings pulled 1 October
> 2026. https://github.com/popnetmedia/love-burn-rv-listing-signals. See also
> https://loveburnrentals.com/rv-rentals.

## Before you rely on a count

Listings change daily and owners edit their rules. Every count carries the date it was measured. The
"what the owner's text says" counts are a model's reading of the text against fixed questions, with
the thresholds in `METHOD.md`; read the listing yourself and ask the owner before you book.

## Corrections

Open an issue with the count you believe is wrong and why. No correction can name a listing or a
host, because this set holds none.

Love Burn Rentals owns no RVs and takes no bookings, and is not affiliated with The Love Burn,
Outdoorsy or any host. You book with the host on Outdoorsy.
