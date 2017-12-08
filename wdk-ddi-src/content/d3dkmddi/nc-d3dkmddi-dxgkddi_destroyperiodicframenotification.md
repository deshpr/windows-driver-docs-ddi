---
UID: NC.d3dkmddi.DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION
title: DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION
author: windows-driver-content
description: Used to destroy a periodic frame notification.
old-location: display\dxgkddi_destroyperiodicframenotification.htm
old-project: display
ms.assetid: 4C6B6FB2-A699-40F5-ACA3-62E8620E99AB
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION
req.alt-loc: d3dkmddi.h
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

# DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION callback



## -description
Used to destroy a periodic frame notification.


## -prototype

````
NTSTATUS APIENTRY DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION(
  _In_ const PDXGKARG_DESTROYPERIODICFRAMENOTIFICATION pDestroyPeriodicFrameNotification
);
````


## -parameters

### -param pDestroyPeriodicFrameNotification [in]

A structure of type <i>PDXGKARG_DESTROYPERIODICFRAMENOTIFICATION</i> containing the arguments needed to destroy a periodic frame notification.

## -returns
DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>When a periodic frame notification has been successfully created.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Indicates that there was an invalid parameter passed to the call.

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>