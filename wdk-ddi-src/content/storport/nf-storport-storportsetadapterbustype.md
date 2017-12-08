---
UID: NF.storport.StorPortSetAdapterBusType
title: StorPortSetAdapterBusType function
author: windows-driver-content
description: Used to adjust the BusType of the adapter depending on its current configuration.
old-location: storage\storportsetadapterbustype.htm
old-project: storage
ms.assetid: 818A9F03-F56E-47D6-A9D1-DD0F63B05054
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortSetAdapterBusType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortSetAdapterBusType
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# StorPortSetAdapterBusType function



## -description
Used to adjust the BusType of the adapter depending on its current configuration. Setting the BusType with this routine will allow you to override the global property set in the miniport INF without having to re-install the driver. This is useful for scenarios such as RAID support or support for multiple adapters with a different bus type.


## -syntax

````
ULONG StorPortSetAdapterBusType(
  _In_ PVOID HwDeviceExtension,
  _In_ ULONG BusType
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="storage.storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param BusType [in]

Contains a value of type <a href="storage.storage_bus_type">STORAGE_BUS_TYPE</a> that specifies the type of bus-specific configuration data to be set.

## -returns
The <b>StorPortSetAdapterBusType</b> routine returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>This routine will return this value if it was called outside the <a href="storage.hwstorfindadapter">HwStorFindAdapter</a> function.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>This routine will return this value if it was successful.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>This routine fails with this return value if the BusType is an invalid value.

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
</table>