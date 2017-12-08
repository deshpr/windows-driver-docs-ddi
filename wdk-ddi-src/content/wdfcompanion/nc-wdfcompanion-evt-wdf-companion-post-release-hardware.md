---
UID: NC.wdfcompanion.EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
title: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_companion_post_release_hardware.htm
old-project: wdf
ms.assetid: ebba5344-dc3a-443f-a080-991dd784eb54
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_COMMON_BUFFER_CONFIG, WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.alt-api: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
req.alt-loc: wdfcompanion.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_COMPANION_POST_RELEASE_HARDWARE callback



## -description
<p>
			For internal use only.</p>


## -prototype

````
EVT_WDF_COMPANION_POST_RELEASE_HARDWARE EVT_WDF_COMPANION_POST_RELEASE_HARDWARE;

NTSTATUS EVT_WDF_COMPANION_POST_RELEASE_HARDWARE(
  _In_ WDFCOMPANION Companion,
  _In_ WDFCMRESLIST ResourcesTranslated
)
{ ... }
````


## -parameters
<dl>

### -param Companion [in]

<dd></dd>

### -param ResourcesTranslated [in]

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.23</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfcompanion.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>