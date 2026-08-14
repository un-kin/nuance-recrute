# Nuance-recrute

## KARIMO plugin

This project uses [KARIMO](https://github.com/opensesh/KARIMO) — a PRD-driven
autonomous agent-orchestration plugin for Claude Code
("you are the architect, agents are the builders").

KARIMO is wired into this repo through `.claude/settings.json`, which
registers the KARIMO marketplace and enables the `karimo` plugin. The
marketplace is registered automatically when you trust this repo, but the
plugin itself needs a **one-time install per machine**:

```
/plugin install karimo@karimo
/reload-plugins
```

If the marketplace isn't picked up automatically, register it first:

```
/plugin marketplace add opensesh/KARIMO
/plugin install karimo@karimo
```

Then verify and configure:

```
/karimo:doctor       # verify installation health
/karimo:configure    # detect project + populate GitHub settings
```

### Your first feature

```
/karimo:research "feature-name"   # create PRD folder + run research
/karimo:plan  --prd {slug}        # interactive PRD creation
/karimo:run   --prd {slug}        # execute tasks in waves
/karimo:merge --prd {slug}        # final PR to main
```

**Commands:** type `/karimo:` to list them all.
**Prerequisites:** Claude Code, GitHub CLI (`gh auth login`), Git 2.5+.
**Docs & source:** https://github.com/opensesh/KARIMO

> Prefer a fully self-contained (vendored) copy of the plugin instead of the
> marketplace reference? Run KARIMO's installer locally:
> `git clone https://github.com/opensesh/KARIMO && bash KARIMO/.karimo/install.sh .`
