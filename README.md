# VSCode Essentials (Extension Pack)

[![Inline (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/jabacchetta.vscode-essentials.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.vscode-essentials)
[![Inline (VSCode extension) installs badge](https://vsmarketplacebadge.apphb.com/installs-short/jabacchetta.vscode-essentials.svg?color=blue)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.vscode-essentials)
[![Inline (VSCode extension) rating badge](https://vsmarketplacebadge.apphb.com/rating-short/jabacchetta.vscode-essentials.svg?color=blue)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.vscode-essentials)
[![MIT license badge](https://img.shields.io/badge/license-MIT-orange.svg?color=blue)](http://opensource.org/licenses/MIT)

## VSCode Masterclass (Coming Soon)

Follow [on Twitter](https://twitter.com/devcastcode) and [subscribe at DevCast](https://www.devcast.app/) to get priority access.

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
* Extended multi-cursor functionality (incrementing, inserting numeric sequences, etc.)
* Hack VSCode's stylesheets for UI elements that aren't yet included in the settings or official theme API
* Semantic indent and scope guides
* Automatic and manually added (tagged commits) local edit history
* Bookmarks for marking lines of code and quickly jumping back to them
* Giving workspaces unique colors to help identify the editor when working with multiple instances, using Live Share, or taking advantage of remote development
* Add syntax highlighting to log files and to VSCode's output/debug panels
* Toggle the display of hidden files in the explorer
* GitHub Gist management with interactive playgrounds, code snippets, and notes
* Synchronize edits you make in a Search Editor back to source files.

## Recommended Settings

### All Autocomplete

```jsonc
{
  // // TODO: Add files that you want to be included in IntelliSense at all times.
  // // Enable to get autocomplete for the entire project (as opposed to just open files). It's a
  // // good idea to read the All Autocomplete extension's documentation to understand the performance
  // // impact of specific settings.
  // "AllAutocomplete.wordListFiles": ["/src/"],
}
```

### CodeStream

```jsonc
{
  "codestream.autoSignIn": false,
}
```

### Customize UI

```jsonc
{
  "customizeUI.stylesheet": {
    // NOTE: Only hide icons if you're already familiar with their functionality and shortcuts
    // Hides specific editor action icons
    ".editor-actions a[title^=\"Toggle File Blame Annotations\"]": "display: none !important;",
    ".editor-actions a[title^=\"Open Changes\"]": "display: none !important;",
    ".editor-actions a[title^=\"More Actions...\"]": "display: none !important;",
    ".editor-actions a[title^=\"Split Editor Right (⌘\\\\)\"]": "display: none !important;",
    ".editor-actions a[title^=\"Run Code (⌃⌥N)\"]": "display: none !important;",

    // Adds a border below the sidebar title.
    // TODO: Update `19252B` in the setting below with the hex color of your choice.
    ".sidebar .composite.title": "border-bottom: 1px solid #19252B;",

    // Leaves only the bottom border on matching bracket border.
    ".monaco-editor .bracket-match": "border-top: none; border-right: none; border-left: none;",

    // Changes color of the circle that appears in a dirty file's editor tab.
    // TODO: Update `00bcd480` in the setting below with the hex color of your choice.
    ".monaco-workbench .part.editor>.content .editor-group-container.active>.title .tabs-container>.tab.dirty>.tab-close .action-label:not(:hover):before, .monaco-workbench .part.editor>.content .editor-group-container>.title .tabs-container>.tab.dirty>.tab-close .action-label:not(:hover):before": "color: #00bcd480;",
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

### Todo Tree

```jsonc
{
  "todo-tree.highlights.customHighlight": {
      "TODO": {
        "foreground": "#FFEB95",
      },
      "NOTE": {
        "foreground": "#FFEB95",
        "icon": "note",
      },
      "FIXME": {
        "foreground": "#FFEB95",
        "icon": "alert",
      },

      // Clearly mark comments that belong to disabled (commented-out) code.
      "// //": {
        "foreground": "#5d7783",
        "textDecoration": "line-through",
        "type": "text",
        "hideFromTree": true,
      },
  },

  "todo-tree.tree.grouped": true,
  "todo-tree.tree.hideIconsWhenGroupedByTag": true,
  "todo-tree.tree.labelFormat": "∙ ${after}",
  "todo-tree.tree.showCountsInTree": true,
  "todo-tree.tree.showInExplorer": false,
  "todo-tree.tree.showScanOpenFilesOrWorkspaceButton": true,
  "todo-tree.tree.tagsOnly": true,
  "todo-tree.highlights.highlightDelay": 0,
  "todo-tree.general.tags": [
    "TODO",
    "FIXME",
    "NOTE",
    "// //",
  ],

  // Allow for matches inside of VSCode files (e.g. `settings.json`).
  "todo-tree.highlights.schemes": [
    "file",
    "untitled",
    "vscode-userdata",
  ],

  // Allows for matches inside of JSDoc comments.
  "todo-tree.regex.regex": "((\\*|//|#|<!--|;|/\\*|^)\\s*($TAGS)|^\\s*- \\[ \\])",
}
```

## Bug Reports

Bug reports should be filed at the repository belonging to the individual extension that is causing the issue (click on the extension's marketplace link below and then look for the repo link in the sidebar, under "Project Details").

## Known Issues

Some extensions will prevent the Output Colorizer extension from adding syntax highlighting in the output/debug panels. This is a VSCode limitation waiting for a fix. The current workaround is to disable extensions (when not needed) that conflict with the Output Colorizer extension. Code Runner is one of the known, conflicting extensions (which itself is also included in this extension pack).

## Included Extensions

| Extension | Link |
| --- | --- |
| All Autocomplete | [![All Autocomplete (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/Atishay-Jain.All-Autocomplete.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=Atishay-Jain.All-Autocomplete) |
| Bookmarks | [![Bookmarks (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/alefragnani.Bookmarks.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) |
| Checkpoints | [![Checkpoints (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/micnil.vscode-checkpoints.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints) |
| Code Runner | [![Code Runner (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/formulahendry.code-runner.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner) |
| Code Spell Checker | [![Code Spell Checker (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/streetsidesoftware.code-spell-checker.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) |
| CodeStream | [![CodeStream (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/CodeStream.codestream.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=CodeStream.codestream) |
| Control Snippets | [![Control Snippets (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/svipas.control-snippets.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=svipas.control-snippets) |
| Customize UI | [![Customize UI (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/iocave.customize-ui.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=iocave.customize-ui) |
| DotENV | [![DotENV (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/mikestead.dotenv.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv) |
| Easy Snippet | [![Easy Snippet (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/inu1255.easy-snippet.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=inu1255.easy-snippet) |
| Explorer Exclude | [![Explorer Exclude (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/RedVanWorkshop.explorer-exclude-vscode-extension.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=RedVanWorkshop.explorer-exclude-vscode-extension) |
| Format All | [![Format All (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/lacroixdavid1.vscode-format-context-menu.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=lacroixdavid1.vscode-format-context-menu) |
| GistPad | [![GistPad (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/vsls-contrib.gistfs.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=vsls-contrib.gistfs) |
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
| Output Colorizer | [![Output Colorizer (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/IBM.output-colorizer.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer) |
| PDF | [![PDF (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/tomoki1207.pdf.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=tomoki1207.pdf) |
| Peacock | [![Peacock (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/johnpapa.vscode-peacock.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=johnpapa.vscode-peacock) |
| Polacode | [![Polacode (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/pnp.polacode.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=pnp.polacode) |
| Project Manager | [![Project Manager (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/alefragnani.project-manager.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager) |
| Rewrap | [![Rewrap (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/stkb.rewrap.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=stkb.rewrap) |
| Search Editor: Apply Changes | [![Search Editor: Apply Changes (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/stkb.rewrap.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=jakearl.search-editor-apply-changes) |
| Settings Cycler | [![Settings Cycler (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/hoovercj.vscode-settings-cycler.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=hoovercj.vscode-settings-cycler) |
| Text Pastry | [![Text Pastry (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/jkjustjoshing.vscode-text-pastry.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=jkjustjoshing.vscode-text-pastry) |
| Todo Tree | [![Todo Tree (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/Gruntfuggly.todo-tree.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree) |
