```
__ FAQ for 3.x __

Q: Why did you remove the "missing trinket" bit?
A: Because it wasn't always accurate and to make it more accurate would require more bag scanning than is necessary for the mod to function.  Specifically: when a series of BAG_UPDATEs occur, it waits until they're done and then quickly scans only the bags that updated.  When it finds a trinket it notes its position.  If a trinket disappeared it doesn't care because it's not going to show in the menu.  I am hyper-sensitive to BAG_UPDATE performance and don't want to spend more CPU cycles than is necessary in normal BAG_UPDATE actions. (You may note that if you remove the TrinketMenuQueue.* files then BAG_UPDATE isn't registered at all)

Q: Can you let the auto queue remain enabled when I swap in passive trinkets?
A: At some point, you will have to tell the mod that you no longer want to use the passive trinket.  Alt+clicking the slot seems simplest.

Q: Can you make auto queue stop/start with my trinket-swapping mod/macro?
A: There are numerous ways of equipping trinkets: UseContainerItem, UseAction, PickupContainerItem/PickupInventoryItem, EquipCursorItem, etc.  I don't want to hook all those functions.  I want this mod to be small and unobtrusive.  Check 'Pause Queue' on trinkets your mod/macro equips, or use TrinketMenu.SetQueue in the macro or event that does the swap.

Q: You said you'd never add full queues to this.  Why the change?
A: Mostly it was to work out some design problems for ItemRack that will have queues for equippable and consumable items.  I needed to back up to a simpler level and adding queues to TrinketMenu was a logical place to work them out.

Q: One reason I used TrinketMenu was because it wasn't bloated with bells and whistles.  Will you release a version without the Auto Queues?
A: If you delete TrinketMenuQueue.xml and TrinketMenuQueue.lua then it will remove the Auto Queue and all the frames and code associated with it.  What's left will be about the same size as 2.7 TrinketMenu.  If there's demand I can post a zip with those files removed.

Q: Does this mean you're not working on ItemRack?
A: See above.  Work is progressing.  Some design issues needed sorted out and this mod's update was a helpful part of that.

Q: Why a rewrite?
A: I'm hoping to keep this mod tidy with as little feature creep as possible.  Rewrites are a good way to trim out unnecessary junk.

Q: I set the menu columns to X, but it's doing X rows and the wrong number of columns.
A: Rotate the menu by right-clicking its unlocked edge.  Then rows will become columns and vice versa.

Q: I made Trinket A higher priority than Trinket B, but when Trinket A comes off cooldown it's not equipping.
A: The default behavior is to not swap trinkets if the currently-equipped trinket is clickable and not on cooldown.  This is to prevent the trinket slots excessively swapping and spending a lot of time in 30-second cooldowns.  If you have a trinket you want equipped ASAP when it's ready, select it and check 'Priority' at the bottom.

__ FAQ __

Q: How do I equip a trinket to the "off" trinket slot?
A: Left click goes to main trinket slot, right click goes to off slot.

Q: Can you add items other than trinkets to the menu?
A: See ItemRack, which is the big brother to this mod.  It handles all inventory slots as well as item sets and stuff.

Q: What does ItemRack mean for TrinketMenu's future?
A: TrinketMenu will stay focused on trinkets.  For the foreseeable future it will be maintained alongside ItemRack since many are looking for just a trinket manager without the extras.  While some new stuff may be added from time to time, any larger changes would probably happen in ItemRack.  TrinketMenu will be kept small and focused.

Q: Localization?
A: This mod should work on all clients.  I can't test this for myself but many report it works fine.

Q: I changed my notify settings on my warrior, but the change shows on my other characters also.
A: Everything in the options window saves for all characters.  Just position, orientation, docking and scaling are saved per-character.

Q: I'd like to go back to using global position/orientation/docking for all my characters.  Can I do this?
A: Sure.  Edit TrinketMenu.toc and change these two lines to the one that follows:

Change:
## SavedVariables: TrinketMenuOptions
## SavedVariablesPerCharacter: TrinketMenuPerOptions

To:
## SavedVariables: TrinketMenuOptions, TrinketMenuPerOptions

To change all settings (notify, tooltips, etc), change the previous two lines to:
## SavedVariablesPerCharacter: TrinketMenuOptions, TrinketMenuPerOptions

Q: How do I move the minimap icon?
A: Drag it like a normal window.  Left click and drag it around and it will slide around the edge.

Q: I'm trying to swap trinkets, but instead of swapping it put a tiny trinket icon over my equipped one.
A: This means you're in combat mode.  You won't be able to swap trinkets until you leave combat.  The tiny trinket is the one that will swap in once you leave combat.

Q: What if I don't have Scrolling Combat Text, will it still notify me when trinket cooldowns expire?
A: If you don't have SCT, it will notify in the "errors" overhead, where you get "Insufficient mana", "Out of range", etc type errors.

Q: I don't have many trinkets and because of this I'm having problems docking to some corners.  Any way to make it easier?
A: Temporarily resize (drag lower-right corner) either window to make the differences greater so it's easier to dock to an exact corner.

Q: My menu is docked to the left of my main window, when I resize it by dragging the lower right corner, it's not behaving as I expect.
A: You likely expect the topleft corner of the menu to remain and the bottomright corner to follow the pointer as you drag.  If it worked this way, the window would then "snap" to dock position after you're done resizing, and it'd be difficult to know exactly how it'd look while resizing.  A better solution would've been to make all corners resizable, but it was kept in this awkward state for simplicity's sake.  If there's demand for it, I can make all corners resizable.

Q: It's not showing all my trinkets, I have over 30 of them in my bags.
A: This version can handle only up to 32 trinkets.  Two equipped and 30 in bags.  If you exceed this amount, post how many trinkets you have and I'll up the limit.  30 seemed a reasonable number, but as the screenshots show it's not very difficult to get 30 trinkets if you're an engineer.  In the meantime the mod will lift trinkets from right bag to left if you want to control which 30 are displayed.

Q: I can't rotate, resize, move or do anything with the windows.
A: That sounds like the windows are locked.  Enter: /trinket unlock
```
