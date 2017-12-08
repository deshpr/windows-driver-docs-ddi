---
UID: NS.d3dumddi._DDRAW_MODE_SPECIFIC_CAPS
title: DDRAW_MODE_SPECIFIC_CAPS
author: windows-driver-content
description: The DDRAW_MODE_SPECIFIC_CAPS structure describes Microsoft DirectDraw capabilities that are specific to a particular display device (head) on the graphics card.
old-location: display\ddraw_mode_specific_caps.htm
old-project: display
ms.assetid: 4434e2cb-af36-446b-b84e-f303ba315cd3
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DDRAW_MODE_SPECIFIC_CAPS, DDRAW_MODE_SPECIFIC_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DDRAW_MODE_SPECIFIC_CAPS
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

# DDRAW_MODE_SPECIFIC_CAPS structure



## -description
<p>The DDRAW_MODE_SPECIFIC_CAPS structure describes Microsoft DirectDraw capabilities that are specific to a particular display device (head) on the graphics card.</p>


## -syntax

````
typedef struct _DDRAW_MODE_SPECIFIC_CAPS {
  UINT Head;
  UINT Caps;
  UINT CKeyCaps;
  UINT FxCaps;
  UINT MaxVisibleOverlays;
  UINT MinOverlayStretch;
  UINT MaxOverlayStretch;
} DDRAW_MODE_SPECIFIC_CAPS;
````


## -struct-fields
<dl>

### -field Head

<dd>
<p>[in] The display device (head) on the multiple-head graphics card to retrieve capabilities about.</p>
</dd>

### -field Caps

<dd>
<p>[out] A valid bitwise OR of the following general capability bits that the driver supports.</p>
<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>MODE_CAPS_OVERLAY (0x00000001)</p>
</td>
<td>
<p>Overlay operations can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CAPS_OVERLAYSTRETCH (0x00000002)</p>
</td>
<td>
<p>Overlay operations can be performed simultaneously with stretching.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CAPS_CANBOBINTERLEAVED (0x00000004)</p>
</td>
<td>
<p>The overlay hardware can display each field of an interlaced video stream individually while it is interleaved in memory without causing any artifacts that might typically occur without special hardware support. This option is valid only when the surface is receiving data from a VPE object and is valid only when the video is zoomed at least 200 percent in the vertical direction.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CAPS_CANBOBNONINTERLEAVED (0x00000008)</p>
</td>
<td>
<p>The overlay hardware can display each field of an interlaced video stream individually while it is not interleaved in memory without causing any artifacts that might typically occur without special hardware support. This option is valid only when the surface is receiving data from a VPE object and is valid only when the video is zoomed at least 200 percent in the vertical direction.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CAPS_CANFLIPODDEVEN (0x00000010)</p>
</td>
<td>
<p>The driver supports bob-style deinterlacing that uses software without using a VPE object.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CAPS_READSCANLINE (0x00000020)</p>
</td>
<td>
<p>The current scan line can be read and returned.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CAPS_COLORCONTROLOVERLAY (0x00000040)</p>
</td>
<td>
<p>The driver supports color-control settings for an overlay. For information about setting and retrieving color-control settings, see the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-getoverlaycolorcontrols.md">GetOverlayColorControls</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-setoverlaycolorcontrols.md">SetOverlayColorControls</a> functions.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field CKeyCaps

<dd>
<p>[out] A valid bitwise OR of the following color key capability bits that the driver supports.</p>
<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>MODE_CKEYCAPS_DESTOVERLAY (0x00000001)</p>
</td>
<td>
<p>Overlaying operations that use color keying of the replaceable bits of the destination surface that is being overlaid for RGB colors can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CKEYCAPS_DESTOVERLAYYUV (0x00000002)</p>
</td>
<td>
<p>Overlaying operations that use color keying of the replaceable bits of the destination surface that is being overlaid for YUV colors can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CKEYCAPS_SRCOVERLAY (0x00000004)</p>
</td>
<td>
<p>Overlaying operations that use the color key for the source with this overlay surface for RGB colors can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CKEYCAPS_SRCOVERLAYCLRSPACE (0x00000008)</p>
</td>
<td>
<p>Overlaying operations that use a color space as the source color key for the overlay surface for RGB colors can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CKEYCAPS_SRCOVERLAYCLRSPACEYUV (0x00000010)</p>
</td>
<td>
<p>Overlaying operations that use a color space as the source color key for the overlay surface for YUV colors can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_CKEYCAPS_SRCOVERLAYYUV (0x00000020)</p>
</td>
<td>
<p>Overlaying operations that use the color key for the source with this overlay surface for YUV colors can be performed.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field FxCaps

<dd>
<p>[out] A valid bitwise OR of the following effects capability bits that the driver supports.</p>
<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>MODE_FXCAPS_OVERLAYSHRINKX (0x00000001)</p>
</td>
<td>
<p>Arbitrary shrinking of an overlay surface along the x-axis (horizontally) can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_FXCAPS_OVERLAYSHRINKY (0x00000002)</p>
</td>
<td>
<p>Arbitrary shrinking of an overlay surface along the y-axis (vertically) can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_FXCAPS_OVERLAYSTRETCHX (0x00000004)</p>
</td>
<td>
<p>Arbitrary stretching of an overlay surface along the x-axis (horizontally) can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_FXCAPS_OVERLAYSTRETCHY (0x00000008)</p>
</td>
<td>
<p>Arbitrary stretching of an overlay surface along the y-axis (vertically) can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_FXCAPS_OVERLAYMIRRORLEFTRIGHT (0x00000010)</p>
</td>
<td>
<p>Mirroring of overlays around the vertical axis can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_FXCAPS_OVERLAYMIRRORUPDOWN (0x00000020)</p>
</td>
<td>
<p>Mirroring of overlays across the horizontal axis can be performed.</p>
</td>
</tr>
<tr>
<td>
<p>MODE_FXCAPS_OVERLAYDEINTERLACE (0x00000040)</p>
</td>
<td>
<p>Deinterlacing of an overlay surface can be performed.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field MaxVisibleOverlays

<dd>
<p>[out] The maximum number of visible overlays.</p>
</dd>

### -field MinOverlayStretch

<dd>
<p>[out] The minimum overlay stretch factor multiplied by 1000. For example, a factor of 1.3 should be stored as 1300. The display driver must set the minimum factor to the actual minimum to which the graphics hardware can shrink the overlay. If the graphics hardware has no minimum limitation, set <b>MinOverlayStretch</b> to 1.</p>
</dd>

### -field MaxOverlayStretch

<dd>
<p>[out] The maximum overlay stretch factor multiplied by 1000. For example, a factor of 1.3 should be stored as 1300. The display driver must set the maximum factor to the actual maximum to which the graphics hardware can stretch the overlay. If the graphics hardware has no maximum limitation, set <b>MaxOverlayStretch</b> to 32000.</p>
</dd>
</dl>

## -remarks
<p>Capabilities can change between heads of a multiple-headed graphics card and can change after a display mode change.</p>

## -requirements
<table>
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
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-getcaps.md">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi--d3dddicaps-type.md">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-getcaps.md">GetCaps</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDRAW_MODE_SPECIFIC_CAPS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>