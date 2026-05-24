# 🔔 Redeem Popup

A lightweight Twitch channel points redemption popup overlay for OBS. Displays a styled notification card whenever a viewer redeems any (or a specific) channel points reward — live on stream.

**Live:** [`dexteritycs.github.io/redeem-popup/`](https://dexteritycs.github.io/redeem-popup/)

---

## Features

- Real-time redemption alerts via Twitch EventSub WebSocket
- Shows redeemer's username, reward name, and optional user input
- Smooth slide-in / slide-out animation
- Optional reward name filter — show popups only for specific rewards
- Credentials persist in URL hash — no re-login needed in SLOBS
- Twitch-purple accent theme, easily reskinned via CSS variables

---

## Setup

### 1. Create a Twitch App

1. Go to [dev.twitch.tv/console](https://dev.twitch.tv/console)
2. Register a new application
3. Set OAuth Redirect URL to: `https://dexteritycs.github.io/redeem-popup/`
4. Copy your **Client ID**

### 2. Configure the Widget

1. Open `https://dexteritycs.github.io/redeem-popup/?config=1` in Chrome
2. Enter your **Client ID** and **Twitch channel name**
3. Click **Connect with Twitch** and authorize
4. (Optional) Enter a reward name filter to only show popups for specific rewards
5. Click **Save & Apply**

### 3. Add to OBS / Streamlabs

1. Add a **Browser Source**
2. URL: the full URL with hash token (copy it from the config page after saving)
3. Width: `500` | Height: `150`
4. Position it in a corner of your scene — transparent background

---

## Tech

- Vanilla HTML/CSS/JS — no dependencies, no server
- Twitch EventSub WebSocket (`channel.channel_points_custom_reward_redemption.add`)
- Twitch OAuth Implicit Grant (token in URL hash for SLOBS compatibility)
