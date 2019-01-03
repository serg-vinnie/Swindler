0.0.3
=====

New features
- A `Window.frame` property was added. You can now atomically change the whole
  frame of a window.

Breaking changes
- The new `Window.frame` now uses Cocoa coordinates (origin at bottom-left), to
  match the behavior of Screen and most modern macOS APIs.
- `Window.position` was removed in favor of `Window.frame`. See #32 and #29 for
  more.
- `WindowFrameChangedEvent` was added, replacing `WindowPosChangedEvent` and
  `WindowSizeChangedEvent`. See #16 for more.

Bug fixes
- `ScreenLayoutChangedEvent` is now correctly detected.
- When a property value is written to, and the new value is changed but does
  not match the desired value, the corresponding event is marked as external.
  See #49.

0.0.2
=====

Breaking changes
- `Swindler.state` has been replaced with `Swindler.initialize()`, which returns
  a Promise.

New features
- An experimental FakeSwindler API has been added for testing code which depends
  on Swindler. The API is expected to change, but probably not too much.

Bug fixes
- Setting the frontmostApplication from Swindler should now work.
- Various other bug fixes and improvements.