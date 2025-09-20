# 🎮 Minecraft APIs - Collection

A comprehensive collection of useful APIs for developers working with Minecraft. From skin rendering to server data and player information.

## 📋 Table of Contents

- [🧑‍💼 User and Skin APIs](#-user-and-skin-apis)
- [🖼️ Skin Rendering APIs](#️-skin-rendering-apis)
- [🖥️ Server Status APIs](#️-server-status-apis)
- [📊 Statistics APIs](#-statistics-apis)
- [📱 Third-Party APIs](#-third-party-apis)

---

## 🧑‍💼 User and Skin APIs

### Mojang API - User Information
```
GET https://api.mojang.com/users/profiles/minecraft/{username}
```
Gets a player's UUID by their username.

**Response example:**
```json
{
  "id": "069a79f444e94726a5befca90e38aaf5",
  "name": "Notch"
}
```

### UUID to Profile
```
GET https://sessionserver.mojang.com/session/minecraft/profile/{uuid}
```
Gets detailed profile information including textures.

---

## 🖼️ Skin Rendering APIs

### Crafatar - Skin Rendering
Base URL: `https://crafatar.com`

**Avatar (face):**
```
GET https://crafatar.com/avatars/{uuid}?size=128&overlay
```

**Full body:**
```
GET https://crafatar.com/renders/body/{uuid}?size=512&overlay
```

**3D head:**
```
GET https://crafatar.com/renders/head/{uuid}?size=256&overlay
```

**Full skin:**
```
GET https://crafatar.com/skins/{uuid}
```

### MC-Heads.net
Base URL: `https://mc-heads.net`

**Avatar:**
```
GET https://mc-heads.net/avatar/{uuid}/{size}
```

**Body:**
```
GET https://mc-heads.net/body/{uuid}/{size}
```

### Visage - Advanced Rendering
Base URL: `https://visage.surgeplay.com`

**Face:**
```
GET https://visage.surgeplay.com/face/{size}/{uuid}.png
```

**Full body:**
```
GET https://visage.surgeplay.com/full/{size}/{uuid}.png
```

**Bust:**
```
GET https://visage.surgeplay.com/bust/{size}/{uuid}.png
```

---

## 🖥️ Server Status APIs

### Minecraft Server Status API
```
GET https://api.mcsrvstat.us/3/{server_address}
```

**Example:**
```bash
curl https://api.mcsrvstat.us/3/hypixel.net
```

### McStatus API
```
GET https://api.mcstatus.io/v2/status/java/{server_address}
```
---

## 📊 Statistics APIs

### Hypixel API
```
GET https://api.hypixel.net/player?uuid={uuid}&key={api_key}
```

### PlanckeAPI (Hypixel Stats)
```
GET https://plancke.io/hypixel/player/stats/{uuid}
```

### NameMC API
```
GET https://api.namemc.com/profile/{uuid}
```

---

## 📱 Third-Party APIs

### MCApi.us
```
GET https://mcapi.us/server/status?ip={server_address}
```

### MC-API.net
```
GET https://mc-api.net/v3/server/ping/{server_address}
```

### MinecraftSkinChecker
```
GET https://minecraftskinchecker.com/api/skin/{username}
```

### BlockyTalky
```
GET https://blockytalky.com/api/player/{uuid}
```

---

## 🔗 Usage Examples

### Get and render player skin

```javascript
// 1. Get player UUID
const username = "Notch";
const uuidResponse = await fetch(`https://api.mojang.com/users/profiles/minecraft/${username}`);
const playerData = await uuidResponse.json();
const uuid = playerData.id;

// 2. Get avatar image
const avatarUrl = `https://crafatar.com/avatars/${uuid}?size=128&overlay`;

// 3. Get full body
const bodyUrl = `https://crafatar.com/renders/body/${uuid}?size=512&overlay`;
```

### Check server status

```javascript
const serverAddress = "hypixel.net";
const response = await fetch(`https://api.mcsrvstat.us/3/${serverAddress}`);
const serverData = await response.json();

console.log(`Server: ${serverData.hostname}`);
console.log(`Online: ${serverData.online}`);
console.log(`Players: ${serverData.players.online}/${serverData.players.max}`);
```

---

## 🤝 Contributing

Know more useful APIs? Contribute to this list!

## 📄 License

This list is public domain. Use it freely in your projects.