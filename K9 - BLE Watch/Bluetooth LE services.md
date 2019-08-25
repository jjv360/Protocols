# Bluetooth LE data

```
Advertise records:

0x01 Flags
    06

0x03 16-bit UUIDs available
    ...

0x09 Name
    "K9"

0x15 128-bit UUIDs
    ...

0x16 Service Data
    0F 18 26

0x19 Unknown record
    C1 00

0xFF Manufacturer specific data
    EF F0 EC 6E 28 04 F3 F8
```

```
Device Name: K9
Device Address: EC:6E:28:04:F3:F8

Services:--------------------------
GAP (00001800-0000-1000-8000-00805f9b34fb)
	Device Name (00002a00-0000-1000-8000-00805f9b34fb)
        "K9"
	Appearance (00002a01-0000-1000-8000-00805f9b34fb)
        C1 00
        (16bit) = Category
            (10bit) = General category -> 192 = Generic Watch
            (6bit) = Sub category -> 193 = Sports Watch
	Peripheral Preferred Connection Parameters (00002a04-0000-1000-8000-00805f9b34fb)
        10 00 20 00 04 00 58 02
        (uint16) = Min connection interval from 6 to 3200, multiplied by 1.25ms
        (uint16) = Max connection interval from field above to 3200, multiplied by 1.25ms
        (uint16) = Slave latency from 0 to 1000
        (uint16) = Connection supervised timeout multiplier from 10 to 3200 (65535 = no specific value)
	Central Address Resolution (00002aa6-0000-1000-8000-00805f9b34fb)
        01
        00 = Address resolution not supported
        01 = Address resolution is supported
        The Peripheral checks if the peer device supports address resolution by reading 
        the Central Address Resolution characteristic before using directed advertisement 
        where the initiator address is set to a Resolvable Private Address (RPA).


GATT (00001801-0000-1000-8000-00805f9b34fb)
	Service Changed (00002a05-0000-1000-8000-00805f9b34fb)


Human Interface Device (00001812-0000-1000-8000-00805f9b34fb)
	Protocol Mode (00002a4e-0000-1000-8000-00805f9b34fb)
        01
        00 = Boot Protocol Mode
        01 = Report Protocol Mode
	Report (00002a4d-0000-1000-8000-00805f9b34fb)
        -
        (uint8 repeated)
        The Report characteristic value contains Input Report, Output Report or
        Feature Report data to be transferred between the HID Device and HID Host.
	Report (00002a4d-0000-1000-8000-00805f9b34fb)
	Report map (00002a4b-0000-1000-8000-00805f9b34fb)
        -
        (uint8 repeated)
        The Report Map characteristic is used to define formatting information for 
        Input Report, Output Report, and Feature Report data transferred between a 
        HID Device and HID Host, information on how this data can be used, and other 
        information regarding physical aspects of the device (i.e. that the device 
        functions as a keyboard, for example, or has multiple functions such as a 
        keyboard and volume controls).
	Boot Keyboard Input Report (00002a22-0000-1000-8000-00805f9b34fb)
        3F 8C BF 04 03 A8 E7 6A
        (uint8 repeated)
        The Boot Keyboard Input Report characteristic is used to transfer fixed 
        format and length Input Report data between a HID Host operating in Boot 
        Protocol Mode and a HID Service corresponding to a boot keyboard.
	Boot Keyboard Output Report (00002a32-0000-1000-8000-00805f9b34fb)
        DF
        (uint8 repeated)
        The Boot Keyboard Output Report characteristic is used to transfer fixed 
        format and length Output Report data between a HID Host operating in Boot 
        Protocol Mode and a HID Service corresponding to a boot keyboard.
	HID Information (00002a4a-0000-1000-8000-00805f9b34fb)
        -
        (uint16) = Version of base USB HID Specification
        (uint8) = Country code, usually 0
        (uint8) = Flags
            (bit 0) = Remote wake support
            (bit 1) = Normally connectable
        The HID Information Characteristic contains the HID attributes. The value 
        of this Characteristic is static and can be cached for the lifetime of the 
        bond between the HID device and the HID host.
        NOTE: Not readable for some reason, I guess it's unnecessary if both sides
        already know the value. I don't though!
	HID Control Point (00002a4c-0000-1000-8000-00805f9b34fb)
        <write only>
        The HID Control Point characteristic is a control-point attribute that defines the following HID Commands when written:
        - Suspend (Refer to Section 7.4.2, Bluetooth HID Profile Specification 1.0)
        - Exit Suspend (Refer to Section 7.4.2, Bluetooth HID Profile Specification 1.0)


Device Information (0000180a-0000-1000-8000-00805f9b34fb)
	Manufacturer Name String (00002a29-0000-1000-8000-00805f9b34fb)
        "MOYOUNG"
	Model Number String (00002a24-0000-1000-8000-00805f9b34fb)
        "DFU=0"
	Serial Number String (00002a25-0000-1000-8000-00805f9b34fb)
        "a62db89f"
	Hardware Revision String (00002a27-0000-1000-8000-00805f9b34fb)
        "A130FL1.5"
	Software Revision String (00002a28-0000-1000-8000-00805f9b34fb)
        "MOY-TS3-1.7.7"


Battery service (0000180f-0000-1000-8000-00805f9b34fb)
	Unknown characteristic (00002a19-0000-1000-8000-00805f9b34fb)
        29

This service below I got this info by looking at the Da Fit APK, so I don't know if it's correct.
Unknown service (0000feea-0000-1000-8000-00805f9b34fb)
	Step change listener (0000fee1-0000-1000-8000-00805f9b34fb)
        D2 02 00 3A 02 00 27 00 00
	Unknown characteristic (0000fee2-0000-1000-8000-00805f9b34fb)
        <write no response>
        Has something to do with writing commands to the watch...
	Unknown characteristic (0000fee3-0000-1000-8000-00805f9b34fb)
	Unknown characteristic (0000fee5-0000-1000-8000-00805f9b34fb)
	Unknown characteristic (0000fee6-0000-1000-8000-00805f9b34fb)


HEART_RATE (0000180d-0000-1000-8000-00805f9b34fb)
	Heart Rate Measurement (00002a37-0000-1000-8000-00805f9b34fb)
	Body Sensor Location (00002a38-0000-1000-8000-00805f9b34fb)
        02


Unknown service (0000fee7-0000-1000-8000-00805f9b34fb)
	Unknown characteristic (0000fea1-0000-1000-8000-00805f9b34fb)
        07 D2 02 00 3A 02 00 27 00 00
	Unknown characteristic (0000fec9-0000-1000-8000-00805f9b34fb)
        EC 6E 28 04 F3 F8


Unknown service (0000fcba-0000-1000-8000-00805f9b34fb)
	Unknown characteristic (0000fcc1-0000-1000-8000-00805f9b34fb)


--------------------------
```