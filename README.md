# GitP - Multi-Repository Git Manager

K9s-style TUI for managing git operations across multiple repositories.

## Installation

```bash
cargo build --release
ln -sf $(pwd)/target/release/gitp ~/.local/bin/gitp
```

Make sure `~/.local/bin` is in your PATH:
```bash
export PATH="$HOME/.local/bin:$PATH"
```

## Usage

Navigate to a directory containing git repositories and run:
```bash
gitp
```

## Features

- **Auto-refresh**: Status updates every 5 seconds
- **Color-coded status**: Visual indicators for repo state
  - ✓ Green: Clean and synced
  - ● Yellow: Uncommitted changes
  - ↑ Blue: Ahead of remote
  - ↓ Magenta: Behind remote
  - ⇅ Red: Diverged from remote
- **Rich information**: Branch name, ahead/behind counts, file changes
- **Direct actions**: No selection needed, acts on current repo
- **Filtering**: Quick filter by status
- **Split view**: Repos on left, output on right

## Keyboard Shortcuts

### Navigation
- **↑/↓** - Navigate between repositories
- **Enter** - Show detailed status for current repo

### Git Operations
- **p** - Pull current repository
- **P** - Pull ALL repositories
- **f** - Fetch current repository
- **F** - Fetch ALL repositories
- **l** - Show logs (last 10 commits)
- **d** - Show diff for current repo
- **s** - Show detailed status

### Filters
- **1** - All repositories
- **2** - Dirty repositories only (uncommitted changes)
- **3** - Sync issues only (ahead/behind)
- **4** - Clean repositories only

### Other
- **r** - Manual refresh
- **q** - Quit

## Display Format

```
✓ repo-name | main ↑2↓1 +1 ~3 ?2
│           │    │   │   │  │  └─ Untracked files
│           │    │   │   │  └──── Modified files
│           │    │   │   └─────── Staged files
│           │    │   └─────────── Behind count
│           │    └───────────────── Ahead count
│           └────────────────────── Branch name
└────────────────────────────────── Status symbol
```
