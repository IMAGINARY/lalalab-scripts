- Installed Ubuntu 18.04.2 LTS
- Minimal Install
    + Download updates while installing Ubuntu : ON
    + Install third-party software for graphics and WiFi hardware... : ON
    + Configure secure boot: ON. (set a password set needs to be entered on first boot)
    + Time zone
    + Name, password, login automatically
- Boot
- `sudo apt update`
- Settings
    + Notifications
        * Notifications popups: pff
        * Lock screen notifications: off
    + Power
        * Power saving
            - Blank screen: Never
            - Turn off WiFi: OFF
            - Turn off Bluetooth: OFF
        * Suspend and power button
            - Automatic suspend: Off
- `sudo apt upgrade`
- `sudo apt install openbox`
- `sudo reboot`
- Logout
- Log in into Openbox
- Copy the kiosk browser .deb package
    + Install the package
        + `sudo dpkg -i kiosk-browser_0.10_0_amd64.deb`
    + Fix unmet dependencies
        + `sudo apt --fix-broken install`
    + Fix permissions because only root has access
        + `sudo chmod -R ag+rx /opt/kiosk-browser`
- `sudo apt install git`
- `sudo apt install qjackctl kmidimon vmpk qsynth aconnectgui pavucontrol`
- `sudo apt install feh`
- `sudo apt install htop`

## xbanish (hide mouse)

Rebuild if necessary:

```
sudo apt install build-essential libx11-dev libxt-dev libxfixes-dev libxi-dev
cd "$HOME"
git clone https://github.com/IMAGINARY/xbanish-hide  
cd xbanish-hide/
make
cp xbanish ~/bin/
```

## La La Lab Scripts

```
  cd "$HOME"
  mkdir repos
  cd repos/
  git clone https://github.com/IMAGINARY/lalalab-scripts.git
  cd lalalab-scripts
  ./install.sh
```

Add ~/bin to PATH:

`echo -e '# set PATH so it includes user'"'"'s private bin if it exists\nif [ -d "\$HOME/bin" ] ; then\n    PATH="$HOME/bin:$PATH"\nfi\n' >> ~/.bashrc`


## AI Jam

- `sudo apt install python python-pip virtualenv`
- `sudo mkdir /opt/ai-jam`
- `sudo chmod ag+w /opt/ai-jam`
- `git clone https://github.com/IMAGINARY/ai-jam.git /opt/ai-jam`
- Follow the installation instructions in the ai-jam README file
- Edit `public/cfg/config.yml` and set `skipStartScreen` to `true`.
- Raise the volume to 200% or as appropriate for the exhibit.
