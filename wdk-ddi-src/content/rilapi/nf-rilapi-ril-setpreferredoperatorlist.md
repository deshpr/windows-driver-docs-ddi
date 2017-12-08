---
UID: NF.rilapi.RIL_SetPreferredOperatorList
title: RIL_SetPreferredOperatorList
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setpreferredoperatorlist.htm
old-project: netvista
ms.assetid: e61e9e3f-b70f-4b0a-8e64-4c7c4c086130
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RIL_SetPreferredOperatorList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RIL_SetPreferredOperatorList
req.alt-loc: rilapi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# RIL_SetPreferredOperatorList function



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            </p>


## -syntax

````
HRESULT  RIL_SetPreferredOperatorList(
   HRIL              hRil,
   LPVOID            lpContext,
   HUICCAPP          hUiccApp,
   DWORD             dwPreferredListSize,
   RILOPERATORNAMES  lpPreferredList
);
````


## -parameters
<dl>

### -param hRil 

<dd></dd>

### -param lpContext 

<dd></dd>

### -param hUiccApp 

<dd></dd>

### -param dwPreferredListSize 

<dd></dd>

### -param lpPreferredList 

<dd></dd>
</dl>

## -returns
<p>If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rilapi.h</dt>
</dl>
</td>
</tr>
</table>