---
layout: post
title: Getting your computer specs with the console (macOS)
date: 2021-12-26 14:43 -0300
categories: en
image: https://nyc3.digitaloceanspaces.com/betzerra/blog/misc/betzerra_post_terminal.png
---

Either when you're looking to sell your old laptop or bought a new one, someone asks about the specs of your machine; or maybe you're ssh-ing a server and you have no clue what machine it is.

Well, you can run `system_profiler SPHardwareDataType` on your terminal and you'll get something like:

```
Hardware:

    Hardware Overview:

      Model Name: MacBook Pro
      Model Identifier: MacBookPro18,3
      Chip: Apple M1 Pro
      Total Number of Cores: 10 (8 performance and 2 efficiency)
      Memory: 32 GB
      System Firmware Version: [REDACTED]
      OS Loader Version: [REDACTED]
      Serial Number (system): [REDACTED]
      Hardware UUID: [REDACTED]
      Provisioning UDID: [REDACTED]
      Activation Lock Status: [REDACTED]
```

Also, `system_profiler SPSoftwareDataType` gives you some information about the OS you're running:

```
Software:

    System Software Overview:

      System Version: macOS 12.0.1 (21A559)
      Kernel Version: Darwin 21.1.0
      Boot Volume: Macintosh HD
      Boot Mode: Normal
      Computer Name: [REDACTED]
      User Name: [REDACTED]
      Secure Virtual Memory: Enabled
      System Integrity Protection: Enabled
      Time since boot: 20:37
```

And there's plenty more. You can try with the following parameters too:

```
SPAirPortDataType               SPFireWireDataType              SPPowerDataType
SPApplicationsDataType          SPFirewallDataType              SPPrefPaneDataType
SPAudioDataType                 SPFontsDataType                 SPPrintersDataType
SPBluetoothDataType             SPFrameworksDataType            SPPrintersSoftwareDataType
SPCameraDataType                SPHardwareDataType              SPSASDataType
SPCardReaderDataType            SPHardwareRAIDDataType          SPSPIDataType
SPComponentDataType             SPInstallHistoryDataType        SPSerialATADataType
SPConfigurationProfileDataType  SPLogsDataType                  SPSoftwareDataType
SPDeveloperToolsDataType        SPManagedClientDataType         SPStartupItemDataType
SPDiagnosticsDataType           SPMemoryDataType                SPStorageDataType
SPDisabledSoftwareDataType      SPNetworkDataType               SPSyncServicesDataType
SPDiscBurningDataType           SPNetworkLocationDataType       SPThunderboltDataType
SPDisplaysDataType              SPNetworkVolumeDataType         SPUSBDataType
SPEthernetDataType              SPPCIDataType                   SPUniversalAccessDataType
SPExtensionsDataType            SPParallelATADataType           SPWWANDataType
SPFibreChannelDataType          SPParallelSCSIDataType
```