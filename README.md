# EuroLobby

Simple Spigot lobby plugin that awards silent join points, provides a shop and head-search minigame, and adds lobby protections and a scoreboard.

**Features**
- Silent join points (configurable)
- Shop GUI and right-click item effects
- Head-search minigame with claim persistence
- Simple join message and optional visuals (particles, sounds, title)
- Lobby protection toggles (block place/break, damage, drop, hunger)
- Scoreboard showing points

**Installation**
- Build with Maven: `mvn package -DskipTests`
- Place the generated JAR from `target/` into your server's `plugins/` folder
- Start/restart server

**Configuration**
Edit `src/main/resources/config.yml` in the project or the generated plugin folder after first run.

Important config keys:
- `teleport-on-join` (boolean)
- `join-points` (int) — points awarded on join (silent)
- `head-search.points` (int) — points per head found
- `scoreboard.enabled` (boolean)
- `lobby-protection.*` — protection toggles
- `lobby-visuals.*` — particles, join-sound, join-title
- `lobby-spawn.*` — world, x, y, z, yaw, pitch

**Commands**
- `lobbypoints` — show your points
- `lobbyshop` (`/shop`) — open the lobby shop
- `setlobby` — set lobby spawn (permission `eurolobby.admin`)
- `setheadpoints` — set head-search points (permission `eurolobby.admin`)
- `setlobbypoint` — set a player's points (permission `eurolobby.admin`)
- `addlobbypoint` — add points to a player (permission `eurolobby.admin`)
- `lobbyentityclear` — clear certain lobby entities (permission `eurolobby.admin`)
- `resetheads` — reset head claims for everyone or a single player (permission `eurolobby.admin`)

**Permissions**
- `eurolobby.admin` — required for admin commands (setlobby, setheadpoints, setlobbypoint, addlobbypoint, lobbyentityclear, resetheads)

**Build from source**
1. Clone or open this project in your IDE
2. Run:

```bash
mvn package -DskipTests
```

3. The plugin JAR will be at `target/EuroLobby-1.0.0.jar` (or similar)

**Notes**
- Config changes in the plugin's data folder will persist between runs; edit `config.yml` in `plugins/EuroLobby/` after first start.
