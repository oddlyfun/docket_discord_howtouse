# MTG Cube Docket Bot

A Discord bot for organizing cube nights. Players can add cubes to a shared docket, mark which cube they most want to play, generate sample packs from CubeCobra, and keep the list fresh from week to week.

## What The Docket Is

The docket is the current list of cubes available for a cube night in a Discord channel. Each channel gets its own docket, so different groups or channels can run separate lists.

Each cube entry can include:

- Cube name
- CubeCobra link, when the bot can find one
- Person who added the cube
- Optional notes
- Players who marked that cube as one they really want to play

The docket is meant to answer a simple question: “What could we draft tonight, and who is especially interested in what?”

## Basic Commands

| Command | What It Does | Example |
|---------|--------------|---------|
| `!add [cube]` | Adds a cube to the docket | `!add Turbo Cube` |
| `!add [cube] !note [notes]` | Adds a cube with notes | `!add Turbo Cube !note Updated list this week` |
| `!remove [cube]` | Removes a cube you added | `!remove Turbo Cube` |
| `!rem [cube]` | Short version of `!remove` | `!rem Turbo Cube` |
| `!docket` | Shows the current docket | `!docket` |
| `!pack [cube] [size]` | Generates a random pack image from a CubeCobra cube | `!pack turbo 15` |
| `!co [cube] [size]` | Short version of `!pack` | `!co turbo 15` |
| `!help` | Shows command help in Discord | `!help` |

## Adding A Cube

Use `!add` followed by a CubeCobra ID, short ID, or cube name.

```text
!add turbo
```

If the bot finds the cube on CubeCobra, it will use the official cube name and link it in the docket.

You can include notes with `!note`:

```text
!add turbo !note Trying the new blue package tonight
```

Notes are useful for things like:

- Recent updates
- Special rules
- “Last chance before I rebuild this”
- Power level or player count reminders

## Adding A Cube For Someone Else

You can mention another user when adding a cube:

```text
!add @Anthony turbo
```

The cube will be listed under that person instead of you.

## Removing A Cube

Use `!remove` or `!rem`:

```text
!remove turbo
```

Players can remove cubes they added. Server admins can remove any cube.

There is also a **Remove Cube** button on the docket. That button removes your own cube from the current channel’s docket.

## Viewing The Docket

Use `!docket`:

```text
!docket
```

The bot keeps track of the current docket message. When commands update the docket, the bot tries to remove the older docket message and post a fresh one near the current conversation.

## Want To Play

The docket message includes a **Want to Play** button.

Use this when there is one cube you especially want to draft. The bot will show a private dropdown where you can choose a cube from the current docket.

Each player can mark interest in one cube at a time. Each cube can show up to four interested players.

If you already marked a cube, pressing **Want to Play** again will let you remove your interest.

## Add Cube Button

The docket message also includes an **Add Cube** button. This opens a form where you can enter:

- Cube name or CubeCobra ID
- Optional notes

This is the button version of `!add`.

## Generating A Sample Pack

Use `!pack` with a CubeCobra ID or short ID and a pack size:

```text
!pack turbo 15
```

The bot will fetch cards from CubeCobra and post a stitched image of a random pack.

The short command is `!co`:

```text
!co compost 15
```

Pack size is capped at 25.

## Resetting The Docket

Admins can reset the current channel’s docket:

```text
!reset
```

The bot also has an automatic weekly reset. When a docket is reset, current entries are archived so cube history can be reviewed later.

## Good Docket Etiquette

- Add only cubes you are realistically willing to play that session.
- Use notes when a cube has special rules, unusual power level, or recent changes.
- Remove your cube if you leave or no longer want it considered.
- Use **Want to Play** as a preference signal, not a reservation system.
- Run `!docket` when the conversation has moved and people need a fresh view of the list.

## Common Examples

Add a CubeCobra cube by short ID:

```text
!add turbo
```

Add a cube with notes:

```text
!add The Compost Cube !note Last run before updates
```

Show the docket:

```text
!docket
```

Remove your cube:

```text
!rem The Compost Cube
```

Generate a 15-card pack:

```text
!pack compost 15
```
