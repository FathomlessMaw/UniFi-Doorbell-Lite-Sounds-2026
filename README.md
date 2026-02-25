# UniFi Doorbell Lite Sound Files

Default sound files extracted from the UniFi Doorbell Lite (firmware 5.1.240).

Inspired by [johnzanussi/unifi-g4-doorbell-sounds](https://github.com/johnzanussi/unifi-g4-doorbell-sounds) for the G4 Doorbell.

## File Locations on Device

| Path | Description |
|------|-------------|
| `/var/etc/persistent/sounds/` | Active configured chime — the "Default" tone selected in Protect |
| `/etc/sounds/` | Runtime sound set |
| `/usr/etc/sounds/` | Firmware sound set including unique inactive doorbell messages |
| `/usr/etc/sounds/0xa061/` | Hardware variant sound set |
| `/usr/etc/sounds/0xa592/` | Hardware variant sound set |

## Extraction Method

1. Enable SSH on the Doorbell Lite via Home Assistant UniFi Protect integration (`switch.<doorbell>_ssh` entity — disabled by default, enable then toggle on)
2. SSH in: `ssh ubnt@<doorbell_ip>` using the Recovery Code from Protect (Settings → System → Other Configurations → Recovery Code)
3. Copy files: `scp -O ubnt@<doorbell_ip>:/path/to/sounds/*.ogg .` (the `-O` flag is required — the Doorbell Lite lacks SFTP support)

## Usage with Home Assistant + Sonos

Place files in `/config/www/doorbell_chimes/` and reference them in automations as `/local/doorbell_chimes/filename.ogg`.

## License

These files are property of Ubiquiti Inc. This repository is provided for personal and educational use only.
