```
TrinketMenu 3.41

This is a mod to make swapping trinkets easier.  It will display your two equipped trinkets in a bar.  Mouseover on either trinket will display a menu of up to 30 trinkets in your bags to swap.

__ New in 3.41 __
- /trinket reset will work properly again
- /trinket load top|bottom profilename can set profiles in macros
- nil error fix if TrinketMenuQueue.* deleted
- Options window shrinks if TrinketMenuQueue.* deleted
__ New in 3.4 __
- Auto queue profiles to save/load trinket priority sets
- Trinkets can be removed from list

__ Swapping/Using trinkets __

Left click a trinket in the menu to equip it to the top trinket slot.
Right click a trinket in the menu to equip it to the bottom trinket slot.

Left or Right click either equipped trinket to use them.  Or make a key binding for either trinket.

__ Auto Queue __

3.0 introduces auto trinket queues to TrinketMenu.  In options you can sort a trinket slot to the order you want trinkets equipped, turn on Auto Queue for that slot (Alt+Click the trinket on the bar or check the tab in options), and the mod will automatically swap trinkets as they're used and come off cooldown.

It was (hopefully) made to be intuitive enough to use without instructions, but if wondering about specifics:

The auto queue rules are:
- A trinket at 30 seconds or less cooldown is considered off cooldown.
- If the currently equipped trinket is on cooldown, swap to the first available trinket not on cooldown.
- If the currently equipped trinket cannot go on cooldown (passive trinkets), equip a higher ranking trinket when it comes off cooldown.
- If the currently equipped trinket is ready for use, then do nothing unless a higher-ranked trinket marked 'Priority' is waiting to swap in.
- If a trinket has a 'Delay' defined, then hold that trinket for its delay before swapping it out. (ie, Earthstrike for 20 seconds)

Auto queue icon colors:
- A gold gear on a trinket means that auto queue is active for that slot.
- A grey gear on a trinket means the equipped trinket has a delay defined and is waiting to swap out.
- A red gear on a trinket means the equipped trinket is flagged 'Pause Queue' and auto queue is suspended.

Other auto queue notes:
- If you use some mod to automatically swap in passive trinkets (Carrot on a Stick or Argent Dawn Commission), flag those trinkets 'Pause Queue' to suspend the queue while they're equipped.
- Swapping a passive trinket manually in TrinketMenu will stop the auto queue for that slot.  Alt+click the slot to turn auto queue back on.
- A purely passive trinket will mark the natural end of a queue.  If you would like the queue to stop sooner (ie, Burst of Knowledge as bottom-most trinket even on cooldown), move the "-- stop queue here--" mark to where you want the queue to stop.
- The auto queues work independently of the "trinket ready!" notifications.
- Trinkets attempting to swap during combat or while dead will queue for when you drop out of combat or return to life.
- If you don't want to use auto queue and would like to remove it completely, you can delete TrinketMenuQueue.xml and TrinketMenuQueue.lua while out of game.  The remaining mod will be about the size of TrinketMenu 2.7 and run better than 2.7.

__ Auto Queue Shared Timers __

Keep in mind as you set up your queues that many trinkets trigger shared cooldown timers.  As an example:

Trinket 0 contains a Cannonball Runner not on cooldown
Trinket 1 contains a Diamond Flask not on cooldown

When you click Diamond Flask, it will put the Cannonball Runner into a 60-second cooldown.  TrinketMenu will then look for something more available for Trinket 0, and then 30 seconds later as the Cannonball Runner comes off cooldown it will swap it back in.

This is expected behavior.  If it seems like this happens a lot, you may want to Auto Queue only one trinket slot, until you get trinkets that can be used without triggering the other's cooldown.

__ Customizing Display __

The main and menu windows are independently scalable and rotatable.  While the windows are unlocked:

- Move either window by dragging its edge.
- Rotate either window by right-clicking its edge.
- Scale/resize either window by dragging the lower-right corner to the desired size.

If you're having problems grabbing the edge of the menu window to move/rotate/resize it, hold Shift down while it's open and the menu won't go away when the mouse leaves the menu's edge.

If you right-click the gear icon around the minimap (or /trinket options) a small options window will appear under the minimap.  Here you can customize the display further by showing cooldowns as numbers and keeping the menu always open.

Once you're settled on a setup you like, you can lock the windows in options.

To set an exact scale (optional):
/trinket scale main n : Scale the main window to n
/trinket scale menu n : Scale the menu window to n
ie: /trinket scale menu 0.85

__ Docking __

While 'Keep Menu Docked' is checked (default), the menu will always be docked to one corner of the main window.  To change the corner where it's docked, drag the menu window so that a corner of the main and menu windows meet.  White brackets will appear at the corners that will dock as you drag.

If you uncheck 'Keep Menu Docked', remember the menu goes away when the mouse leaves your trinkets.  Feel free to experiment if you'd like.  Remember that /trinket reset will restore positions/docking, or you can hold Shift down to keep the menu open.  Or you can turn on 'Keep Menu Open' in options.

__ Combat/Death Queued Trinkets __

We can't swap trinkets during combat or when we're dead.  If you attempt to swap trinkets during combat or while dead it will put the trinket on hold and automatically swap them once you leave combat:

- The queued trinket will appear as a small icon inset into the slot it's heading to.
- If you want to unqueue the trinket, reselect it again for that slot (left or right click).
- If you want to queue the trinket to the other slot, reselect it again for the other slot (left or right click).
- The "combat queue" is only one-trinket deep right now.  Meaning, once a queued trinket is equipped that queue is emptied.
- Selecting a series of trinkets for a slot will only change the queued trinket, it won't set up an order to them.  Go to options to set up an auto queue sort order.

__ Misc __

- If you hold shift while you move trinkets up/down the sort list, the list will stay in place.
- You can drag the minimap icon around the minimap directly.
- You can Shift+click the trinkets to link them to chats just as you would from your bags or inventory.
- If you log in to a character with no trinkets in bags or on their person, the trinket window will not be displayed.
- You can hold Shift while swapping trinkets or manipulating the windows to prevent the menu from disappearing.
- You can set up key bindings to use whatever trinket is in the top or bottom slot.
- If you have Scrolling Combat Text installed, and 'Notify When Ready' checked, it will send a message via SCT when a trinket is ready.

__ Optional Slash Commands __

/trinket or /trinketmenu : toggle the window
/trinket reset : reset window
/trinket opt : summons options window
/trinket lock|unlock : toggles window lock
/trinket scale main|menu n : scales windows to exact scale
/trinket help : lists the above commands

__ TrinketMenu.SetQueue (Advanced Users) __

This function is intended to be used by those that want to script different sort orders or script the auto queue behavior to work with other gear-swapping mods.

TrinketMenu.SetQueue(0 or 1,"ON" or "OFF" or "PAUSE" or "RESUME" or list)

"ON" : Turn queue on irregardless of previous state
"OFF" : Turn queue off irregardless of previous state
"PAUSE" : Suspend queue if it was on
"RESUME" : Return queue to normal operation if it was paused

some examples:
/script TrinketMenu.SetQueue(1,"PAUSE") -- if queue is going, pause it
/script TrinketMenu.SetQueue(1,"RESUME") -- if queue is paused, resume it
/script TrinketMenu.SetQueue(1,"SORT","Earthstrike","Insignia of the Alliance","Diamond Flask") -- set sort
/script TrinketMenu.SetQUeue(0,"SORT","Lifestone","Darkmoon Card: Heroism") -- set sort and turn queue on
(a "stop the queue" is assumed at the end of the list)

So in ItemRack if you want a different queue when in a raid or not:

name: In Raid
trigger: RAID_ROSTER_UPDATE
delay: 0.5
script:
if GetNumRaidMembers()>0 and not IR_INRAID then
  IR_INRAID = 1
  TrinketMenu.SetQueue(1,"SORT","Zandalarian Hero Badge","Force of Will")
elseif IR_INRAID and GetNumRaidMembers()==0 then
  IR_INRAID = nil
  TrinketMenu.SetQueue(1,"SORT","Earthstrike","Diamond Flask","Defender of the Timbermaw")
end
--[[ Changes trinket sort orders depending on whether in a raid or not ]]

or for some situation when you don't want trinkets swapping at all:

name: In IF
trigger: ZONE_CHANGED_NEW_AREA
delay: 2
script:
if GetRealZoneText()=="Ironforge" and not IR_INIF then
  IR_INIF = 1
  TrinketMenu.SetQueue(0,"PAUSE")
elseif IR_INIF and GetRealZoneText()~="Ironforge" then
  IR_INIF = nil
  TrinketMenu.SetQueue(0,"RESUME")
end
--[[ Pauses trinket slot 0 auto queue while in IF ]]
```
