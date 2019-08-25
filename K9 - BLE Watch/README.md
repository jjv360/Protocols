# K9 - Bluetooth LE watch

This contains all the research I have found about the K9 smartwatch.

## About device

This is a cheap-ish smart watch with a long advertised battery life.

- **Store link:** [Takealot](https://www.takealot.com/bitbyte-smart-sport-watch-k9/PLID54951882)
- **Screen:** Advertised as a 1.3" IPS _round_ touchscreen, 240 x 240 pixels. It is not round, but rather a small square screen inside a round cover. No parts of the screen are covered.
- **Element resistance:** Advertised as IP68
- **Operating system:** A custom firmware.
- **CPU:** Unknown, looks to be a microcontroller.
- **Apps:** [Android](https://play.google.com/store/apps/details?id=com.crrepa.band.dafit&hl=en_ZA), [iOS](https://apps.apple.com/us/app/da-fit/id1316004998)

## Debug menu

Hold down on the clock screen for 3 seconds. You will get a screen with:

- OS version: `VERSION MOY-TS3-1.7.7`
- Bluetooth address: `EC:6E:28:04:F3:F8`
- Serial number: `A62DB89F`
- Unknown code: `030D0006-04862601`
- Hardware revision: `A130FL1.5`
- Bottom left: Battery icon with remaining charge
- Bottom right: Bluetooth icon, only visible while connected

## Device Information

This data was gathered by reading the Device Information BLE GATT service.

- Manufacturer: `MOYOUNG` - Mo Young seems to make other fitness trackers and smart watches.
- Model: `DFU=0`
- Serial: `A62DB89F`
- Hardware revision: `A130FL1.5`
- Software revision: `MOY-TS3-1.7.7`

## Bluetooth LE services

- GAP
- GATT
- Human Interface Device `0x1812`
  - [Spec](https://www.bluetooth.com/wp-content/uploads/Sitecore-Media-Library/Gatt/Xml/Services/org.bluetooth.service.human_interface_device.xml)
- Device Information
- Battery service
- Unknown `0xFEEA`
- Heart rate
- Unknown `0xFEE7`
  - Maybe related to Mi Band? [Link](https://github.com/dkhmelenko/miband-android/blob/7dbb15e7186989136bee170d69bb34420db114fc/miband-sdk/src/main/java/com/khmelenko/lab/miband/model/Profile.java#L35)

## Sending notifications

Since this device works on iOS, we can surely simulate the iOS Notification Center Service on Android and send notifications that way. But is that the only way?

## References

- [Apple's Notification Center Service](https://developer.apple.com/library/archive/documentation/CoreBluetooth/Reference/AppleNotificationCenterServiceSpecification/Specification/Specification.html#//apple_ref/doc/uid/TP40013460-CH1-SW7)