```
3.41, 8/24/06, added: /trinket load, changed: tabs removed and window shortened if TrinketMenuQueue not installed, bug fixed: /trinket reset (savedvars load defaults if nil), checked for Queue before setting HideOnLoad
3.4, 8/22/06, added: trinket profiles, delete trinket button
3.3, 8/5/06, added: 1.12 "Floating Combat Text" support, changed: trinkets coming off cooldown clear combat queue, toggle key binding obeys 'Disable Toggle' option
3.22, 7/24/06, added: TrinketMenu.SetQueue and TrinketMenu.GetQueue
3.21, 7/16/06, changed: lock also locks OptFrame, bug fixed: global strings stripped "%1$d Charge" to "%d Charge"
3.2, 7/16/06, added: Stop Queue On Swap option, global cooldown spinners, alt+click to stop queue cancels combatqueue
3.1, 7/12/06, changed: cooldown-enabled trinkets swapped in manually will not stop queue, added: "pause queue" attribute to trinkets, bug fixed: error from trinket used then banked while on cooldown, removed: trinket missing checks
3.01, 7/9/06, bug fixed: hunter fd will allow swap, minimap button can turn off
3.0, 7/9/06, rewritten, auto trinket queues, new timer and cooldown/notification system, options: set menu columns, tiny tooltips, large cooldowns, show key bindings
2.7 3/30/05 - added: /trinket debug, changed: update events disabled while zoning
2.6 2/8/05 - bug fixed: minimap button movement, added: option to drag around square minimap, option to show menu on shift only
2.5 1/4/05 - added: notify at 30 sec option, changes: 1.9 scaling, uses GetItemInfo, removed: scalebugfix, cooldowns off screen check
2.4 10/21/05 - added: /trinket scale slash command, sound on notify, changed: per-character position/orientation/docking, UseInventoryItem 13 and 14 hooked to reflect use, bug fixed: added scale bug fix back in
2.3 10/2/05 - added: option to disable tooltip, changed: options movable window that defaults to center, bug fixed: logging in character without trinkets won't prevent it from showing next login, for 1.8: pre-emptive fix for 1.8 SetPoint layout-cache bit, scale bug fix no longer performed
2.23 9/3/05 - bug fixed: hunter fd won't queue a trinket that can ordinarily swap, if the mod is hidden on logout it will be hidden on login
2.22 9/2/05 - bug fixed: if res'ed before releasing your spirit with trinkets in queue, they'll swap on revive normally
2.21 8/21/05 - bug fixed: window scaling bug definitively fixed, and error when clicking an empty trinket slot
2.2 8/20/05 - added: swap attempts while dead will queue trinkets to swap on revive, options to disable toggle, notify used only, and notify chats also, bugs fixed: error for more than 30 trinkets, notify corrected, hopeful fix for location bug some have: forced start/stopmove to save to layout-cache.txt, move the window to saved point going in/out of windowed mode
2.11 8/17/05 - changed: swap attempts won't happen if anything on cursor, bug fixed: options window will appear on screen irregardless where minimap is, added: /trinket debug to help find location bug issue some see
2.1 8/17/05 - added: a resize grip to lower right corner, trinket queue, option to dock/undock, notification when trinket cooldown ends (via SCT or overhead), bugs fixed: cooldown update made less frequent, 
2.0 8/14/05 - rewritten from scratch, added up to 30+2 trinkets, menu grows outward, cooldown numbers, keep menu open option, minimap icon and scaling, far better handling of bag/inventory updates, cooldown models won't update if they're off the screen
1.1 7/20/05 - only react to BAG_UPDATE every second (by Thelgar), made lock/unlock more visually apparent and moved menu closer to main window
1.0 4/8/05 - initial release
```
