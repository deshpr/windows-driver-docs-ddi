---
UID: NC.d3dumddi.PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
title: PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
author: windows-driver-content
description: A callback to submit a signal command to the hardware queue.
old-location: display\pfnd3dddi_submitsignalsyncobjectstohwqueuecb.htm
old-project: display
ms.assetid: D952A432-7B2C-43AC-9BC4-4335D2F37301
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
req.alt-loc: d3dumddi.h
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
---

# PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB callback



## -description
<p>A callback to submit a signal command to the hardware queue.</p>


## -prototype

````
_Check_return_ HRESULT APIENTRY CALLBACK PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB(
  _In_ HANDLE                                           hDevice,
  _In_ D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE *const submitSignalSyncoObjectsToHwQueue
);
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p>A handle to the device.</p>
</dd>

### -param submitSignalSyncoObjectsToHwQueue [in]

<dd>
<p>A pointer to the structure holding information on submitting a signal command to the hardware queue.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The call was successfully completed.</p>

<p> </p>

<p>This function might also return other HRESULT values.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h</dt>
</dl>
</td>
</tr>
</table>