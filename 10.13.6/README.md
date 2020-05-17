# Hackintosh Installation Guide

## Specs

| Type        | Item                       |
| ----------- | -------------------------- |
| CPU         | Intel SkyLake i7-6700      |
| Motherboard | MSI Z170 Krait Gaming      |
| Memory      | Kingston DDR4 2400 16G x 2 |
| VideoCard   | MSI Nvidia GTX 550 Ti      |
| Storage     | NVMe M.2 Intel 600p 256G   |


## Step 1 : Download macOS High Sierra
1. You need a working macOS, either an Apple product or VMware
2. Download macOS High Sierra from App Store

## Step 2 : Create a Bootable USB with UniBeast
1. Open `/Applications/Utilities/` `Disk Utility`
2. Choose your USB drive (better have more then 16GB, and USB3.0 is recommended)
3. Click Erase
  - Name : USB
  - Format : OS X Extended (Journaled)
  - Scheme : GUID Partition Map

4. run UniBeast
  - Continue → Continue → Continue → Agree
  - Choose USB → Continue
  - Choose UEFI Boot Mode
  - Select "Inject Nvidia" (for GTX550Ti or older card, newer VGA card may need web driver)
  - Continue to Copying Files...

5. After done making the bootable USB drive,
    now edit config.plist to make you be able to install macOS on a NVMe drive.

    edit `/EFI/CLOVER/config.plist`, add the following line to KextsToPatch
    between `<array>  </array>`
    ```plist
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily IONameMatch</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>InfoPlistPatch</key>
        <true/>
        <key>Find</key>
        <data>PHN0cmluZz5wY2kxNDRkLGE4MDQ8L3N0cmluZz4=</data>
        <key>Replace</key>
        <data>PHN0cmluZz5wY2kxNDRkLGE4MDI8L3N0cmluZz4=</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#1</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>ibPoAgAAweAMBQAQAACJgw==</data>
        <key>Replace</key>
        <data>ibPoAgAAweAJBQAQAACJgw==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#2</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>D7aMiIIAAACD+QwPhTIBAA==</data>
        <key>Replace</key>
        <data>D7aMiIIAAACD+QkPhTIBAA==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#3</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>AMeDpAAAAAAQAABIi0gISA==</data>
        <key>Replace</key>
        <data>AMeDpAAAAAACAABIi0gISA==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#4</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>SYnGTYX2dGFBwecMSWP/vg==</data>
        <key>Replace</key>
        <data>SYnGTYX2dGFBwecJSWP/vg==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#5</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>hv8PAABIwegMD7cPgeH/Dw==</data>
        <key>Replace</key>
        <data>hv8PAABIwegJD7cPgeH/Dw==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#6_7</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>icGB4f8PAABIAdFIgfn/DwAAdzs=</data>
        <key>Replace</key>
        <data>icGB4f8BAABIAdFIgfn/AQAAdzs=</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#8</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>SYHF/w8AAEnB7QxJiwQkSA==</data>
        <key>Replace</key>
        <data>SYHF/w8AAEnB7QlJiwQkSA==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#9_10</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>BgIAAEyNuAAQAABMiflIgeEA8P//SYmGGgEAAEmJjiIBAABBvAAQAABJKfQ=</data>
        <key>Replace</key>
        <data>BgIAAEyNuAACAABMiflIgeEA8P//SYmGGgEAAEmJjiIBAABBvAACAABJKfQ=</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#11</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>AABJiY4iAQAAugAQAABIKQ==</data>
        <key>Replace</key>
        <data>AABJiY4iAQAAugACAABIKQ==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#12</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>yAAAAEkp17gAEAAATYskJA==</data>
        <key>Replace</key>
        <data>yAAAAEkp17gAAgAATYskJA==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#13</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>4b+AQBUGTYnWugAQAABFMQ==</data>
        <key>Replace</key>
        <data>4b+AQBUGTYnWugACAABFMQ==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#14</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>iWTY+EmBxAAQAABJgccA8A==</data>
        <key>Replace</key>
        <data>iWTY+EmBxAACAABJgccA8A==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#15</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>Bf8PAABIwegMZvfB/w8PlQ==</data>
        <key>Replace</key>
        <data>Bf8PAABIwegJZvfB/w8PlQ==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#16</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>weIIQQ+2wcHgDEQJ0EQJwA==</data>
        <key>Replace</key>
        <data>weIIQQ+2wcHgCUQJ0EQJwA==</data>
    </dict>
    <dict>
        <key>Comment</key>
        <string>IONVMeFamily Pike R. Alpha Patch#17</string>
        <key>Disabled</key>
        <false/>
        <key>Name</key>
        <string>IONVMeFamily</string>
        <key>Find</key>
        <data>RYTJD5XAD7bAweAMRAnYRA==</data>
        <key>Replace</key>
        <data>RYTJD5XAD7bAweAJRAnYRA==</data>
    </dict>
    ```

6. Download OsxAptioFix2Drv-free2000.efi, put it to `EFI/CLOVER/drivers64UEFI/`
> This file is so damn fucking important, without it I randomly got stuck boot with the error:
> `Error allocating 0x#### pages at 0x#### alloc type 2`
> It annoyed me for few days, until I found the solution provided by @nickwoodhams
> Here is the article.
7. Open Clover Configurator, click left bottom icon to load system `EFI/CLOVER/``config.plist`
  Devices → USB → Inject
  Devices → USB → FixOwnership

