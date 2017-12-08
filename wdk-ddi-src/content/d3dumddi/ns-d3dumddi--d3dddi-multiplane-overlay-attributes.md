---
UID: NS.d3dumddi._D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
title: D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
author: windows-driver-content
description: Used by the user-mode display driver to specify overlay plane attributes.
old-location: display\d3dddi_multiplane_overlay_attributes.htm
old-project: display
ms.assetid: 6f758785-5d7f-4d63-82c7-93ced5de3da4
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES, D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
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

# D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES structure



## -description
<p>Used by the user-mode display driver to specify overlay plane attributes.</p>


## -syntax

````
typedef struct _D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES {
  UINT                                         Flags;
  RECT                                         SrcRect;
  RECT                                         DstRect;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  RECT                                         ClipRect;
#endif 
  D3DDDI_ROTATION                              Rotation;
  D3DDDI_MULTIPLANE_OVERLAY_BLEND              Blend;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  UINT                                         DirtyRectCount;
  RECT                                         *pDirtyRects;
#else 
  UINT                                         NumFilters;
  void                                         *pFilters;
#endif 
  D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT VideoFrameFormat;
  UINT                                         YCbCrFlags;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY    StretchQuality;
#endif 
} D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field Flags

<dd>
<p>Specifies a flip operation as one of the applicable values in the <a href="..\d3dumddi\ne-d3dumddi--d3dddi-multiplane-overlay-flags.md">D3DDDI_MULTIPLANE_OVERLAY_FLAGS</a> enumeration.</p>
</dd>

### -field SrcRect

<dd>
<p>Specifies the source rectangle, of type <a href="display.rect">RECT</a>, relative to the source resource.</p>
</dd>

### -field DstRect

<dd>
<p>Specifies the destination rectangle, of type <a href="display.rect">RECT</a>, relative to the monitor resolution.</p>
</dd>

### -field ClipRect

<dd>
<p>Specifies any additional clipping, of type <a href="display.rect">RECT</a>, relative to the <b>DstRect</b> rectangle, after the data has been stretched according to the values of <b>SrcRect</b> and <b>DstRect</b>.</p>
<p>The driver and hardware can use the <b>ClipRect</b> member to apply a common stretch factor as the clipping changes when an app occludes part of the <b>DstRect</b> destination rectangle.</p>
</dd>

### -field Rotation

<dd>
<p>Specifies the clockwise rotation of the overlay plane, given as a value from the <a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-rotation.md">D3DDDI_ROTATION</a> enumeration.</p>
</dd>

### -field Blend

<dd>
<p>Specifies the blend mode that applies to this overlay plane and the plane beneath it, given as a value from the <a href="..\d3dumddi\ne-d3dumddi--d3dddi-multiplane-overlay-blend.md">D3DDDI_MULTIPLANE_OVERLAY_BLEND</a> enumeration.</p>
</dd>

### -field DirtyRectCount

<dd>
<p>The number of dirty rectangles specified for the overlay plane. If zero, the entire plane is considered dirty.</p>
</dd>

### -field pDirtyRects

<dd>
<p>A pointer to an array of dirty rectangles (<a href="display.rect">RECT</a>s), relative to the source rectangle <b>SrcRect</b>, that indicate the portion of the overlay plane that has changed.</p>
<p>The driver can use this member to perform optimizations, though it's not required to use the dirty rectangle info. However, the driver should never fail a function call based on the provided dirty rectangles.</p>
</dd>

### -field NumFilters

<dd>
<p>Optionally specifies the number of filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.</p>
</dd>

### -field pFilters

<dd>
<p>An optional pointer to a buffer that specifies the filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.</p>
</dd>

### -field VideoFrameFormat

<dd>
<p>Specifies the overlay plane's video frame format, given as a value from the <a href="..\d3dumddi\ne-d3dumddi-d3dddi-multiplane-overlay-video-frame-format.md">D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a> enumeration.</p>
<div class="alert"><b>Note</b>  This value must always be <b>DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b>. The operating system does not support the other enumeration values.</div>
<div> </div>
</dd>

### -field YCbCrFlags

<dd>
<p>Specifies YUV range and conversion info given as a value from the <a href="..\d3dumddi\ne-d3dumddi-d3dddi-multiplane-overlay-ycbcr-flags.md">D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a> enumeration.</p>
</dd>

### -field StretchQuality

<dd>
<p>Specifies the overlay plane's stretch quality, given as a value from the <a href="..\d3dumddi\ne-d3dumddi-d3dddi-multiplane-overlay-stretch-quality.md">D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a> enumeration.</p>
</dd>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ne-d3dumddi--d3dddi-multiplane-overlay-blend.md">D3DDDI_MULTIPLANE_OVERLAY_BLEND</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi--d3dddi-multiplane-overlay-flags.md">D3DDDI_MULTIPLANE_OVERLAY_FLAGS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-d3dddi-multiplane-overlay-stretch-quality.md">D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-d3dddi-multiplane-overlay-video-frame-format.md">D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-d3dddi-multiplane-overlay-ycbcr-flags.md">D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-rotation.md">D3DDDI_ROTATION</a>
</dt>
<dt>
<a href="display.rect">RECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>