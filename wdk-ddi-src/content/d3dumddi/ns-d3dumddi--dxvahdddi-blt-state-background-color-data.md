---
UID: NS.d3dumddi._DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA
title: DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure describes data that specifies the background color to fill in the target rectangle of the output.
old-location: display\dxvahdddi_blt_state_background_color_data.htm
old-project: display
ms.assetid: 23eaa88a-a3c3-4630-92b0-d76b266a9c45
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA, DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA
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

# DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure



## -description
<p>The DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure describes data that specifies the background color to fill in the target rectangle of the output. </p>


## -syntax

````
typedef struct _DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA {
  BOOL            YCbCr;
  DXVAHDDDI_COLOR BackgroundColor;
} DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA;
````


## -struct-fields
<dl>

### -field YCbCr

<dd>
<p>[in] A Boolean value that specifies whether the driver should determine whether the <b>BackgroundColor</b> member specifies a YCbCr or RGB color space. The default value is <b>FALSE</b>, which indicates a RGB color space. <b>TRUE</b> specifies a YCbCr color space. </p>
</dd>

### -field BackgroundColor

<dd>
<p>[in] A <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-color.md">DXVAHDDDI_COLOR</a> union that specifies the background color as either a YCbCr or RGB color space. The default value is full range RGB black with opaque alpha, that is (R,G,B,A) = (0.0,0.0,0.0,1.0). </p>
</dd>
</dl>

## -remarks
<p>The color space of the background color is determined by the color space of the output. For more information about output color space, see <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-output-color-space-data.md">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>. </p>

<p>The alpha value of the background color is used when the DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND value is specified in the alpha fill mode (that is, the <b>Mode</b> member of the <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-alpha-fill-data.md">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a> structure) when the DXVAHDDDI_BLT_STATE_ALPHA_FILL value is specified in the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-dxvahd-setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-dxvahd-setvideoprocessbltstate.md">SetVideoProcessBltState</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA is supported beginning with the Windows 7 operating system.</p>
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
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-dxvahd-setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-alpha-fill-data.md">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-output-color-space-data.md">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-color.md">DXVAHDDDI_COLOR</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-dxvahd-setvideoprocessbltstate.md">SetVideoProcessBltState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>