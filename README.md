# VSCode Essentials (Extension Pack)

[![Inline (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/jabacchetta.vscode-essentials.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.vscode-essentials)
[![Inline (VSCode extension) installs badge](https://vsmarketplacebadge.apphb.com/installs-short/jabacchetta.vscode-essentials.svg?color=blue)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.vscode-essentials)
[![Inline (VSCode extension) rating badge](https://vsmarketplacebadge.apphb.com/rating-short/jabacchetta.vscode-essentials.svg?color=blue)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.vscode-essentials)
[![MIT license badge](https://img.shields.io/badge/license-MIT-orange.svg?color=blue)](http://opensource.org/licenses/MIT)

## Introduction

[VSCode Essentials](https://marketplace.visualstudio.com/items?itemName=jabacchetta.vscode-essentials) is a collection of many individual extensions that includes all of the
functionality needed to turn VSCode into a ⚡ supercharged ⚡ integrated development environment (IDE).

This extension pack is language-agnostic, and does not include functionality for specific programming languages or
frameworks. Instead, this extension's objective is to remain relatively lean while delivering powerful features that all developers can benefit from.

## Features

* Enhanced comment highlights, styling, and wrapping
* Todo manager
* Snippet manager and generator
* Run code
* Spell check
* Real-time collaboration with edits, calls, chats, and comments
* Formatting of multiple files
* Advanced git tooling
* Multiple clipboards (clipboard ring)
* Code screenshots
* Project manager
* Detection of non-printing characters
* Smart backspacing (delete indentation/whitespace)
* Cursor navigation with the ability to go to any character with a few keystrokes
* Macros for executing multiple commands with a single keyboard shortcut
* Synced and shared VSCode settings
* Extended multi-cursor functionality (incrementing, inserting numeric sequences, etc.)
* Underlined matching brackets for improved visibility
* Ability to hack VSCode's stylesheets for UI elements that aren't yet included in the settings or official theme API
* Semantic indent and scope guides
* Automatic and manually added (tagged commits) local edit history

## Recommended Settings

### Bracket Pair Colorizer

```jsonc
{
    // Disable distracting bracket pair colors (prefer styling of Subtle Bracket matching pairs)
  "bracket-pair-colorizer-2.colors": [],

  // TODO: Modify style to fit your theme. This works well with Material Theme.
  // Customizes indent guide and scope line
  "bracket-pair-colorizer-2.scopeLineCSS": [
    "borderStyle : solid",
    "borderWidth : 1px",
    "borderColor : #46535B",
    "opacity: 1"
  ],

  // // Set to false if wanting to remove the horizontal scope line that connects to the active indent
  // // guide.
  // "bracket-pair-colorizer-2.showHorizontalScopeLine": false,

  // Turn off built-in active indent guides since they aren't semantic (parent scope gets
  // highlighted in some scenarios).
  "editor.highlightActiveIndentGuide": false,
}
```

### Better Comments

```jsonc
{
  "better-comments.tags": [
    // Clearly mark comments that belong to disabled (commented-out) code.
    {
      "tag": "//",
      "color": "#546e7a",
      "strikethrough": true
    }
  ],
}
```

### Customize UI

```jsonc
{
  "customizeUI.stylesheet": {
    // NOTE: Hides icons in top right of an editor tab. Only enable if you're already familiar with
    // the editor icons, along with their functionality and keyboard shortcuts.
    ".editor-actions": "display: none !important",

    // TODO: Update `f07178` in the setting below with the hex color of your choice. This changes
    // the color of the circle that appears in a dirty file's editor tab.
    ".hc-black .monaco-workbench .part.editor>.content .editor-group-container>.title .tabs-container>.tab.close-button-off.dirty, .vs-dark .monaco-workbench .part.editor>.content .editor-group-container>.title .tabs-container>.tab.close-button-off.dirty:not(.dirty-border-top)": "background-image: url(\"data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' height='16' width='16'%3E%3Ccircle fill='%23f07178' cx='8' cy='8' r='4'/%3E%3C/svg%3E\") !important",
  },
}
```

### GitLens

```jsonc
{
  // Toggle from command palette as needed.
  "gitlens.codeLens.enabled": false,
  "gitlens.currentLine.enabled": false,

  // Keep source control tools in same view.
  "gitlens.views.compare.location": "scm",
  "gitlens.views.fileHistory.location": "scm",
  "gitlens.views.lineHistory.location": "scm",
  "gitlens.views.repositories.location": "scm",
  "gitlens.views.search.location": "scm",
}
```

### Macros

```jsonc
{
  // TODO: Add your own macros. Below are some examples to get you started. Execute these commands with the command palette, or assign them to keyboard shortcuts.
  // NOTE: Use in combination with the Settings Cycler settings listed further down this page.
  "macros.list": {
    // Toggle zoom setting and panel position when moving from laptop to external monitor and vice versa.
    "toggleDesktop": [
      "workbench.action.togglePanelPosition",
      "settings.cycle.desktopZoom",
    ],
    // Copy line and paste it below, comment out the original line, and move cursor down to the pasted line. Great for debugging/experimenting with code while keeping the original intact.
    "commentDown": [
      "editor.action.copyLinesDownAction",
      "cursorUp",
      "editor.action.addCommentLine",
      "cursorDown"
    ],
  },
}
```

### MetaGo

```jsonc
{
  // TODO: Update styling to fit your theme. The following works well with Material Theme.
  "metaGo.decoration.borderColor": "#253036",
  "metaGo.decoration.backgroundColor": "red, blue",
  "metaGo.decoration.backgroundOpacity": "1",
  "metaGo.decoration.color": "white",

  // TODO: Update font settings to fit your preference.
  "metaGo.decoration.fontFamily": "'Operator Mono SSm Lig', 'Fira Code', Menlo, Monaco, 'Courier New', monospace",
  "metaGo.decoration.fontWeight": "normal",

  "metaGo.jumper.timeout": 60,
}
```

### Project Manager

```jsonc
{
  // TODO: Add the folders where you keep your code projects at.
  "projectManager.any.baseFolders": [
    "$home/Code",
  ],

  "projectManager.any.maxDepthRecursion": 1,
  "projectManager.sortList": "Recent",
  "projectManager.removeCurrentProjectFromList": false,
}
```

### Rewrap

```jsonc
{
  "rewrap.autoWrap.enabled": true,
  "rewrap.reformat": true,
  "rewrap.wrappingColumn": 100,
}
```

### Settings Cycler

```jsonc
{
  // Use in combination with the Macro settings listed further up this page.
  "settings.cycle": [
    {
      "id": "desktopZoom",
      "values": [
        {
          "window.zoomLevel": 1,
        },
        {
          "window.zoomLevel": 1.4,
        }
      ]
    }
  ],
}
```

### Settings Sync

```jsonc
{
  "sync.quietSync": true,

  // TODO: Add your gist ID
  "sync.gist": "00000000000000000000000000000000",
}
```

### Subtle Brackets

```jsonc
{
  "subtleBrackets.parse": false,
  "subtleBrackets.pairs": [
    {
      "open": "(",
      "close": ")"
    },
    {
      "open": "[",
      "close": "]"
    },
    {
      "open": "{",
      "close": "}"
    },
    {
      "open": "<",
      "close": ">"
    },
  ],

  // TODO: Change border color to match the theme you're using.
  "subtleBrackets.style": {
    // Matches Material Theme cursor color.
    "borderColor": "#ffcc00",
  },

  // NOTE: Required for Subtle Brackets to work (removes native brackets).
  "editor.matchBrackets": false,
}
```

### Todo Tree

```jsonc
{
  "todo-tree.tags": [
    "TODO",
    "FIXME",
    "NOTE",
  ],

  "todo-tree.customHighlight": {
    "NOTE": {
      "icon": "note"
    },
    "FIXME": {
      "icon": "alert"
    }
  },

  "todo-tree.defaultHighlight": {
    "foreground": "#FFEB95"
  },

  "todo-tree.grouped": true,
  "todo-tree.hideIconsWhenGroupedByTag": true,
  "todo-tree.labelFormat": "∙ ${after}",
  "todo-tree.showCountsInTree": true,
  "todo-tree.showInExplorer": false,
  "todo-tree.showScanOpenFilesOrWorkspaceButton": true,
  "todo-tree.tagsOnly": true,
}
```

## Bug Reports

Bug reports should be filed at the repository belonging to the individual extension that is causing the issue (click on the extension's marketplace link below and then look for the repo link in the sidebar, under "Project Details").

## Included Extensions

| Extension | Link |
| --- | --- |
| Better Comments | [![Better Comments (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/aaron-bond.better-comments.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) |
| Bookmarks | [![Bookmarks (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/alefragnani.Bookmarks.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) |
| Bracket Pair Colorizer | [![Bracket Pair Colorizer (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/CoenraadS.bracket-pair-colorizer-2.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2) |
| Checkpoints | [![Checkpoints (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/micnil.vscode-checkpoints.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints) |
| Code Runner | [![Code Runner (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/formulahendry.code-runner.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner) |
| Code Spell Checker | [![Code Spell Checker (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/streetsidesoftware.code-spell-checker.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) |
| Control Snippets | [![Control Snippets (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/svipas.control-snippets.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=svipas.control-snippets) |
| Customize UI | [![Customize UI (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/iocave.customize-ui.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=iocave.customize-ui) |
| DotENV | [![DotENV (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/mikestead.dotenv.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv) |
| Easy Snippet | [![Easy Snippet (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/inu1255.easy-snippet.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=inu1255.easy-snippet) |
| Format All | [![Format All (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/lacroixdavid1.vscode-format-context-menu.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=lacroixdavid1.vscode-format-context-menu) |
| Git Graph | [![Git Graph (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/mhutchie.git-graph.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) |
| GitHub Pull Requests | [![GitHub Pull Requests (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/GitHub.vscode-pull-request-github.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) |
| Gitignore | [![Gitignore (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/codezombiech.gitignore.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=codezombiech.gitignore) |
| GitLens | [![GitLens (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/eamodio.gitlens.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) |
| Gremlins | [![Gremlins (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/nhoizey.gremlins.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=nhoizey.gremlins) |
| Hungry Delete | [![Hungry Delete (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/jasonlhy.hungry-delete.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=jasonlhy.hungry-delete) |
| IntelliCode | [![IntelliCode (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/VisualStudioExptTeam.vscodeintellicode.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode) |
| Live Share | [![Live Share (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/ms-vsliveshare.vsliveshare.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare) |
| Live Share Audio | [![Live Share Audio (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/ms-vsliveshare.vsliveshare-audio.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare-audio) |
| Live Share Chat | [![Live Share Chat (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/karigari.chat.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=karigari.chat) |
| Live Share Whiteboard | [![Live Share Whiteboard (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/lostintangent.vsls-whiteboard.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=lostintangent.vsls-whiteboard) |
| Local History | [![Local History (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/xyz.local-history.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=xyz.local-history) |
| Macros | [![Macros (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/ctf0.macros.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=ctf0.macros) |
| MetaGo | [![MetaGo (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/metaseed.metago.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=metaseed.metago) |
| Monkey Patch | [![Monkey Patch (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/iocave.monkey-patch.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=iocave.monkey-patch) |
| Multiple Clipboards | [![Multiple Clipboards (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/slevesque.vscode-multiclip.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=slevesque.vscode-multiclip) |
| PDF | [![PDF (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/tomoki1207.pdf.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=tomoki1207.pdf) |
| Polacode | [![Polacode (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/pnp.polacode.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=pnp.polacode) |
| Project Manager | [![Project Manager (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/alefragnani.project-manager.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager) |
| Rewrap | [![Rewrap (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/stkb.rewrap.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=stkb.rewrap) |
| Settings Cycler | [![Settings Cycler (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/hoovercj.vscode-settings-cycler.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=hoovercj.vscode-settings-cycler) |
| Settings Sync | [![Settings Sync (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/Shan.code-settings-sync.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync) |
| Subtle Match Brackets | [![Subtle Match Brackets (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/rafamel.subtle-brackets.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=rafamel.subtle-brackets) |
| Text Pastry | [![Text Pastry (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/jkjustjoshing.vscode-text-pastry.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=jkjustjoshing.vscode-text-pastry) |
| Todo Tree | [![Todo Tree (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/Gruntfuggly.todo-tree.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree) |
