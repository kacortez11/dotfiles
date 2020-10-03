# dotfiles
Collection of dotfiles for linux customization

## Notes on current Pop! OS customization
### Fresh install to-dos:
1.  Nautilus (Files) will not have 'New Document' option on right-click: 
/home_dir/Templates: add a file such as 'New Document.txt' so that the option will appear on right click.
2. If dual-booting, install rEFInd. https://rodsbooks.com/refind/installing.html#linux 
    2.1. During restart to test Windows and Linux systems are both working properly, remove the extra prints by:
        * Choose the icon to be removed / Del / Yes 
    2.2. refind-minimal is a pretty decent and minimal setup
      Download refind-minimal theme. Copy to /boot/efi/EFI/refind/themes. Update config to add directory of theme
3. Monday week start on calendar: set locale for date and time to en_GB (in .pam_environment file, i guess)
4. CLI `full-update` alias to .bashrc: 
```bash
alias full-update='sudo apt update && sudo apt list --upgradable && sudo apt full-upgrade && sudo apt autoremove && flatpak update'
```
5. Good to have Gnome Extensions:
* Bluetooth quick connect -- quick ON https://extensions.gnome.org/extension/1401/bluetooth-quick-connect/
* Hide Activities button
* Resource Monitor (Oryon) -- PopOS has System Load Indicator preinstalled (visual)
* Cpu Power Manager https://extensions.gnome.org/extension/945/cpu-power-manager/
* User themes
* Bring Out Submenu of Power Logout Button https://extensions.gnome.org/extension/2917/bring-out-submenu-of-power-offlogout-button/
* GSConnect - https://github.com/andyholmes/gnome-shell-extension-gsconnect/wiki
* Scrovol -- scroll volume https://extensions.gnome.org/extension/1519/scrovol/
* Toggle Mute on Middle Click https://extensions.gnome.org/extension/1473/toggle-mute-on-middle-click/
* For Lenovo, Conservation mode toggle in gnome: https://extensions.gnome.org/extension/2992/ideapad/

Command to update dconf values: 
```bash
dconf write /org/gnome/shell/extensions/pop-shell/toggle-stacking-global "['<Super><Shift>s']"
```
### Not installation but good to know: 
* To flush dconf values. `dconf dump /org/gnome/shell/extensions/pop-shell/global/`
* *dconf* - Desktop configuration 
* *gconf* - Gnome configuration


### 09/28 Bugs/Wishlist Features/To find extensions: 
* After gnome-shell restart via Alt-F2+r, the top bar disappears and I need to click Super 2x 
* Find a way to remove border highlight when there is only 1 active window. 
* Change accent color of active window selected when Super is pressed once. 
* System Load Indicator (indicator-multiload) has a misunderstood feature: text appears beside the graph, should you choose to use SLI, add a blank indicator item (just play with it) to remove the text.

Wifi Settings > IPv4 > Set DNS to manual: 8.8.8.8, 8.8.4.4

### TeX related fixes applied: In .profilerc, .bashrc, set PATH so it includes texlive if it exists
```bash
PATH="/home/kacortez/texlive/2020/bin/x86_64-linux:$PATH"
```
