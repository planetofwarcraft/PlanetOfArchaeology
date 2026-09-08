# Planet of Archaeology

PlanetOfArchaeology is a dependency-free archaeology expedition companion for World of Warcraft Retail. This build targets the locally installed **12.1.0.69587** client (`## Interface: 120100`).

## Installation

### 1.15.58

- Embedded Ukrainian translations for all 12 native archaeology race histories. The projects header now uses the selected addon language instead of always displaying client-language history. Other locales and native Blizzard tooltips are unchanged.
- Later cultures have artifact lore instead of native race histories; this release does not claim to complete the remaining artifact lore translations.

### 1.15.57

- Added Ukrainian lore for all ten mantid artifacts, including Ancient Sap Feeder. ID-based overrides work regardless of native client language and do not use packing-effect text as lore.
- Audit: the saved native snapshot still contains only 100 lore descriptions and 70 item-effect-only texts. This update closes the ten mantid gaps; other uncaptured artifact lore remains incomplete and retains native text. No claim of complete catalog lore coverage is made.

### 1.15.56

- Increased automatic window scale by 15% at 1080p, tapering smoothly to no change at 1440p and above. Viewport bounds, manual settings and the minimap scale exemption remain intact.

### 1.15.55

- Sidebar race crests now crop the actual Blizzard race artwork region and sit vertically centered on the left with a six-unit inset, rather than centering the transparent texture sheet.

### 1.15.54

- Removed the minimap glow, pulse and hover highlight. Enlarged dig-site sidebar race crests from 30 to 44 UI units and adjusted text anchors.

### 1.15.53 — renamed package

The install folder and TOC are now PlanetOfArchaeology. Runtime globals, frame names, asset paths and saved-variable names use PlanetOfArchaeology. Commands: /planetofarchaeology, /poa and the compatible /rp alias.

IMPORTANT: upgrades from the old package require closing WoW first and migrating the old account SavedVariables file to PlanetOfArchaeology.lua with the renamed database globals. Keep a backup of the original. Remove the old addon from AddOns only after this transfer; do not enable both versions. Older release notes below describe historical builds, not this migration procedure.

Donation prompts are intentionally absent from the in-game addon under Blizzard's UI Add-On Development Policy. Donation links belong on the external addon website or distribution page.

### 1.15.52

- Addon windows and menus use LOW strata below Blizzard map, bags and achievements. Notifications stay above addon windows but below native panels, with a more opaque background to prevent text bleed-through. Blizzard frames are unchanged. The settings language dropdown keeps its native-settings dialog layer.

### 1.15.51

- Middle-click now cycles through eligible dig sites instead of selecting the same nearest target again. Automatic nearest-target selection is unchanged.
- About includes a compact illustrated control guide and a channel button that focuses/selects the copyable URL. Restricted browser-launch APIs are not called.

### 1.15.50

- Renamed the displayed addon to Planet of Archaeology by Planet of Warcraft. The PlanetOfArchaeology folder, saved-variable keys and commands remain compatible with existing installations. Replace the existing folder; do not install a second copy.
- Added the About tab with the creator's YouTube link for copying. All supported UI languages include the new labels.
- Achievement search filters translated titles immediately, combines with expansion/status filters, and supports Cyrillic case folding. Escape clears the search.
- Continuous viewport-based scaling across 1080p, 1440p and 4K; the main frame reserves horizontal space for the docked route. Default dock groups are moved into the viewport after dragging, without overwriting saved positions or moving during a drag.

### 1.15.49

- Percentage sliders replace scale/opacity +/- controls, snapping to 5 percentage points. Window/global scales support 40%; their product is no longer silently clamped to 75%. Interface reset restores appearance and positions without deleting archaeology data, language, or navigation preferences.
- Distance choices include automatic, metric, imperial (yards/miles), meters-only and kilometers-only. Automatic uses imperial for enUS clients and metric otherwise; manual selection overrides it. Client language is a preference heuristic, not physical location detection.

### 1.15.48

- High-resolution scaling now uses the actual UIParent viewport instead of mixing physical pixels with UI coordinates. Main-window scaling is bounded to 76% of viewport width and 85% of height, including previously saved large manual settings. Saved preferences are preserved; collector-owned minimap buttons remain exempt.

### 1.15.47

