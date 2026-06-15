# docket_discord_howtouse

# MTG Cube Night Bot

A Discord bot for coordinating Magic: The Gathering cube contributions for weekly Cube Night sessions.

## Features

- ⚡ **Add Cubes**: Users can register their MTG cubes for Cube Night
- 🗑️ **Remove Cubes**: Users can remove cubes they added from the list  
- 📋 **View Cube List**: Anyone can view cubes signed up for Cube Night
- 🔄 **Reset List**: Server admins can manually reset the cube list
- ⏰ **Auto Reset**: List automatically resets weekly (Wednesdays at midnight)
- 🛡️ **Permission Control**: Only cube contributors or admins can remove cubes

## Commands

| Command | Description | Example |
|---------|-------------|---------|
| `!add [cube name] !note [optional notes]` | Add your cube to Cube Night | `!add Vintage Cube !note New changes this week` |
| `!remove [cube name]` / `!rem [cube name]` | Remove a cube you added | `!remove Vintage Cube` |
| `!list` / `!docket` / `!dock` | Show cubes signed up for Cube Night | `!docket` |
| `!reset` | Reset the entire cube list (Admin only) | `!reset` |
| `!pack [cube name] [pack size]` / `!co` | Generate a random CubeCobra pack image | `!pack turbo 15` |
| `!help` | Show help information | `!help` |

