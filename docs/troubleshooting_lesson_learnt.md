## Troubleshooting Log

Real problems hit during this project, and how they actually got solved.

# Wyse wouldn't boot from a USB installer at all

Symptom: "No bootable devices found" even when the USB installer already plugged in and confirm on another device.

Assumption: USB installer defect or the write process via Rufus failed.

--> Solution: via Dell's own device documentation that Wyse thin client's default setting is "USB boot support disabled" - a setting buried in the BIOS setting. After enabling, USB installer recognised right away.

# Jellyfin's iOS app couldn't but Safari could, on the identical address

Symptom: Typing the exact address on the safari browser works find but on the iOS app shows "connection to server not possible."

Root cause: iOS app requires apps to be granted a separate local network permission. Can be toggled in the iOS app setting.