- Embedded original Ukrainian translations from the available native text snapshot: 100 artifact lore descriptions, 70 additional item-effect texts, all 109 captured archaeology achievement names/descriptions/rewards, 315 non-empty criterion slots, and 7 available expedition reward descriptions. IDs, not Russian text, select achievement translations on every client locale.
- Six artifacts include both their captured lore paragraphs. Missing lore is not replaced with generic packing instructions. Blizzard item tooltips are unchanged; no runtime translator or export command is required to use the bundled translations.
- Coverage is not complete for all possible native content: 94 catalog items had no captured description/effect, another 70 had only effect text, and 6 expedition rewards had no captured effect. Future uncatalogued text retains the native fallback. The local source snapshot and translation tests track coverage; no completion values are altered.
- Effect-only artifact translations are matched against the captured original, so an uncaptured research-spell lore paragraph is never overwritten with an unrelated item-use effect. These effect matches currently cover the captured Russian client; lore and achievements use locale-independent IDs.

### 1.15.46

- Ukrainian in-panel content overrides for the three user-supplied examples: Eye of Har'gunn the Blind, Starlight Beacon and the Russian-client Boy Emperor achievement. Asynchronous spell loads preserve the translated description. Native item tooltips remain unchanged.
- Full description localization remains pending source collection. `/rp exporttexts` captures available native artifact descriptions, archaeology achievements/criteria and expedition reward text; wait 10 seconds, then `/reload`. The `PlanetOfArchaeologyTranslationSource` table is saved inside the addon's usual WTF SavedVariables/PlanetOfArchaeology.lua file. The export table contains no character names or completion progress. Missing/unloaded game descriptions are not invented or hidden.

### 1.15.45

- HUD uses the race reported by survey/find events, scoped to the current dig site. First-project data gets bounded event-driven retries; site refresh finishes before the HUD rereads its project. Unknown learned branches no longer erase a known site's race index. No automatic artifact selection or invented progress.

### 1.15.44

- Route distances and arrows can use the player's current city/floor world position when the continent map returns no player position (including Northrend Dalaran). World instance IDs are checked, and stale distances are cleared when position is unavailable.

### 1.15.43

- Settings split into Interface, Navigation and Advanced tabs. Scale controls show percentages with separate labels; language selection opens a list instead of cycling.
- Added an addon-authored Ukrainian UI dictionary, all 264 catalog artifact names and 20 archaeology race names. Display translations do not modify native names used for completion matching or saved history.
- Ukrainian content localization is not yet complete: native lore descriptions, quest/map names, achievement titles/descriptions and Blizzard item tooltips still use the game client language. This is not an official Blizzard locale.

### 1.15.42

- Docking remains enabled by default. Dragging linked secondary windows saves a persistent relative offset instead of disabling docking. The route follows the main window, and the HUD follows the repositioned route. Only the settings checkbox disables linking.

### 1.15.41

- Unified selection markers: one 18-unit cut-corner gold outline and consistent check strokes. Removed the route marker's fractional downscale and nested decorative borders.

### 1.15.40

- Added complete UI dictionaries for deDE, itIT, ptBR, koKR, zhCN and zhTW, plus a separate esMX dictionary based on shared Spanish translations. Automatic and manual selection cover all 11 WoW locales; enGB/ptPT aliases map to enUS/ptBR.
- Item, race, quest and achievement data supplied by WoW retain the client language. UI translations are addon-authored, not official Blizzard translations.
- Expanded the reference dig-site/race mappings to all client locales using Minimal Archaeology's localized site names. Only the active client's table is instantiated; unknown sites still use the existing survey-learning fallback.

### 1.15.38

- Added a persistent Dock windows checkbox. Dragging the route or unlocked survey HUD switches to free mode without snapping back. Re-enable the checkbox to regroup.
- Free windows keep their positions; opening windows tries adjacent non-overlapping placements when space permits, without a continuous positioning constraint.

### 1.15.37

- Automatic 1440p/2160p window scaling accounts for WoW's root UI scale. 1080p remains unchanged. Manual scale now extends to 2.00 and resize grips preserve the resolution multiplier.
- Display/UI-scale changes reapply settings outside combat. Minimap icons retain their previous scale for collector compatibility; the popup menu scales with the windows.

### 1.15.36

- Animated first-artifact notifications with the native icon and wrapped name. Requires a fresh first-solve history record; persisted per-character deduplication and bounded history retries prevent repeat alerts. Replaces unconditional rare-solve alerts.
- Notifications queue instead of replacing one another. Existing notification and sound settings still apply.

