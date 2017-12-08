---
UID: NC.d3dumddi.PFND3DDDI_DESTROYEXTENSIONDEVICE
title: PFND3DDDI_DESTROYEXTENSIONDEVICE
author: windows-driver-content
description: The DestroyExtensionDevice function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.
old-location: display\destroyextensiondevice.htm
old-project: display
ms.assetid: 8c4bcab3-b903-4f39-aab0-7efb3b18d068
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DestroyExtensionDevice
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

# PFND3DDDI_DESTROYEXTENSIONDEVICE callback



## -description
<p>The <b>DestroyExtensionDevice</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.</p>


## -prototype

````
PFND3DDDI_DESTROYEXTENSIONDEVICE DestroyExtensionDevice;

__checkReturn HRESULT APIENTRY DestroyExtensionDevice(
  _In_ HANDLE hDevice,
  _In_ HANDLE hExtension
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param hExtension [in]

<dd>
<p> A handle to the DirectX VA extension device that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createextensiondevice.md">CreateExtensionDevice</a> function created.</p>
</dd>
</dl>

## -returns
<p><b>DestroyExtensionDevice</b> should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA extension device.</p>

## -remarks
<p>The <b>DestroyExtensionDevice</b> function notifies the driver to destroy the handle to the DirectX VA extension device that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createextensiondevice.md">CreateExtensionDevice</a> function previously created. The driver can then release resources that are associated with the DirectX VA extension device handle.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createextensiondevice.md">CreateExtensionDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddi-devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYEXTENSIONDEVICE callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>