# Omarchy Rose Pine Grey - Theme Customization Notes

## Overview
This is a Rose Pine theme for Omarchy that covers multiple applications and tools. The theme is currently based on the Rose Pine color palette with a purple-tinted background.

## Requested Changes

### Background Color Change
**Current background:** `#191724` (Rose Pine's base purple-tinted dark)
**New background:** `#0d1117` (GitHub-style dark grey/black)

This is a significant shift from the warm purple tone to a cooler, more neutral grey-black tone.

## Files to Update

The background color appears in multiple configuration files across different applications:

1. **[alacritty.toml:3](alacritty.toml#L3)** - Terminal emulator
   - `background = '#191724'` → needs update

2. **[kitty.conf:2](kitty.conf#L2)** - Alternative terminal emulator
   - `background               #191724` → needs update
   - Also appears on line 14 for `inactive_tab_background`

3. **[hyprland.conf:5](hyprland.conf#L5)** - Window manager colors
   - `$base           = 0xff191724` → needs update
   - Note: Uses different format (0xff prefix for ARGB)

4. **Other files to check:**
   - [btop.theme](btop.theme) - System monitor
   - [neovim.lua](neovim.lua) - Text editor
   - [hyprlock.conf](hyprlock.conf) - Lock screen
   - [mako.ini](mako.ini) - Notification daemon
   - [waybar.css](waybar.css) - Status bar
   - [walker.css](walker.css) - App launcher
   - [swayosd.css](swayosd.css) - OSD

## Implementation Strategy

### Phase 1: Core Background Change
Update the main background color in terminal emulators and Hyprland:
- Alacritty
- Kitty
- Hyprland base color

### Phase 2: Related Colors
Some colors may need adjustment to maintain proper contrast and visual hierarchy:
- **Surface colors** - May need to be adjusted to work with the new darker background
- **Overlay colors** - Current: `#26233a` (purple-tinted), might need updating
- **Selection backgrounds** - May need contrast adjustments
- **Inactive/dimmed elements** - Review for visibility

### Phase 3: UI Elements
Update background references in:
- Status bars (waybar)
- Notifications (mako)
- Lock screen (hyprlock)
- System monitor (btop)
- App launcher (walker)
- OSD (swayosd)
- Neovim

## Color Format Notes
Different applications use different color formats:
- **Hex (no prefix):** `#191724` - Used by most configs
- **Hex with 0xff prefix:** `0xff191724` - Used by Hyprland (ARGB format)
- **RGB format:** May be used in some CSS files

## Questions to Consider

1. **Scope:** Should we only change the pure background, or also adjust related surface/overlay colors to match the new cooler tone?

2. **Contrast:** The new background `#0d1117` is darker than `#191724`. Should we verify that text and UI elements have sufficient contrast?

3. **Theme name:** Since we're changing from purple-tinted to grey, should the theme be renamed (e.g., "omarchy-rose-pine-grey")?

4. **Secondary backgrounds:** Should colors like `$surface` and `$overlay` also shift from purple tones to grey tones, or keep the purple accent?

## Next Steps

Would you like me to:
1. Just update the background color to `#0d1117` across all files?
2. Also adjust surface/overlay colors to match the cooler tone?
3. Review and update related colors for better contrast?
4. Update the README and any documentation?
