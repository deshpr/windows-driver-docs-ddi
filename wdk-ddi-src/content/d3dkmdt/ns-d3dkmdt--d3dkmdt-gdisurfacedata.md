---
UID: NS.d3dkmdt._D3DKMDT_GDISURFACEDATA
title: D3DKMDT_GDISURFACEDATA
author: windows-driver-content
description: The D3DKMDT_GDISURFACEDATA structure describes surfaces that are used by GDI hardware acceleration and the Desktop Window Manager (DWM).
old-location: display\d3dkmdt_gdisurfacedata.htm
old-project: display
ms.assetid: 7ae789dd-2454-4ed6-bd26-5ebfd9c33768
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMDT_GDISURFACEDATA, D3DKMDT_GDISURFACEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_GDISURFACEDATA
req.alt-loc: d3dkmdt.h
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

# D3DKMDT_GDISURFACEDATA structure



## -description
<p>The D3DKMDT_GDISURFACEDATA structure describes surfaces that are used by GDI hardware acceleration and the Desktop Window Manager (DWM).</p>


## -syntax

````
typedef struct _D3DKMDT_GDISURFACEDATA {
  UINT                    Width;
  UINT                    Height;
  D3DDDIFORMAT            Format;
  D3DKMDT_GDISURFACETYPE  Type;
  D3DKMDT_GDISURFACEFLAGS Flags;
  UINT                    Pitch;
} D3DKMDT_GDISURFACEDATA;
````


## -struct-fields
<dl>

### -field Width

<dd>
<p>[in] The width of the surface, in pixels.</p>
</dd>

### -field Height

<dd>
<p>[in] The height of the surface, in pixels.</p>
</dd>

### -field Format

<dd>
<p>[in] A <a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the surface. The following formats are supported:</p>
<dl>
<dd>
<p>D3DDDIFMT_A8B8G8R8</p>
</dd>
<dd>
<p>D3DDDIFMT_X8B8G8R8</p>
</dd>
<dd>
<p>D3DDDIFMT_A8R8G8B8</p>
</dd>
<dd>
<p>D3DDDIFMT_X8R8G8B8</p>
</dd>
<dd>
<p>D3DDDIFMT_A8</p>
</dd>
</dl>
<p>The D3DDDIFMT_A8 format is used only for D3DKMDT_GDISURFACE_STAGING and D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE staging surface types from the <a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a> enumeration.</p>
</dd>

### -field Type

<dd>
<p>[in] A <a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>-typed value that indicates the surface type.</p>
</dd>

### -field Flags

<dd>
<p>[in] Reserved for future use. Must be zero.</p>
</dd>

### -field Pitch

<dd>
<p>[out] The width of the surface, which includes padding, in bytes. The display miniport driver must return the pitch value for all allocations of <a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a> type D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE,  D3DKMDT_GDISURFACE_EXISTINGSYSMEM, and D3DKMDT_GDISURFACE_TEXTURE_CROSSADAPTER.</p>
</dd>
</dl>

## -remarks
<p>The D3DKMDT_GDISURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="display.dxgkddigetstandardallocationdriverdata">DxgkDdiGetStandardAllocationDriverData</a> function. This call generates a description of a surface that can be used for redirection by GDI hardware acceleration and the DWM.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 7.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>
</dt>
<dt>
<a href="display.dxgkddigetstandardallocationdriverdata">DxgkDdiGetStandardAllocationDriverData</a>
</dt>
<dt>
<a href="display.dxgkddipresent">DxgkDdiPresent</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_GDISURFACEDATA structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>