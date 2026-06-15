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

| Command                      | What It Does                                        | Example                                        |
| ---------------------------- | --------------------------------------------------- | ---------------------------------------------- |
| `!add [cube]`                | Adds a cube to the docket                           | `!add Turbo Cube`                              |
| `!add [cube] !note [notes]`  | Adds a cube with notes                              | `!add Turbo Cube !note Updated list this week` |
| `!remove [cube]`             | Removes a cube you added                            | `!remove Turbo Cube`                           |
| `!docket`                    | Shows the current docket                            | `!docket`                                      |
| `!pack [cube] [size]`        | Generates a random pack image from a CubeCobra cube | `!pack turbo 15`                               |
| `!setreset [day] [timezone]` | Sets this channel's weekly midnight reset           | `!setreset Tuesday ET`                         |
| `!help`                      | Shows command help in Discord                       | `!help`                                        |

## Admin Setup: Set The Weekly Reset

If you are setting up the bot for a server or channel, start here:

```text
!setreset Tuesday ET
```

This is strongly recommended. Cubes stay on the docket until either an admin runs `!reset` or a scheduled reset runs. If no reset is configured, last week's cubes will remain visible and players may not know whether the docket is current.

Use the day your cube night happens. The bot resets at midnight after that day in the timezone you choose. For example, `!setreset Tuesday ET` resets after Tuesday cube night in Eastern time.

Common timezone shortcuts:

- `ET` or `Eastern`
- `CT` or `Central`
- `MT` or `Mountain`
- `PT` or `Pacific`

Admins can check the current reset schedule with `!help`, and can see supported timezone shortcuts with:

```text
!setreset timezones
```

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

## Add Cube Button

The docket message also includes an **Add Cube** button. This opens a form where you can enter:

- Cube name or CubeCobra ID
- Optional notes

This is the button version of `!add`.

## Removing A Cube

Use `!remove`:

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

## Generating A Sample Pack

Use `!pack` with a CubeCobra ID or short ID and a pack size:

```text
!pack turbo 15
```

The bot will fetch cards from CubeCobra and post a stitched image of a random pack.

Pack size is capped at 25.

## Resetting The Docket

Admins can reset the current channel's docket immediately:

```text
!reset
```

To turn off the scheduled reset for a channel:

```text
!setreset off
```

When a docket is reset, current entries are archived so cube history can be reviewed later.

## Common Examples

Add a CubeCobra cube by short ID:

```text
!add redterror
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
!remove The Compost Cube
```

Generate a 15-card pack:

```text
!pack compost 15
```
