---
title: OID_GEN_CO_HARDWARE_STATUS
author: windows-driver-content
description: This topic describes the OID_GEN_CO_HARDWARE_STATUS object identifier (OID).
ms.assetid: b846622a-a082-41e8-b32b-74c111b31f69
keywords:
- OID_GEN_CO_HARDWARE_STATUS
ms.author: windowsdriverdev
ms.date: 11/02/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# OID_GEN_CO_HARDWARE_STATUS

The OID_GEN_CO_HARDWARE_STATUS OID specifies the current hardware status of the underlying NIC, as one of the following NDIS_HARDWARE_STATUS-type values:

**NdisHardwareStatusReady**  
Available and capable of sending and receiving data over the wire.

**NdisHardwareStatusInitializing**  
Initializing.

**NdisHardwareStatusReset**  
Resetting.

**NdisHardwareStatusClosing**  
Closing.

**NdisHardwareStatusNotReady**  
Not ready.

## Requirements

| | |
| --- | --- |
| Version | Windows Vista and later |
| Header | Ntddndis.h (include Ndis.h) |

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bnetvista\netvista%5D:%20OID_WWAN_DEVICE_CAPS_EX%20%20RELEASE:%20%288/8/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")