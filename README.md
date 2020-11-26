# Drift
Addon for World of Warcraft that modifies default UI frames so you can click and drag to move and scale.

CurseForge links:
 * [Drift (Retail)](https://www.curseforge.com/wow/addons/drift)
 * [Drift (Classic)](https://www.curseforge.com/wow/addons/driftclassic)

## TODO
1. Bag behavior different in retail and classic
   1. containerFrameOffsetX logic only exists in retail, so classic is not accurate
1. Add scaling support for WorldMapFrame
1. Remove delay for Guild & Communities (retail) and Blizzard Groups (classic)
1. Configurable variables
   1. Opacity while moving and scaling
   1. Max and min scale
   1. Scale increment
1. Add "/drift reset" alias to "/driftreset" and maybe more commands
   1. Make sure to update documentation
1. Why do Drift Delegates make the mouse move the drag distance before moving their frame?
1. Make frames optional
   1. All the menu frames
   1. Achievements
1. Make ObjectiveTrackerFrame (retail) have dynamic height instead of fixed
   1. Or if not dynamic, some height parameter in Drift Options
   1. Or figure out some other way of not dragging around empty space
1. Add Vehicle Seat Indicator

## Bugs
1. VehicleSeatIndicator bugs
   1. Moving VehicleSeatIndicator will move the ObjectiveTracker
   1. Sometimes, the ObjectiveTracker gets hidden when the VehicleSeatIndicator moved
   1. VehicleSeatIndicator stretches out sometimes because of SetPoint called elsewhere
   1. VehicleSeatIndicator resets from other stuff too - probably managed
1. Fix UIWidgetTopCenterContainerFrame (retail and classic)
   1. Dragging "Time Remaining" in BG causes the widget to get stuck in drag mode
   1. Sometimes the children do not get to be made movers, e.g. return from BG
   1. Need some recursion for the child movers, e.g. BG Horde and Ally bars
1. Clicking PlayerChoiceFrame buttons resets PlayerChoiceFrame (retail)
   1. Example is in Warfronts
   1. To fix, need to add Drift Tabs
1. LootFrame resets when opening other frames (retail and classic)
1. Scaling Bugs
   1. Map does not work correctly after scaling WorldMapFrame
   1. Character model has incorrect size after scaling CharacterFrame
   1. Item models have incorrect size after scaling CollectionsJournal
1. Frames with tabs move from hotkey when on other tab
1. ColorPickerFrame moves when it's not supposed to
1. Some frames do not move depending on addons loaded
   1. TimeManagerFrame (retail and classic)
   1. TalkingHeadFrame (retail)
   1. PlayerChoiceFrame (retail, seems to only break right after login)
1. Some frames do not reset position after Reset Frames is invoked
   1. Game Menu / Main Menu
   1. System
   1. Interface / Interface Options
   1. Key Bindings
   1. AddOn List
1. Leveling up causes frame positions to reset
