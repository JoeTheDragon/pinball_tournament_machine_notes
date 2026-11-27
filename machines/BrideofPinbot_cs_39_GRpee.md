The general idea is to set up the wheel to your specifications and (hopefully) avoid bad things

| Menu | Adj. | Name | Value |
| ---- | ---- | ---- | ---- |
| A.2 | 01 | Extra Ball Percentage | as low as possible |
| A.2 | 02 | Extra Ball Lit Off Wheel Percentage | as low as possible |
| A.2 | 03 | Jackpot Lit Off Wheel Percentage | at your discretion |
| A.2 | 04 | Big Wheel 1 Million | at your discretion |
| A.2 | 05 | Big Wheel 10 Million | at your discretion |
| A.2 | 06 | Big Wheel 50 Million | at your discretion |
| A.2 | 07 | Big Wheel Lit Billion | **as low as possible** |
| A.2 | 08 | Special Percentage | as low as possible |
| ... | ... | | |
| A.2 | 12 | Jackpot Time Out Rate | if you want Jackpots or not |
| A.2 | 13 | Billion Lit Time Down | **as low as possible** |
| A.2 | 14 | Consolation Extra Ball Time | Set to 0 to disable |
| ... | ... | | |
| A.2 | 20 | Enter Mini Playfield (Pinbot) | can be set to HARD to make multiball harder to get to |

Billion Lit Time Down on its lowest setting generally makes it physically impossible to collect the billion point shot.

These recommended settings was suggested by ScoutPilgrim

#### Custom ROM
Custom ROM's
https://www.vpforums.org/index.php?showtopic=59938

Extra balls (all modes)
- Light Extra Ball can now light even when extra balls are off (MAX E.B. COUNT = 0)
  or at the limit. This applies to the small wheel, the loop and the Pinbot sources.
- Collecting a lit extra ball while extra balls are off / at the limit does not award
  an extra ball (the lit extra ball is used up, nothing is added).
- Small wheel (tournament off): when extra balls are unavailable, only the Extra Ball
  result is skipped; Light Extra Ball is still allowed.

Tournament mode works now 

Small wheel: no randomness and the percentage settings are ignored. Each player has
their own position in a fixed sequence of results:
Light Jackpot, 1, 4, 5,  Light Jackpot, 1, 4, 5,  Extra Ball, Light Extra Ball
(wheel results 1, 4 and 5 are the other small wheel awards). The Extra Ball and Light
Extra Ball results only come up after two trips through the loop. Extra Ball is
skipped when extra balls are off or at the limit, and Light Jackpot is skipped while the
jackpot is already lit. Light Extra Ball is never skipped.
- Big wheel: no randomness and the percentage settings are ignored. Each player has
  their own position in a fixed sequence:
  1 MILLION, 10 MILLION, 50 MILLION, special, remaining result 4, LIGHT 1 BILLION (last)
  Wheel results go through the game's own award code, so lamps/flags such as the
  billion-lit flag are set exactly as in stock.
- Each player's wheel positions are reset at the start of every game, both when the game
  starts and again when player 1 starts ball 1.
- Jackpot: kept per player (including growth: in L8 it adds to all four players'
  jackpots) and reset at the start of a game, now starting at 1 MILLION (was 8 million
  in L8). The jackpot still resets to 1 million after it is collected.