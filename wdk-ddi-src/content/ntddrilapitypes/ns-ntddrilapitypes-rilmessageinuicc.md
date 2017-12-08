---
UID: NS.NTDDRILAPITYPES.RILMESSAGEINUICC
title: RILMESSAGEINUICC
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinuicc.htm
old-project: netvista
ms.assetid: 71f48863-06dd-4ea1-a8b7-fdf673090fe0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILMESSAGEINUICC, *LPRILMESSAGEINUICC, RILMESSAGEINUICC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMESSAGEINUICC
req.alt-loc: ntddrilapitypes.h
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
---

# RILMESSAGEINUICC structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILMESSAGEINUICC {
  DWORD     cbSize;
  DWORD     dwExecutor;
  HUICCAPP  hUiccApp;
  DWORD     dwIndex;
} RILMESSAGEINUICC, RILMESSAGEINUICC;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field hUiccApp


### -field dwIndex


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>