8. We also need all of the following things, and put them to the USB drive.
  - Clover Bootloader
  - Clover Configurator
  - SSDT for i7-6700 - Get it from ammulder's Guide and rename it SSDT.aml
  - Audio SSDT - SSDT-HDEF-HDAS-1.aml
  - Audio Driver - audio_cloverALC-120 (audio_cloverALC-120_v1.0f3.command)
  - RehabMan-CodecCommander-2017-0501.zip
  - KextBeast


## Step 3 : BIOS Setting

Setting/Advanced/Windows OS Configuration/ALL Disabled
Setting/Advanced/Integrated Peripherals/LAN Option ROM: Disabled
Setting/Advanced/Integrated Peripherals/Network Stack: Disabled
Setting/Advanced/USB Configuration/XHCI Hand-off: Enabled
Setting/Boot/Boot mode select: UEFI
Overclocking/CPU features/Intel VT-D Tech: Disabled


## Step 4 : Install macOS Sierra
1. Reboot, and Press F11 to enter Boot Device selection menu, then choose your usb drive
2. At Clover boot screen, choose Boot Mac OS X from USB
3. When you arrive at the Installer, choose language.
  > sometimes i encountered a STOP SIGN on boot, just reboot and try again.
  > for more debug info, you can add -v on boot args
![add -v to see logs](https://d2mxuefqeaa7sj.cloudfront.net/s_CEBBB72558A7BDA9E8EABA268DFB31C6C66AED54BA43D1A203D1D2892190DF64_1495856005741_Screen+Shot+2017-05-27+at+11.33.03+AM.png)

![choose language to begin installation](https://d2mxuefqeaa7sj.cloudfront.net/s_CEBBB72558A7BDA9E8EABA268DFB31C6C66AED54BA43D1A203D1D2892190DF64_1495855459444_113565-6a640e96fccd82a54255429e396b3c94.png)

4. In the top menu bar choose Utilities, and open Disk Utility
5. Select Intel SSDPEKKW256G7 Media (Intel 600p), and Erase
  - Name : macOS
  - Format : OS X Extended (Journaled)
  - Scheme : GUID Partition Map
6. When the installer asks you where to install, choose macOS
7. Installation takes about 12 minutes, then system will reboot.
8. After done installation, we don’t have a boot-loader installed yet. So we boot using USB drive, and go to Options, delete nv_disable=1, ESC and select Boot Mac OS X from macOS
![](https://d2mxuefqeaa7sj.cloudfront.net/s_CEBBB72558A7BDA9E8EABA268DFB31C6C66AED54BA43D1A203D1D2892190DF64_1495855393976_Screen+Shot+2017-05-27+at+11.23.03+AM.png)



## Step 5 : Post Installation
1. Allow apps downloaded from anywhere
    sudo spctl --master-disable
2. Run Clover Configurator or EFI Mounter, mount system EFI and USB EFI.
3. Run Clover Bootloader (Clover_v2.4k_r4077.pkg), Continue, Continue, Customize, and check `Install for UEFI booting only`, then click Install.
![](https://d2mxuefqeaa7sj.cloudfront.net/s_CEBBB72558A7BDA9E8EABA268DFB31C6C66AED54BA43D1A203D1D2892190DF64_1495962806419_Screen+Shot+2017-05-28+at+5.13.14+PM.png)

4. Copy the following file from USB EFI to the same place on system EFI
  - EFI/CLOVER/config.plist
  - EFI/CLOVER/drivers64UEFI/OsxAptioFix2Drv-free2000.efi
5. Put SSDT.aml and SSDT-HDEF-HDAS-1.aml to system `EFI/CLOVER/ACPI/patched/`
6. Run Clover Configurator, click left bottom icon to load system `EFI/CLOVER/``config.plist`, Boot → Arguments → darkwake
  Boot → Arguments → dart=0
  Boot → Default Boot Volume → Sierra
  Devices → USB → Inject
  Devices → USB → FixOwnership
  Graphics → Inject NVidia
![](https://d2mxuefqeaa7sj.cloudfront.net/s_CEBBB72558A7BDA9E8EABA268DFB31C6C66AED54BA43D1A203D1D2892190DF64_1495963509325_Screen+Shot+2017-05-28+at+5.24.51+PM.png)

7. Save (beside the load icon), and reboot the system.
8. Double click audio_cloverALC-120_v1.0f3.command → y → y → y → reboot again
9. install RehabMan-CodecCommander-2017-0501.zip
10. System → Preferences → Sound → Output → choose Internal Speakers
![](https://d2mxuefqeaa7sj.cloudfront.net/s_CEBBB72558A7BDA9E8EABA268DFB31C6C66AED54BA43D1A203D1D2892190DF64_1495963933529_Screen+Shot+2017-05-28+at+5.32.07+PM.png)

Known Issues
- No sound (or very low) after waking up from sleep



References
----------
- Stork's Gene Build > ASUS MAXIMUS VIII GENE - i5-6600K - Gigabyte GTX 950

https://www.tonymacx86.com/threads/storks-gene-build-asus-maximus-viii-gene-i5-6600k-gigabyte-gtx-950.181272/#Installation


- UniBeast: Install macOS Sierra on Any Supported Intel-based PC

https://www.tonymacx86.com/threads/unibeast-install-macos-sierra-on-any-supported-intel-based-pc.200564/


- Wuyuan's Blog - z170+skylake

https://wuyuans.com/2015/12/z170-skylake-hackintosh


- Pike's Universum - IONVMeFamily.kext bin patch data

https://pikeralpha.wordpress.com/2016/06/27/nvmefamily-kext-bin-patch-data/


- toleda’s Sierra audio patcher

https://www.tonymacx86.com/threads/sierra-desktop-realtek-applehda-audio.197923/
