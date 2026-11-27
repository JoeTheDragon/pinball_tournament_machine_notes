#### Concerns - Flipper cannot be held

The game will kill power to the flippers if one is held for more than about 1 minute. There are custom roms (yet to be tested on real hardware) to fix it. So with out them it is not well suited for competition where a player may need to hold a ball to wait for a TD to make a ruling.


#### Custom ROM
Custom ROM's
https://www.vpforums.org/index.php?showtopic=59938

# Verne's World ROM MOD
**Flipper shutdown removed; locked balls protected during early ball-search rounds**

## Tournament Notes

Ball search remains enabled but takes considerably longer to activate than in the original game.

The first five ball-search rounds are modified to preserve locked balls. Beginning with the sixth round, the normal ball-release/chase-ball behavior may occur.

This MOD also removes the original flipper shutdown behavior associated with repeated ball-search timeouts. Flipper control remains available during ball search.

Players must not deliberately induce ball searches or manipulate ball trapping to obtain an unintended chase-ball release or multiball. Normal player-controlled trapping during ordinary gameplay remains permitted under the applicable tournament rules.

## ROM Changes

Changes to the supplied MOD in `vwmcpu0.rom` and `vwmcpu1.rom`:

- **Removed the third-timeout flipper lockout.** The original behavior killed the flippers until the ball drained. Ball search now continues retrying without this lockout.
- **Removed the pre-timeout flipper shutdown.** Flipper enable is no longer dropped immediately before the ball-search timeout.
- **Protected locks during the first five ball-search rounds.** These rounds no longer:
  - Pulse coils 6 (octopus release), 7, 13 (volcano elevator), or 20.
  - Start the balloon motor (coil 23).
  - Clear the lock counts.
  
  This prevents the early ball-search rounds from activating the lock-release mechanisms or clearing their counts. Beginning with the sixth round, ball search follows the base MOD's behavior, including its normal lock-release/chase-ball sequence.

The base MOD's 60-second / 76-second no-switch timeout and all its other changes are retained.

## Changes Inherited from the Base MOD

This ROM builds on the changes described in the [original MOD discussion](https://github.com/vpinball/pinmame/pull/845#issuecomment-7048748818).

- **Extra ball on a slow serve:** Both serve routines previously fired the trough eject again when a ball was slow to reach the shooter lane, potentially putting an extra ball into play. They now fire again only if the ball is still detected in the trough.
- **Extended no-switch timeout:** Increased from 16 seconds to 60 seconds (76 seconds instead of 32 seconds at game start). The original timeout could initiate ball search too quickly, releasing locked balls and clearing lock counts.
- **Persistent last-game scores:** The previous game's scores are displayed in the attract-mode rotation and retained across power cycles.
- **Final scores held until START:** After game over, final scores remain displayed with a PRESS START prompt. Pressing START returns to attract mode without immediately starting another game. START input is debounced, and coins continue to be accepted.
- **Cold-start recovery:** When NVRAM is empty, the original game writes factory defaults and then halts with a dark display until manually reset. The MOD automatically restarts the boot process and enters attract mode.