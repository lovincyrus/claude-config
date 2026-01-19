# Workflows

## Setting up on a new machine

```bash
git clone git@github.com:brianlovin/claude-config.git ~/Developer/claude-config
cd ~/Developer/claude-config
./install.sh
```

Creates symlinks from `~/.claude/` to this repo. Local-only skills are preserved.

## Sync status legend

```bash
./sync.sh
```

- `✓` synced (symlinked to this repo)
- `○` local only (not in repo)
- `⚠` conflict (exists in both - run `./install.sh` to fix)

## Adding a skill to sync across machines

```bash
./sync.sh add <skill-name>
./sync.sh push
```

Copies the skill to repo, replaces local with symlink, prompts for commit.

## Removing a skill from repo

```bash
./sync.sh remove <skill-name>
./sync.sh push
```

Removes from repo but keeps local copy.

## Keeping skills local-only

Any skill in `~/.claude/skills/` that isn't symlinked stays local. The install script only creates symlinks for what's in this repo—it never deletes local files.

Use this for work-specific or experimental skills.
