#### Concerns - Flipper cannot be held

The game will kill power to the flippers if one is held for more than about 1 minute. There are no known workarounds so it is not well suited for competition where a player may need to hold a ball to wait for a TD to make a ruling.

#### Custom ROM
Custom ROM's
https://www.vpforums.org/index.php?showtopic=59938

# Jolly Park ROM MOD
**Flipper shutdown removed; locked balls protected during early ball-search rounds**

## Tournament Notes

Ball search remains enabled but takes considerably longer to activate than in the original game.

The first five ball-search rounds are modified to preserve locked balls. Beginning with the sixth round, the normal ball-release/chase-ball behavior may occur.

This MOD also removes the original flipper shutdown behavior associated with repeated ball-search timeouts. Flipper control remains available during ball search.

Players must not deliberately induce ball searches or manipulate ball trapping to obtain an unintended chase-ball release or multiball. Normal player-controlled trapping during ordinary gameplay remains permitted under the applicable tournament rules.

## ROM Changes
- Removed the third-timeout lockout that killed the flippers until the ball drained.
  Ball search now just keeps retrying.
- Removed the flipper-enable drop just before the ball-search timeout.
- The first 5 ball-search rounds do not pulse any coils and do not clear the lock counts,
  so locked balls stay locked. From the 6th round on, ball search behaves as in the stock ROM.
- Ball-search timeout raised from 16 s to 60 s (76 s at the start of a ball).
- A multiball start no longer shortens an active new ticket (ball saver) timer. It used to
  overwrite it with the multiball repeat time, which is only 5 ticks when that dip is Disabled.
- The ball-saver timers (new ticket / new travel, and the multiball saver) no longer count down while a
  ball is sitting in the shooter lane. They start counting once the ball leaves it.
