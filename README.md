# Omarchy Workspaces Integration Preview

A temporary, installable preview of the combined workspace changes proposed in:

- [Omarchy PR #8997](https://github.com/omacom/omarchy/pull/8997): show the workspace active on each bar's own monitor.
- [Omarchy PR #10190](https://github.com/omacom/omarchy/pull/10190): refresh Quickshell's monitor state after moving a workspace between monitors.

The stale-state behavior is tracked in [Omarchy issue #10187](https://github.com/omacom/omarchy/issues/10187).

This widget preserves the stock Omarchy layout while showing the active workspace number in the current theme color by default. It exists so the combined behavior can be tested during normal use while the upstream changes are reviewed.

## Appearance

The **Use theme color for active workspace** option is enabled by default. Turn it off in the Omarchy shell settings to restore the stock active-workspace symbol.

The same option can be configured directly on the widget entry in `~/.config/omarchy/shell.json`:

```json
"settings": {
  "useThemeColorForActiveWorkspace": false
}
```

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

The preview contains only the combined `Workspaces.qml` from the integration test branch. It does not include the optional color highlighting from [Monitor Workspaces](https://github.com/dzanaga/omarchy-monitor-workspaces).

Once both upstream changes are available in Omarchy, this preview plugin should no longer be necessary.

## License

MIT
