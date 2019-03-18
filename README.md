# CZ Programmer Keyboard
Speciální znaky a čísla jsou stejné jako na anglické klávesnici.

- Čárka nad písmeny je dostupná přes AltGr na klávese s mínusem (pomlčkou) (vpravo od klávesy 0)
- Háček je dostupný přes AltGr na kláavese s rovnítkem (tedy stejně jako na české klávesnici)
- ěščřžýáíé jsou dostupné přes AltGr na číslech
- ĚŠČŘŽÝÁÍÉ josu dostupné přes AltGr + Shift
- Klávesy ů/ú jsou dostupné na stejné klávese jako na české akorát přes AltGr


## Instalace

- Stažení souboru do /tmp.
- Zkopírování souboru do adresare s layouty.
- Nastavení vlastníka souboru, aby nebyl později **přepsán/smazán při upgradu/updatu systému**.
- A nastavení práv.

```bash
curl https://raw.githubusercontent.com/dburton90/cz-programmer-keyboard/master/uscz > /tmp/uscz
sudo cp /tmp/uscz /usr/share/X11/xkb/symbols/
sudo chown $SUDO_USER:$SUDO_USER /usr/share/X11/xkb/symbols/uscz
sudo chmod 644 /usr/share/X11/xkb/symbols/uscz
```

## Nastavení
(Možná bude nutné restartovat)

- **setxkbmap** (nutno dát do nějakého init scriptu, který je volán po kazdem startu)

```bash
setxkbmap -layout uscz -variant basic
```
- nebo **localectl** (localectl je komunikuje se systemd-localed a ulozi nastaveni klavesnice do /etc/..., takze neni potreba to volat po kazdem startu)

```bash
localectl set-x11-keymap uscz
```

Další info
https://wiki.archlinux.org/index.php/Xorg/Keyboard_configuration