### 1.15.35

- Wrap artifact names at word boundaries. Titles with words too wide for the icon-side column, or more than 72 units tall, use the full width below the icon.

### 1.15.34

- Removed vertical constraints that truncated archive detail titles. Wrapped title, metadata and status now determine the description's starting position; body text fits the actual panel width.

### 1.15.33

- Remove PlanetOfArchaeology's own button scale when a collector takes over, preventing scaled grid offsets in EllesmereUI. Preserve collector-defined scales and restore native scale when the original anchor returns.

### 1.15.32

- Respect minimap collectors that reparent or reanchor the icon (including EllesmereUI's flyout). Position/scale updates and native dragging yield to external layouts; collector OnUpdate handlers are no longer overwritten. Native positioning resumes when the original parent and anchor are restored.

### 1.15.31

- Raised window shortcuts above section drag handles so clicks and hover reach them in both full and compact journal layouts. Slightly enlarged the hit area without changing the icon size.

### 1.15.30

- Restored survey HUD docking beside the route, including compact mode and dragging. Closing the route restores the HUD's saved standalone position; temporary docking never saves over it.

### 1.15.29

- Restore the HUD and route to their own saved positions after closing the main window; independent windows no longer move one another. Only factory positions migrate to the right of the character.
- Smaller window shortcuts and narrower route cards, with separate name, checkmark and direction areas. Route height follows the number of sites, up to four visible cards.
- Hide missing project icons and misleading zero fragment totals. Resolve archive icons even before localized item data has loaded.
- Audited the 264 unique catalog rewards against the bundled Minimal Archaeology reference; Drust and Zandalari each contain nine, Demonic contains ten. Pristine variants are separate achievement criteria, not extra base projects.

### 1.15.28

- Preserve theme enter/leave handlers in shared buttons and expedition reward tooltips, restoring immediate hover and leave feedback without polling.

### 1.15.27

- Moved window shortcuts inside each frame. Shortcuts now toggle the target window without stopping an active expedition. Removed external-rail spacing from docking.

### 1.15.26

- Restored immediate hover highlighting on the main dig-race tiles, preserving selected and ready states when the pointer leaves.

### 1.15.25

- Narrower route window (260 UI units) and two compact cross-window shortcuts on each window. Manual survey-panel opening works outside dig sites; its close button restores normal visibility rules. Docking reserves space for shortcut rails.

### 1.15.24

- Verify tracking against the native objective ID list and explicitly refresh/expand the native achievement tracker after a user click. One deferred verification per click; no polling.

### 1.15.23

- Restyled achievement scroll handles with bronze cut-corner borders and grip details. Criteria use thin gold/bronze progress lines, separate counters and stable incomplete-first ordering.

### 1.15.22

- Fixed route-row tooltip handlers replacing theme hover handlers. Hover and leave now respond directly to mouse events, preserving selected-target highlighting.

### 1.15.21

- Achievement criteria now have individual progress cards. Added persistent achievement wishes, a wishlist filter, and native WoW objective tracking controls. Progress reflects credited criteria, including pristine artifact display requirements.

### 1.15.20

- Avoid achievement list rebuilds on criteria events and unchanged UI refreshes; update selected criteria only, coalesce visible events, and schedule no achievement timers while hidden. Reuse rendered rows within a scroll row.

### 1.15.19

- Added draggable achievement list/detail scrollbars and a combined expansion/status filter. General and unclassified achievements remain accessible under General / Other and All expansions.

### 1.15.18

- Restored the standard WaypointUI target marker by removing PlanetOfArchaeology's icon override.

### 1.15.17

- Added Archaeology Achievements before Journal, with earned/missing filters, native descriptions, rewards and criteria progress. Includes progressive achievement tiers and updates on completion.


1. Exit World of Warcraft.
2. Copy the `PlanetOfArchaeology` folder to:
   `World of Warcraft/_retail_/Interface/AddOns/PlanetOfArchaeology`
3. Start the game and enable PlanetOfArchaeology in the AddOns list.
4. Use `/rp` to open the field journal.

## Working in version 1.15.16

- Notification race icons now use the native archaeology crop, filling a 60x68 portrait area rather than showing the texture sheet's empty margins. Item/reward icons keep their normal crop; panel and text sizes are unchanged.

- WaypointUI receives a full archaeology icon instead of an uncropped race texture sheet. Destination names and coordinates are unchanged.

- Research race icons use Blizzard's archaeology texture-sheet crop and larger 44x50 bounds. Gold hover/selection lighting follows the icon's alpha silhouette with shifted texture copies; the square action-button glow is removed.

- The assembly page uses a compact 390-unit card: one race heading, scrollable history supplied by the native archaeology project, an 80px artifact icon, fragments and bottom-aligned actions. The restore animation remains in its own reserved area.

- Research race icons gain a soft gold glow on hover and a stronger persistent glow for the selected race. The short fade stops updating once settled.

- A slim gold fragment-progress bar fills the idle space beneath the shovel. The finds counter replaces it once dig-site progress is available; no Ready label is shown.

- Expanded reward cards are reduced from 264 to 174 units, with a reward icon, a localized item-effect description, availability dates and side-by-side actions. Cards fade in on opening; the icon opens the full native item tooltip on hover.

- The survey HUD no longer displays Ready below the shovel. The label appears only when a dig-site finds count is available.

- The minimap expedition menu has a translucent charcoal shell, chamfered corners, a subdued bronze border and light grain, without the rectangular outer shadow. Its action buttons remain unchanged.

- Notifications have a lighter translucent panel, subdued bronze border, a 68px race/reward icon (previously 46px), more breathing room and readable shadowed text. Existing entrance/exit animations and notification settings are preserved.

- Reward hover uses the native item tooltip. Clicking a reward expands its details inline, including its type, completion status and availability window; technical quest IDs are no longer displayed.
- Expedition dates use the current realm's calendar time and show the realm name. UTC is explicitly labeled when the calendar API is unavailable. Rotation calculations remain region-based.
- Interface languages: English, Russian, French and Spanish. Options > AddOns > PlanetOfArchaeology > Language cycles Auto / Russian / English / French / Spanish live and persists the choice. Auto supports enGB and esMX aliases; unsupported locales fall back to English. Native item/race/quest names and tooltips remain in the WoW client's language.

- Compact controls use Blizzard's matching 24px red-button atlases; layout switches fade out and back in.
- WaypointUI coordinates are correctly passed as percentages, as required by NewUserNavigation. Explicit navigation hides the journal and opens the map where the waypoint was actually placed.
- Expeditions include All rewards / Wishlist filters. Reward details can prepare a personal in-game calendar event in server calendar time; the player confirms Create to save it. Existing calendar drafts are never replaced.

- Route header is centered, compact controls use visible red/gold square buttons, and the footer has only a centered Finish action.
- The main journal can hide its left sidebar without shrinking fonts; the choice persists across reloads.
- Navigation uses C_Map world axes (north/west) and counterclockwise player facing consistently. WaypointUI receives named archaeology targets through its public API, with the native waypoint path retained as fallback.
- Fractional-scale border textures no longer snap to zero coverage; docking does not overwrite an active resize anchor and keeps the survey panel within screen bounds.

- Legion reward details have a persisted wishlist toggle; wished rows are underlined in gold. An available, unfinished wished reward is announced once per rotation, respecting notification settings and retaining deduplication across reloads.
- Route header +/- toggles a persisted 142-unit minimal view with only the current target, arrow and distance. Expanding restores the full route; the independent survey HUD and docking remain unchanged.

- Left sidebar renamed Dig Sites. Explicit Legion waypoint clicks work independently of automatic-waypoint settings and open the destination map. City-map restrictions fall back to a precise world-coordinate projection onto an allowed parent map.

- Tabs: Research / Expeditions / Journal. Legion's 13-entry rotation is calculated separately from the themed UI, using server time and live weekly-reset alignment.
- EU reference: Spirit of Eche'ro starts 2026-08-05; US: 2026-08-04. EU 2026-09-05 resolves to Starlight Beacon, followed by Spear of Rethu.
- Expedition names/icons use client item data with English fallback. Quest-chain completion uses the final quest (character or account completion), not the introductory quest. Missing chain data is explicitly unknown.
- Dariness waypoint: Legion Dalaran (627), 40.8 / 26.4. Active chains use GetNextWaypoint; without reliable coordinates the quest is tracked without inventing a location.
- The left Direction panel shows collection counts or Ready. Project actions switch between Plan Route and Restore Artifact. Original catalogue and journal remain.
- No SavedVariables migration or runtime dependency was introduced. Other regions without a supplied reference date show an unsupported-region message. Dates are labelled UTC; asterisk denotes a missing weekly-reset time.

### 1.15.0 validation

All Lua files pass the Lua 5.1 syntax parser. `work/test-legion.py` executes the real rotation and page modules in Lua 5.1 with mock WoW APIs: EU/US dates, 53 boundaries, future returns, unavailable region, quest-chain status, objectives, waypoints, 13 list rows, details, tab switching and timer cleanup.
This does not replace a Retail in-game `/reload`, visual layout or live quest-data test.

Static IDs come from the existing ArtifactCatalog and `work/minarch/addon/data/ArtifactDB.lua` (see THIRD_PARTY_NOTICES.md). The quest-line API and waypoint signatures were checked against the local Retail API documentation. Dariness's position was cross-checked against [the NPC database](https://www.wowhead.com/npc=93538/dariness-the-learned) and [the Legion archaeology location guide](https://worldofwarcraft.judgehype.com/news/la-balise-de-lumiere-stellaire-est-disponible-jusqu-au-20-ars-2024-176855/).

- Docked windows follow dragging every rendered frame instead of at 10 Hz. Stationary anchors and unchanged visibility are not rewritten.

- Survey HUD docks beside the route, without inheriting its visibility. Each panel has a separate close action.
- Opening the journal docks auxiliary panels on its right when space allows; otherwise temporarily hides them. Closing the journal restores eligible panels and the route's saved position.
- The minimap menu reopens an active expedition's route; completion remains on the route's Finish button. The main Races tab is removed.

- Suppressing the duplicate restoration cast now preserves Blizzard's nonzero-alpha fade prerequisite. Completed suppressed casts are hidden before restoring alpha, without hiding a new cast or channel.

- Route preferences occupy one dropdown: local races and Nearest. Selected races share equal preference and are ordered by distance; no strict filter or numeric ranks.
- Selection indicators and the dropdown chevron are drawn shapes, not font glyphs. The popup overlays the list and closes on outside click.

- The native digsite bar finishes without enqueueing Blizzard's duplicate completion toast. PlanetOfArchaeology's completion notification and the usual completion sound remain; other alert systems are unchanged.

- Digsite finds smoothly advance the bronze fill over 0.6 seconds with a fading gold spark; no idle animation loop.
- The stock player cast bar is visually suppressed only for the matching restoration while the Assembly progress display is visible. Survey and unrelated casts remain unchanged.

- Starting an expedition hides the main journal. The duplicate Dig Sites tab is removed from navigation.
- The route window has local race selection, highest-priority actions, distance/priority ordering, strict/preferred filtering and journal/finish controls.
- Resize grips scale the actual window smoothly around its top-left corner without a preview rectangle; combined scale has a 0.75 readability floor.

- Route directions use open gold compass needles with frame-rate-independent shortest-path rotation.
- The route header contains only the region and wrapping race names, with automatic card height.
- Passive project reads no longer switch the selected artifact and clear socketed stones; keystone clicks verify the actual socket count and refresh the HUD tooltip.

- Assembly shows real restoration cast progress, a moving gold highlight and success/cancellation feedback.
- The native digsite progress bar uses subdued bronze artwork without its heavy shadow or flash; Blizzard still controls its placement and visibility.

- Resize grips preview proportional size from a fixed top-left corner and commit once on release, preserving text during dragging.
- Race summaries no longer select every Blizzard project; reading the current project preserves its inserted keystone.
- Window appearance no longer stacks page fades or fades to a second, reduced opacity.

- Windows, pages, the survey HUD and the minimap menu fade in briefly using native animations.
- Buttons, tabs and interactive cards smoothly transition between bronze, gold and pressed states; the shared animation driver sleeps when idle.

- Переключение вкладок обновляет только открытую страницу, а данные сборки и исследований кешируются до реального изменения археологии.
- Список исследований виртуализирован: вместо сотен UI-карточек одновременно используются только восемь видимых строк.

- Диапазон прокрутки списка артефактов теперь рассчитывается по фактическому числу записей текущего фильтра и больше не уходит в пустоту.

- «Начать экспедицию» снова обязательно открывает окно маршрута, даже если оно было ранее закрыто крестиком.

- Фоновая иллюстрация артефакта убрана из сборки; сохранён единый полупрозрачный фон интерфейса.
- Кнопка ключевого камня показывает настоящее локализованное название предмета выбранной археологической расы.

- Левая карточка экспедиции удалена; вся боковая панель отдана компактному выбору археологических рас.
- Сборка переделана в экран одного выбранного проекта: крупный артефакт, описание, прогресс, ключевые камни и восстановление.

- Левая панель «Сборка» стала полноценным селектором рас и текущих проектов с прогрессом и отметкой готовности.
- Выбор расы слева открывает «Сборку» и показывает в основной области только её текущий артефакт.

- «Сборка» перенесена из верхних вкладок в отдельную карточку левой панели.
- Активные раскопки перенесены с левой панели на страницу «Раскопки» и собраны в компактную сетку из двух колонок.

- Reads active dig sites from `C_ResearchInfo.GetDigSitesForMap(uiMapID)`.
- Walks the current map's parent chain and chooses the useful archaeology map without continuously scanning the world.
- Uses `C_Map.GetWorldPosFromMapPos` for comparable distances when the API supplies compatible world coordinates.
- Nearest and race-priority route modes.
- Strict and Prefer race filters.
- Race selector populated from the live archaeology API, with fragment progress and Shift-click priority.
- Manual destination selection and per-site blacklist from the dig-site context menu.
- Built-in Blizzard user waypoint and super-tracking, with a guarded fallback when a map cannot accept a waypoint.
- A movable, individually scalable route window lists every active dig site on the current archaeology continent using restrained dark field-journal cards, warm gold selection accents, live direction arrows, distances and click-to-track rows.
- Race emblems are larger, vertically centered and intentionally unframed in dig-site, research and race lists.
- Distance display is metric by default and can switch between automatic metres/kilometres, metres only and kilometres only.
- The route window also names the possible archaeology races for the current continent using localized game data.
- Always-available minimap button: left-click opens the journal, right-click opens a deliberately compact expedition/settings panel, and middle-click selects the next site.
- Shape-aware minimap positioning supports round, square, side-rounded and corner-rounded masks exposed by addons such as SexyMap; the button now remains close to the map regardless of its own scale.
- Automatic current-site detection with no arrival popup: during an active expedition, the Survey shovel appears only after the player is actually inside a dig site.
- A tiny on-site Survey widget with a properly inset shovel icon, an optional remaining-find badge and a compact fragment readout. Its artwork stays inside the action-button border at every configured scale.
- The fixed secure Survey action registers both click edges and explicitly fires on release, independent of `ActionButtonUseKeyDown`. It still casts only from the player's hardware click.
- Remaining finds at the current site (after the game reports progress) and fragments still needed for the current artifact.
- Expedition start/stop, explicit dig-session start, automatic next site after `ARTIFACT_DIGSITE_COMPLETE`, notifications and sound toggle.
- Notifications use a compact Blizzard-style card with a framed icon and smooth eased slide/fade entrance and exit. The new-target alert appears only for real destination changes, is throttled to once per 90 seconds, and is disabled by default on upgrade.
- The Archive page reads Blizzard's live completion history and lists every exposed artifact. It now uses a three-pane view: race list, artifacts for the selected race, and full artifact details. All, Obtained and Missing filters can be combined with the race filter.
- Archive artwork uses one clean inset border, and the collection counter is anchored in the header instead of overlapping artifact details.
- A bundled catalog supplies all 264 known archaeology rewards across 20 races instead of treating Blizzard's character-specific history response as the complete catalog. For example, Troll now correctly contains 17 artifacts. Localized item names and icons are loaded through `C_Item`, while Blizzard history supplies obtained status, lore and completion dates.
- Global interface scale and opacity controls, plus separate main-window, Survey-widget, route-window and minimap-button controls. Visible corner grips resize the three movable windows directly.
- A bundled Russian/English dig-site database identifies 438 unambiguous site/race names immediately; live Survey observations remain the fallback for future sites.
- The former Research and Archive pages are consolidated into one Research catalog containing all 264 artifacts and their collected state.
- The main PlanetOfArchaeology window participates in WoW's standard Escape-key closing stack.
- The main journal uses a two-section structure: a permanently visible, scrollable dig-site catalog on the left and a separate content panel on the right. Dig sites are selected directly from illustrated PlanetOfArchaeology cards, and the current destination receives a green completion-style ribbon.
- The expedition route is a standalone narrow catalog with the same framed summary, category divider and selectable dig-site cards. Its shell and cards use PlanetOfArchaeology's code-native 9-slice system rather than a stretched bitmap or borrowed atlas.
- Page-specific spacing was corrected for the two-panel layout: race names, fragment counts, progress bars, archive race totals and artifact subtitles now stay inside their cards. The Journal uses three contained summary cards, and the less frequently needed Races tab is placed last.
- Starting an expedition from the journal keeps the journal open. Artifact details show the vendor sell price after WoW loads the corresponding item data, when that artifact has a non-zero sell value.
- Version 1.12 introduces a unified field-archaeology visual system based on independent backgrounds, four straight edges, four clipped corners, subtle inner lines and state overlays. Large and compact rows, content panels, square icon frames, tabs, buttons, section dividers, route cards, notifications and the Survey HUD now share the same restrained bronze language. Normal, hover, pressed, selected, completed, progress and disabled states are handled centrally without strong glow or oversized decoration.
- Version 1.13 expands the Survey HUD with the current project, exact fragment contribution, an optional keystone slot and a Solve button. Keystone and Solve actions still require an explicit player click.
- Version 1.13.1 condenses that HUD and moves Solve onto the highlighted current-artifact icon, removing the truncated extra button.
- Version 1.13.2 turns the Survey HUD into a narrow vertical tool and keeps only the finds counter and compact project progress visible.
- Version 1.13.3 migrates the vertical HUD back to its safe top-center position and clips every panel fill to its chamfered corners, removing dark square protrusions.
- Version 1.13.4 restores the inner corner wedges up to the bronze diagonal while keeping the area outside each chamfer transparent.
- Version 1.13.5 removes overlapping corner fills, so chamfered side pieces now share exactly the same transparency as the rest of the panel.
- Version 1.13.6 smooths each chamfer with narrow non-overlapping bands, removing the visibly stepped cut while preserving uniform panel transparency.
- Version 1.13.7 replaces font-dependent status glyphs with crisp texture-built symbols: a gold selected check, green completed check, amber progress diamond and grey unavailable cross.
- Version 1.13.8 redesigns notifications as compact, content-sized cards with a race emblem, restrained divider and a clear status marker instead of the oversized generic waypoint toast.
- Version 1.13.9 lowers the texture-built check mark inside its status frame for balanced vertical centering.
- Version 1.13.10 moves the complete selected-target badge down from the card border and aligns it with the dig-site title.
- Version 1.14 removes the square surround from notification race emblems and adds an Assembly view to Research, with every current project, live fragment progress, keystone controls and click-to-solve buttons.
- Version 1.14.1 compacts the Assembly selector and project rows, and applies a one-time 10% global UI reduction to existing profiles without changing saved positions or per-window scale choices.
- Version 1.14.2 promotes Assembly to the first main tab and redesigns Races as a compact four-column emblem grid with slim progress bars and unobtrusive diamond state indicators.
- Saved settings, learned site/race associations, positions, blacklist and expedition statistics in `PlanetOfArchaeologyDB`.
- Modern AddOns settings page and `/planetofarchaeology` / `/rp` commands.
- Full enUS and ruRU strings for PlanetOfArchaeology-owned UI text.
- Debug output for maps, positions, returned dig-site fields, learned race, route target/reason and archaeology events.

Commands:

- `/rp` — toggle the journal
- `/rp start` — begin an expedition
- `/rp stop` — end it
- `/rp next` — recalculate and select the next site
- `/rp hud` — toggle the HUD
- `/rp lock` — lock/unlock the HUD
- `/rp debug` — toggle diagnostics
- `/rp reset` — reset window positions

## API findings and intentional limitations

The Retail-generated `DigSiteMapInfo` structure contains `researchSiteID`, `position`, `name`, `poiBlobID`, and `textureIndex`. It does **not** expose a research branch/race. Blizzard's own current `DigSiteDataProviderMixin` passes exactly that structure to the map pin and super-tracks it by `researchSiteID`; `textureIndex` is used only to select coordinates in the shared minimap POI texture.

PlanetOfArchaeology combines Blizzard's live site list with the maintained, name-based dig-site database from Minimal Archaeology. When an archaeology event supplies a `researchBranchID` while the player is on a site, that live observation overrides the bundled association. Truly new or ambiguous sites remain unknown until observed.

Consequences:

- Prefer mode prioritizes already observed selected races, then unknown sites, then known unselected races.
- Strict mode excludes genuinely unknown sites, because claiming that they match would be incorrect.
- Survey progress is shown only after the game provides `numFindsCompleted` and `totalFinds` in an archaeology event. It is not reconstructed after a reload.
- The API does not report an exact fragment quantity recovered by each find, so the journal does not fabricate a “fragments recovered” statistic.
- The map toggle controls Blizzard's native, modern dig-site pins. PlanetOfArchaeology does not replace the shipped `DigSiteDataProvider` with a second overlapping custom provider; the selected target is visibly represented by the Blizzard user-waypoint pin.
- Cross-continent distances are not invented. Sites whose world position is not comparable to the player's current continent show an unavailable distance and rank after reachable sites.
- PlanetOfArchaeology never casts Survey automatically. The HUD's secure Survey button requires a real player click, as required by WoW's protected-action rules.
- Solve is a normal hardware-click handler using the same non-protected `SetSelectedArtifact` / `CanSolveArtifact` / `SolveArtifact` flow used by Blizzard's Archaeology UI. PlanetOfArchaeology never sockets or spends a keystone automatically.

Primary references checked for this build:

- [Retail ResearchInfo generated API documentation](https://github.com/Gethe/wow-ui-source/blob/live/Interface/AddOns/Blizzard_APIDocumentationGenerated/ResearchInfoDocumentation.lua)
- [Retail Map generated API documentation](https://github.com/Gethe/wow-ui-source/blob/live/Interface/AddOns/Blizzard_APIDocumentationGenerated/MapDocumentation.lua)
- [Blizzard DigSiteDataProvider](https://github.com/Gethe/wow-ui-source/blob/live/Interface/AddOns/Blizzard_SharedMapDataProviders/DigSiteDataProvider.lua)
- [Blizzard Archaeology progress/event handling](https://github.com/Gethe/wow-ui-source/blob/live/Interface/AddOns/Blizzard_FrameXML/ArchaeologyProgressBar.lua)
- [Blizzard Archaeology UI](https://github.com/Gethe/wow-ui-source/blob/live/Interface/AddOns/Blizzard_ArchaeologyUI/Blizzard_ArchaeologyUI.lua)
- [Blizzard UiMapPoint helper](https://github.com/Gethe/wow-ui-source/blob/live/Interface/AddOns/Blizzard_ObjectAPI/Mainline/UiMapPoint.lua)
- [Minimal Archaeology source](https://github.com/MrFox42/minarch) (MIT-licensed dig-site/race data and reference for current Retail Survey-button behavior)

## In-game verification checklist

Static parsing and TOC-order checks cannot reproduce server-provided archaeology state. Test these items with an archaeology-trained character:

1. Open `/rp` on a continent with active dig sites and confirm names/coordinates.
2. Confirm the minimap icon remains visible; test left-click, the right-click expedition menu, middle-click and dragging it around both round and square minimap masks.
3. Fly near, but remain outside, a dig site and confirm that no arrival popup or shovel appears.
4. Start an expedition, enter the dig-site boundary and confirm that only the compact shovel appears automatically.
5. Start an expedition and compare the route-window arrows with the Blizzard waypoint while turning and flying.
6. Enter both the selected site and a different site; verify the HUD switches to the actual nearby dig site.
7. Click the standalone shovel and confirm it casts Survey on mouse release; confirm the badge and remaining-find text match Blizzard's archaeology progress bar.
8. Confirm the route window immediately identifies known site races and that a Survey can still learn a new site's race.
9. Finish a site and confirm the completed site is not immediately reselected while the server refreshes the list.
10. Test Strict with no learned matching sites; the HUD must show “No matching dig sites.”
11. Test zoning, portals, reload, login during an expedition, and maps that reject user waypoints.
12. Verify the HUD Solve button on a ready common and rare artifact; left-click the keystone slot to add a stone and right-click it to remove the last one.
13. Enable `/rp debug` and capture the chat output if a site is missing or its race is associated incorrectly.
14. Open Research, compare the Obtained/Missing filters with Blizzard's archaeology completion history, and open several entries to verify their localized lore and completion details.
15. Drag the gold corner grips on the main window, route window and Survey widget; verify each scale persists after `/reload`.

For the cleanest Lua error report during testing, enable the game CVar with `/console scriptErrors 1` and reload the UI.
