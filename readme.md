```
 _____          _                    __               _     _       _
|_   _|_      _(_) __ _ _ __ __ _   / _|_   _ _ __ __| |___(_) __ _| |_   _
  | | \ \ /\ / / |/ _` | '__/ _` | | |_| | | | '__/ _` |_  / |/ _` |// | | |
  | |  \ V  V /| | (_| | | | (_| | |  _| |_| | | | (_| |/ /| | (_| //| |_| |
  |_|   \_/\_/ |_|\__,_|_|  \__,_| |_|  \__,_|_|  \__,_/___|_|\__,_|_|\__,_|

```
Tiara ma w środku:
- Raspberry PI z Manjaro ARM na pokładzie
- Powerbank
- Głośnik w własnym akumulatorem
- Kabelki:
	- AUX
	- USB-A↔USB-C

W ramach czapki są stworzone:
- Strona internetowa do wgrywania plików dźwiękowych i tekstu
- Dæmon działający w tle do odtwarzania
- Konfiguracja całego systemu

# TODO
- Opisać konfigurację systemu

# Konfiguracja
Opis konfiguracji i plików w systemie.

## GPIO
Używamy pinu 21 jako wejścia.
Patrząc na RPI 4B portami USB i ethernetowym do dołu:
- PIN 21 jest ostatnim prawym pinem.
- Pin 3,3 V jest pierwszym lewym pinem.

Należy je razem połączyć poprzez jakiś fajny opornik i guziczek, aby wykrywał założenie czapki.
Potem stan GPIO można odczytać za pomocą plików w `/sys` w systemie.

## Dæmony
Włączyć następujące dæmony:
- `hostapd`
- `systemd-networkd`
- `dnsmasq`
- `iptables`
- `httpd`
