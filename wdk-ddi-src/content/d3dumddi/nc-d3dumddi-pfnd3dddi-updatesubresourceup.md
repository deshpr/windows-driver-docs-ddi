---
UID: NC.d3dumddi.PFND3DDDI_UPDATESUBRESOURCEUP
title: PFND3DDDI_UPDATESUBRESOURCEUP
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to update a destination subresource region from a source system-memory region. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfnupdatesubresourceup.htm
old-project: display
ms.assetid: 5AF55FED-6FD6-41BE-A743-1E9D0EA51C9C
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnUpdateSubresourceUP
req.alt-loc: D3dumddi.h
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

# PFND3DDDI_UPDATESUBRESOURCEUP callback



## -description
<p>Called by the Microsoft Direct3D runtime to update a destination subresource region from a source system-memory region. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.</p>


## -prototype

````
PFND3DDDI_UPDATESUBRESOURCEUP pfnUpdateSubresourceUP;

_Check_return_ HRESULT APIENTRY* pfnUpdateSubresourceUP(
  _In_       HANDLE                        hDevice,
  _In_ const D3DDDIARG_UPDATESUBRESOURCEUP *pCounterInfo
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p>A handle to the display device (graphics context).

</p>
</dd>

### -param pCounterInfo [in]

<dd>
<p>A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddiarg-updatesubresourceup.md">D3DDDIARG_UPDATESUBRESOURCEUP</a> structure that describes how to update a destination subresource region from a source system-memory region.</p>
</dd>
</dl>

## -returns
<p>If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg-updatesubresourceup.md">D3DDDIARG_UPDATESUBRESOURCEUP</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UPDATESUBRESOURCEUP callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>