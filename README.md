# Omarchy Workspaces Integration Preview

A temporary, installable preview of the combined workspace changes proposed in:

- [Omarchy PR #8997](https://github.com/omacom/omarchy/pull/8997): show the workspace active on each bar's own monitor.
- [Omarchy PR #10190](https://github.com/omacom/omarchy/pull/10190): refresh Quickshell's monitor state after moving a workspace between monitors.

The stale-state behavior is tracked in [Omarchy issue #10187](https://github.com/omacom/omarchy/issues/10187).

This widget preserves the stock Omarchy layout and appearance. It exists so the combined behavior can be tested during normal use while the upstream changes are reviewed.

## Appearance

By default, the active workspace uses Omarchy's stock symbol. The optional `useThemeColorForActiveWorkspace` setting replaces that symbol with the workspace number in the current theme's accent color.

| Theme color enabled | Default stock symbol |
| --- | --- |
| ![Active workspace shown as a colored number](./assets/workspaces-themed.png) | ![Active workspace shown with the stock symbol](./assets/workspaces-stock.png) |

To enable the colored number, add the option directly beside the widget's `id` in `~/.config/omarchy/shell.json`:

```json
{
  "id": "io.github.dzanaga.workspaces-integration-preview",
  "useThemeColorForActiveWorkspace": true
}
```

Set it to `false`, or omit it entirely, to use the stock symbol. The shell reloads the change automatically.

## Installation

```bash
omarchy plugin add https://github.com/dzanaga/omarchy-workspaces-integration-preview.git --enable
```

The plugin declares itself as a clone of `omarchy.workspaces`, so enabling it replaces the built-in workspace widget in its existing position.

## Updating

```bash
omarchy plugin update io.github.dzanaga.workspaces-integration-preview
```

## Removal

```bash
omarchy plugin remove io.github.dzanaga.workspaces-integration-preview
```

Removing the preview restores the built-in Omarchy workspace widget.

## Scope

The workspace-state behavior is the combined implementation from the integration test branch. The themed-number option only changes how the active workspace is drawn.

Once both upstream changes are available in Omarchy, this preview plugin should no longer be necessary.

## License

MIT
