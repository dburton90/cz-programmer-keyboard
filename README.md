# CZ Programmer Keyboard
Speciální znaky a čísla jsou stejné jako na anglické klávesnici.

- Čárka nad písmeny je dostupná přes AltGr na klávese s - (vpravo od 0)
- Háček je dostupný přes AltGr na kláavese s =
- ěščřžýáíé jsou dostupné přes AltGr na číslech
- ĚŠČŘŽÝÁÍÉ josu dostupné přes AltGr + Shift
- Klávesy ů/ú jsou dostupné na stejné klávese jako na české akorát přes AltGr


## Instalace

Stažení souboru do /tmp.

```bash
curl https://raw.githubusercontent.com/dburton90/cz-programmer-keyboard/master/uscz > /tmp/uscz
```

Zkopírování souboru do adresare s layouty.

```bash
sudo cp /tmp/uscz /usr/share/X11/xkb/symbols/
```

Nastavení vlastníka souboru, aby nebyl později přepsán/smazán při upgradu/updatu systému.

```bash
sudo chown $SUDO_USER:$SUDO_USER /usr/share/X11/xkb/symbols/uscz
```
(Možná bude nutné restartovat)

Nastavení layoutu pomocí *setxkbmap* (nutno dát do nějakého init scriptu, který je volán během startu systému)

```bash
setxkbmap -layout uscz -variant basic
```
nebo pomocí *localectl* (localectl je komunikuje se systemd-localed a ulozi nastaveni klavesnice do /etc/...)

```bash
localectl set-x11-keymap uscz
```

Další info
https://wiki.archlinux.org/index.php/Xorg/Keyboard_configuration
