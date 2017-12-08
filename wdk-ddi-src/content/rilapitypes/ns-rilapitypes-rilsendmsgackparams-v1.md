---
UID: NS.rilapitypes.RILSENDMSGACKPARAMS_V1
title: RILSENDMSGACKPARAMS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgackparams_v1_2.htm
old-project: netvista
ms.assetid: 6e1f0283-76de-4c21-8205-cab83250dfae
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILSENDMSGACKPARAMS_V1, RILSENDMSGACKPARAMS_V1
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
req.alt-api: RILSENDMSGACKPARAMS_V1
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

# RILSENDMSGACKPARAMS_V1 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILSENDMSGACKPARAMS_V1 {
  DWORD            cbSize;
  DWORD            dwExecutor;
  HUICCAPP         hUiccApp;
  DWORD            dwAckID;
  RILMSGACKSTATUS  dwMsgStatus;
} RILSENDMSGACKPARAMS_V1, RILSENDMSGACKPARAMS_V1;
````


## -struct-fields
<dl>

### -field cbSize

<dd></dd>

### -field dwExecutor

<dd></dd>

### -field hUiccApp

<dd></dd>

### -field dwAckID

<dd></dd>

### -field dwMsgStatus

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