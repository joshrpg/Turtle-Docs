# PaperMC Settings

## spigot.yml

Change the following settings:

**Note:** Don't add the setting if it isn't present as the PaperMC Dev's may have removed it.

```yaml
world-settings:
  default:
    entity-tracking-range:
      players: 98
      animals: 98
      monsters: 98
      misc: 32
      other: 64
```

## bukkit.yml

Change the following settings:

**Note:** Don't add the setting if it isn't present as the PaperMC Dev's may have removed it.

```yaml
settings:
    connection-throttle: -1
```

## paper.yml

Change the following settings:

**Note:** Don't add the setting if it isn't present as the PaperMC Dev's may have removed it.

### 1.16.1

```yaml
world-settings:
  default:
    allow-non-player-entities-on-scoreboards: true
    keep-spawn-loaded: true
    per-player-mob-spawns: true
    phantoms-only-attack-insomniacs: true
    use-vanilla-world-scoreboard-name-coloring: true
    anti-xray:
        enabled: true
```

### 1.15.2

```yaml
world-settings:
  default:
    allow-leashing-undead-horse: true
    allow-non-player-entities-on-scoreboards: true
    fix-zero-tick-instant-grow-farms: true
    keep-spawn-loaded: true
    per-player-mob-spawns: true
    phantoms-only-attack-insomniacs: false
    use-faster-eigencraft-redstone: false
    use-vanilla-world-scoreboard-name-coloring: true
    anti-xray:
        enabled: true
```
