# 📱 Termux Mobile Dev Toolkit

> Everything you need to code from your phone. No laptop required.

![Made with Termux](https://img.shields.io/badge/Made%20with-Termux-6a0dad?style=for-the-badge&logo=android&logoColor=white)
![Mobile Dev](https://img.shields.io/badge/Mobile-Developer-7b2d8b?style=for-the-badge&logo=android&logoColor=white)
![No Laptop](https://img.shields.io/badge/No%20Laptop-No%20Problem-9b59b6?style=for-the-badge&logoColor=white)

---

## 🚀 Getting Started

### Install Termux
Download from **F-Droid** (not Play Store — the Play Store version is outdated and broken)
- [F-Droid Download](https://f-droid.org/packages/com.termux/)

### First thing after install
```bash
pkg update && pkg upgrade
pkg install git curl wget nano
```

---

## 📦 Essential Package Installation

### Node.js & npm
```bash
pkg install nodejs
node --version
npm --version
```

### Python
```bash
pkg install python
pip install --upgrade pip
```

### Git
```bash
pkg install git
git config --global user.name "YourName"
git config --global user.email "your@email.com"
```

### SSH
```bash
pkg install openssh
ssh-keygen -t ed25519 -C "your@email.com"
cat ~/.ssh/id_ed25519.pub
# copy this and add to GitHub SSH keys
```

---

## 🔧 ADB (Android Debug Bridge)

### Install ADB in Termux
```bash
pkg install android-tools
```

### Wireless ADB Setup (Phone to Phone)
Enable developer options on target phone:
- Settings → About Phone → tap Build Number 7 times
- Enable USB Debugging
- Enable Wireless ADB debugging

```bash
# connect wirelessly
adb connect <IP_ADDRESS>:<PORT>

# check connected devices
adb devices

# list installed packages
adb shell pm list packages

# debloat (remove bloatware without root)
adb shell pm uninstall --user 0 com.package.name
```

### Useful ADB Debloat Commands
```bash
# disable instead of uninstall (safer)
adb shell pm disable-user --user 0 com.package.name

# re-enable if needed
adb shell pm enable com.package.name

# get device info
adb shell getprop ro.product.model
```

---

## 🤖 AI Development

### Install Ollama (run LLMs locally)
```bash
pkg install ollama
ollama serve &
ollama pull tinyllama
ollama run tinyllama
```

### Claude Code (AI coding assistant)
```bash
pkg install nodejs
npm install -g @anthropic-ai/claude-code
claude
```

### Run Node.js Projects
```bash
git clone https://github.com/yourrepo
cd yourrepo
npm install
npm start
```

---

## 🌐 Networking & APIs

### Test APIs with curl
```bash
# GET request
curl https://api.example.com/endpoint

# POST request with JSON
curl -X POST https://api.example.com/endpoint \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_KEY" \
  -d '{"key": "value"}'
```

### Check your IP
```bash
curl ifconfig.me
```

### Port forwarding with SSH tunnel
```bash
ssh -L 3000:localhost:3000 user@server
```

---

## 📁 File Management

### Navigate & manage files
```bash
ls -la          # list all files
cd ~            # go home
mkdir projects  # create folder
cp file1 file2  # copy
mv file1 file2  # move/rename
rm file         # delete file
rm -rf folder   # delete folder
```

### Edit files
```bash
nano filename   # simple editor
# Ctrl+X to exit, Y to save
```

### Storage access
```bash
termux-setup-storage
# then access phone storage at ~/storage/
```

---

## ⚡ Useful Shortcuts & Tips

### Run scripts in background
```bash
nohup node index.js &
# keeps running after terminal closes
```

### Check what's running
```bash
ps aux
```

### Kill a process
```bash
kill <PID>
```

### Environment variables
```bash
export API_KEY="your_key_here"
echo $API_KEY

# make permanent
echo 'export API_KEY="your_key"' >> ~/.bashrc
source ~/.bashrc
```

### Check storage space
```bash
df -h
```

---

## 🔋 Battery & Performance Tips

- Use `nohup` to keep processes running when screen is off
- Disable battery optimization for Termux in phone settings
- For heavy tasks, keep phone plugged in
- Use `tmux` to keep sessions alive

```bash
pkg install tmux
tmux new -s main
# Ctrl+B then D to detach
tmux attach -t main
```

---

## 📲 Tested On

![potato mobile gpc](https://img.shields.io/badge/potato-8%20GPU-6a0dad?style=for-the-badge&logoColor=white)
![Potato Phone](https://img.shields.io/badge/Also%20works%20on-Potato%20Phone%20🥔-7b2d8b?style=for-the-badge&logo=android&logoColor=white)

---

## 🦞 Built by

[![GitHub](https://img.shields.io/badge/GitHub-Yuri--code--dot-9b59b6?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Yuri-code-dot)
[![Moltbook](https://img.shields.io/badge/Moltbook-u%2Ftensora-6a0dad?style=for-the-badge&logoColor=white)](https://www.moltbook.com/u/tensora)

> *"building things from a phone. no laptop. no excuses."*
