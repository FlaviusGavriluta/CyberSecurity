# Mentalist Installation Guide (macOS)

This guide installs **Mentalist** with working GUI (Tk) on macOS.

## Requirements
- macOS
- Homebrew

## Install steps

## 1) Install Python 3.11 and Tk
brew install python@3.11
brew install tcl-tk

## 2) Ensure Tcl/Tk is discoverable (add to shell RC if needed)
echo 'export PATH="/usr/local/opt/tcl-tk/bin:$PATH"' >> ~/.zshrc
echo 'export LDFLAGS="-L/usr/local/opt/tcl-tk/lib"' >> ~/.zshrc
echo 'export CPPFLAGS="-I/usr/local/opt/tcl-tk/include"' >> ~/.zshrc
source ~/.zshrc

## 3) Create project directory and clone Mentalist
mkdir -p ~/CyberSecurity
cd ~/CyberSecurity
git clone https://github.com/sc0tfree/mentalist.git mentalist
cd mentalist

## 4) Create and activate a venv using Python 3.11
python3.11 -m venv ../.mentalist-venv
source ../.mentalist-venv/bin/activate

```bash
mentalist $ cd ~/CyberSecurity
rm -rf .venv
python3.11 -m venv .venv
source .venv/bin/activate
```

## 5) Upgrade pip and install requirements, then install Mentalist
```bash
(.venv) CyberSecurity $ cd ~/CyberSecurity/mentalist
pip install --upgrade pip setuptools wheel
```
## if requirements.txt exists:
```bash
pip install -r requirements.txt || true python3.11 setup.py install
```

## 6) Run Mentalist (GUI)
```bash
(.venv) mentalist $ mentalist
```

## fallback:
```bash
python3.11 -m mentalist
```

## 7) Unninstall
```bash
rm -rf ~/CyberSecurity/mentalist ~/CyberSecurity/.mentalist-venv
```
