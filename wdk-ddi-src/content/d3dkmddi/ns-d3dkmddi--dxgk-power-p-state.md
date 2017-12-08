---
UID: NS.d3dkmddi._DXGK_POWER_P_STATE
title: DXGK_POWER_P_STATE
author: windows-driver-content
description: Reserved for system use. Do not use it in your driver.
old-location: display\dxgk_power_p_state.htm
old-project: display
ms.assetid: F4612284-36C8-49C4-914D-43C32489EABD
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_POWER_P_STATE, DXGK_POWER_P_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_POWER_P_STATE
req.alt-loc: D3dkmddi.h
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
---

# DXGK_POWER_P_STATE structure



## -description
<p>Reserved for system use. Do not use it in your driver.</p>


## -syntax

````
typedef struct _DXGK_POWER_P_STATE {
  ULONG     NominalPower;
  ULONG     OperatingFrequency;
  ULONGLONG TransitionLatencies[DXGK_MAX_P_STATES];
  ULONGLONG ResidencyRequirement;
} DXGK_POWER_P_STATE, *PDXGK_POWER_P_STATE;
````


## -struct-fields
<dl>

### -field NominalPower

<dd></dd>

### -field OperatingFrequency

<dd></dd>

### -field TransitionLatencies

<dd></dd>

### -field ResidencyRequirement

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>