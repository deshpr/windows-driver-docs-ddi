---
UID: NS.rilapitypes.RILUICCLOCK~r1
title: RILUICCLOCK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclock_2.htm
old-project: netvista
ms.assetid: 01a39c94-987c-498c-8890-423b762f09fd
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILUICCLOCK,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCLOCK
req.alt-loc: rilapitypes.h
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

# RILUICCLOCK structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILUICCLOCK {
  HUICCAPP  hUiccApp;
  DWORD     dwKeyRef;
} RILUICCLOCK, RILUICCLOCK;
````


## -struct-fields
<dl>

### -field hUiccApp

<dd></dd>

### -field dwKeyRef

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>