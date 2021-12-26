---
layout: post
title: Obtener información de tu computadora usando la consola (macOS)
date: 2021-12-26 14:43 -0300
categories: es
---

Cuando estás pensando en vender tu laptop, o comprás una nueva, alguien suele preguntar sobre los _specs_ de tu máquina; o quizás estás haciendo ssh a un servidor y no tenés idea qué equipo es.

Una solución es correr `system_profiler SPHardwareDataType` en tu terminal:

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

También podés correr `system_profiler SPSoftwareDataType` y te va a dar algo de información sobre tu sistema operativo:

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

Y eso no es todo, hay muchísimos más parámetros que podés probar:

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