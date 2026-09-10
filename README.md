# giodauongvietroulette

Vietnamese drink case-opening parody. 36 drinks, budget and no-caffeine filters, in-browser synthesized sound (no mirrored game assets), Google Maps + GrabFood search for the chosen drink. No payments or backend records.

## Timing reference

Mirrors the archived CS:GO Panorama client's case-opening timing: a 2.3 s lead-in plus 0.1 s scroll preparation, a 6 s scroll, `cubic-bezier(0.075, 0.82, 0.165, 1)`, and a randomized landing offset from 10–90% of the winning tile. The winner is selected **before** the animation starts; decorative tiles never determine the result, and neighboring tiles avoid same-tier repeats to reduce high-speed visual aliasing.

Reduced-motion mode keeps the same total timing but suppresses reel movement (fades the result in instead of scrolling).

## Rarity system

The 625:125:25:5:2 tier weight ratio reproduces the published standard weapon-case tier ratio, re-purposed for drink pricing tiers instead of item rarity:

| Tier | Weight | Odds | Giá tham khảo |
|---|---|---|---|
| Xanh (blue) | 625 | 62.5% | ≤ 20.000đ |
| Tím (purple) | 125 | 12.5% | ≤ 25.000đ |
| Hồng (pink) | 25 | 2.5% | ≤ 40.000đ |
| Đỏ (red) | 5 | 0.5% | ≤ 65.000đ |
| Vàng (gold) | 2 | 0.2% | > 65.000đ |

Items within a tier have equal probability. Filters (budget, no-caffeine) remove unavailable items and renormalize the remaining weights within each surviving tier — if a whole tier has no items left after filtering, its weight mass is dropped entirely rather than redistributed.

## Assets

No external game assets are used. Drink icons are emoji; the "pop" sound on reveal is synthesized in-browser with the Web Audio API (a short sine-wave chirp), so there is nothing to license or mirror.

## Find or order the chosen drink

The result links to Google Maps search for the drink name near the user. A GrabFood search link is also offered. There is no forced timer redirect, no location request beyond what the browser/Maps link itself triggers, and no checkout integration.

## Development

This is a single static file with no build step:

```
open index.html
```

or serve it locally:

```
npx serve .
```

## Disclaimer

This is a browser-only parody of a case-opening mechanic, not Valve's engine, code, or backend, and is not affiliated with Valve or CS:GO. It is also not affiliated with any drink vendor, GrabFood, or Google. Drink names, prices, and tiers are illustrative reference values, not live pricing. Inspired by the meal-roulette project [truanayangi](https://github.com/nagisanzenin/truanayangi).

## About

CS:GO-style drink roulette for Vietnam.

Mở hòm, chốt ly nước.
