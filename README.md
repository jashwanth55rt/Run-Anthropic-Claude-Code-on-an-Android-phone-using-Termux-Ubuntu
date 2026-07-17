# Claude Code on Android (Termux + Ubuntu)

Run **Anthropic Claude Code** on an Android phone using **Termux** and **Ubuntu (proot-distro)**.

> ⚠️ Native Termux is **not supported** because Claude Code does not provide a `linux-arm64-android` binary. Ubuntu (proot-distro) is required.

---

## ✨ Features

- 📱 Run Claude Code on Android
- 🐧 Ubuntu (proot-distro) setup
- ⚡ Latest Node.js installation
- 🤖 Claude Code installation
- 🔑 Optional FreeModel API configuration
- 🛠️ Easy step-by-step guide

---

## 📋 Requirements

- Android 10+
- Latest Termux
- Stable Internet Connection
- 2GB+ Free Storage
- Git

---

# Step 1 — Update Termux

```bash
pkg update && pkg upgrade -y
pkg install proot-distro git curl nano -y
```

---

# Step 2 — Install Ubuntu

```bash
proot-distro install ubuntu
```

Login:

```bash
proot-distro login ubuntu
```

---

# Step 3 — Install Node.js

```bash
apt update && apt upgrade -y

apt install -y curl git nano

curl -fsSL https://deb.nodesource.com/setup_22.x | bash -

apt install -y nodejs
```

Verify:

```bash
node -v
npm -v
```

---

# Step 4 — Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Verify installation:

```bash
claude --version
```

Expected output:

```
2.x.x (Claude Code)
```

---

# Step 5 — Configure FreeModel (Optional)

Create configuration:

```bash
mkdir -p ~/.claude

nano ~/.claude/settings.json
```

Example:

```json
{
  "env": {
    "ANTHROPIC_API_KEY": "YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://cc.freemodel.dev",
    "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1"
  }
}
```

Save the file.

---

# Step 6 — Start Claude Code

```bash
claude
```

---

# ⚠️ Native Termux Limitation

Native Termux currently cannot run Claude Code because Anthropic does not publish an Android binary.

Error:

```
Native binaries for linux-arm64-android are not available on this release channel.
```

Using **Ubuntu (proot-distro)** avoids this limitation.

---

# FreeModel

If you use FreeModel and receive:

```
API error
```

Check:

- API key is valid
- API endpoint is correct
- Your account has available API credits
- Your account is activated

Without available API credits, requests may fail.

---

# Tested Environment

- Android
- Termux
- Ubuntu (proot-distro)
- Node.js 22
- Claude Code 2.x

---

# Resources

## 🌐 Claude Code

https://github.com/anthropics/claude-code

## 🌐 FreeModel

https://freemodel.dev

---

# Community

📺 **YouTube**

https://www.youtube.com/@Infinitycodesfree

💬 **Telegram**

https://t.me/Infinitycodesfree

---

# License

This repository is provided for educational purposes. Claude Code is developed and maintained by Anthropic. Please review and follow Anthropic's official license and terms of use.

---

⭐ If this repository helped you, consider giving it a Star!
