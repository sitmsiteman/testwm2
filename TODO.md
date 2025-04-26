## Key Concepts to Implement
- Wayland Server Setup (wl_display, wl_event_loop)
- Output & Renderer Management (wlr_output, wlr_renderer)
- Input Handling (wlr_input_device, wlr_keyboard, wlr_pointer)
- Surfaces & Views (wlr_surface, wlr_xdg_surface)
- Layout Management (tiling, stacking, etc.)

## How Wayland Compositors Work
- Windows (Surfaces) – Clients (apps) request to display surfaces.
- Input (Keyboard/Mouse/Touch) – The compositor routes input events.
- Rendering – The compositor decides how and where to draw windows.

## Key Components:
| Component	| Role |
|-----------|------|
|wl_display	| The Wayland server (manages clients & events). |
|wlr_output	| Represents a monitor (handles resolution, modes). |
|wlr_surface| 	A buffer from a client (window content). |
|wlr_xdg_surface| 	A desktop-ready window (from xdg-shell protocol). |
|wlr_seat| 	Input device group (keyboard, mouse, touch). |
|wlr_renderer| 	Renders surfaces (GPU or software). |

## Basic Workflow
- Clients connect to the compositor via WAYLAND_DISPLAY.
- Compositor creates surfaces for each window.
- Input events (keyboard/mouse) are sent to the focused surface.
- Compositor renders all surfaces in a scene graph (with effects like shadows).
