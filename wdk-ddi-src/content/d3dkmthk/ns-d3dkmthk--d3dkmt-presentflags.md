---
UID: NS.d3dkmthk._D3DKMT_PRESENTFLAGS
title: D3DKMT_PRESENTFLAGS
author: windows-driver-content
description: The D3DKMT_PRESENTFLAGS structure identifies how to perform a present operation.
old-location: display\d3dkmt_presentflags.htm
old-project: display
ms.assetid: 2ebee0bd-90f0-4628-8ddf-9e8029b4959a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_PRESENTFLAGS, D3DKMT_PRESENTFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_PRESENTFLAGS
req.alt-loc: d3dkmthk.h
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

# D3DKMT_PRESENTFLAGS structure



## -description
<p>The D3DKMT_PRESENTFLAGS structure identifies how to perform a present operation.</p>


## -syntax

````
typedef struct _D3DKMT_PRESENTFLAGS {
  union {
    struct {
      UINT Blt  :1;
      UINT ColorFill  :1;
      UINT Flip  :1;
      UINT FlipDoNotFlip  :1;
      UINT FlipDoNotWait  :1;
      UINT FlipRestart  :1;
      UINT DstRectValid  :1;
      UINT SrcRectValid  :1;
      UINT RestrictVidPnSource  :1;
      UINT SrcColorKey  :1;
      UINT DstColorKey  :1;
      UINT LinearToSrgb  :1;
      UINT PresentCountValid  :1;
      UINT Rotate  :1;
      UINT PresentToBitmap  :1;
      UINT RedirectedFlip  :1;
      UINT RedirectedBlt  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
      UINT FlipStereo  :1;
      UINT FlipStereoTemporaryMono  :1;
      UINT FlipStereoPreferRight  :1;
      UINT BltStereoUseRight  :1;
      UINT PresentHistoryTokenOnly  :1;
      UINT PresentRegionsValid  :1;
      UINT PresentDDA  :1;
      UINT ProtectedContentBlankedOut  :1;
      UINT RemoteSession  :1;
      UINT Reserved  :6;
#else 
      UINT Reserved  :15;
#endif 
    };
    UINT   Value;
  };
} D3DKMT_PRESENTFLAGS;
````


## -struct-fields
<dl>

### -field Blt

<dd>
<p>A UINT value that specifies whether to bit-block transfer (bitblt) data to the primary surface. This bit-field flag can be used with the <b>DstRectValid</b> and <b>SrcRectValid</b> bit-field flags.</p>
<p>Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).</p>
</dd>

### -field ColorFill

<dd>
<p>A UINT value that specifies whether to perform a colorfill bitblt to the primary surface by using the value in the <b>Color</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-present.md">D3DKMT_PRESENT</a> structure. This bit-field flag can be used with the <b>DstRectValid</b> bit-field flag.</p>
<p>Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).</p>
</dd>

### -field Flip

<dd>
<p>A UINT value that specifies whether to flip to a new surface.</p>
<p>Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).</p>
</dd>

### -field FlipDoNotFlip

<dd>
<p>A UINT value that specifies whether to insert queued waits into the rendering stream. Setting this member indicates to flip to the same surface that is currently being scanned out.</p>
<p>Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).</p>
</dd>

### -field FlipDoNotWait

<dd>
<p>A UINT value that specifies whether the OpenGL installable client driver (ICD) requires that the present operation wait for the number of queued flip surfaces to fall below a particular limit before the operation begins. Setting this member indicates that the ICD does not require waiting. The default limit for the number of queued flip surfaces is three.</p>
<p>Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).</p>
</dd>

### -field FlipRestart

<dd>
<p>A UINT value that specifies whether to restart a flip to a new surface.</p>
<p>Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).</p>
</dd>

### -field DstRectValid

<dd>
<p>A UINT value that specifies whether the bitblt uses a destination rectangular area.</p>
<p>Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).</p>
</dd>

### -field SrcRectValid

<dd>
<p>A UINT value that specifies whether the bitblt uses a source rectangular area.</p>
<p>Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).</p>
</dd>

### -field RestrictVidPnSource

<dd>
<p>A UINT value that specifies whether to restrict the bitblt. If the <b>hWindow</b> member is <b>NULL</b>, the <b>VidPnSourceId</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-present.md">D3DKMT_PRESENT</a> structure indicates which output the full-screen bitblt is directed to; if <b>hWindow</b> is non-<b>NULL</b>, <b>VidPnSourceId</b> indicates which output to restrict the windowed bitblt to.</p>
<p>Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).</p>
</dd>

### -field SrcColorKey

<dd>
<p>A UINT value that specifies whether to perform source color-keying by using the value in the <b>Color</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-present.md">D3DKMT_PRESENT</a> structure. That is, any pixel in the source surface that matches the color key should not be copied to the destination surface, and all of the source pixels that do not match the color key should be copied.</p>
<p>Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).</p>
</dd>

### -field DstColorKey

<dd>
<p>A UINT value that specifies whether to perform destination color-keying by using the value in the <b>Color</b> member of D3DKMT_PRESENT. That is, any pixel in the destination surface that matches the color key should be replaced with the corresponding pixel from the source surface, and all of the destination pixels that do not match the color key should not be replaced. </p>
<p>Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).</p>
</dd>

### -field LinearToSrgb

<dd>
<p>A UINT value that specifies whether to convert the linear-formatted source to sRGB format during the copy operation. sRGB format is gamma corrected. For more information about sRGB format, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a> website.</p>
<p>Setting this member is equivalent to setting the twelfth bit of the 32-bit <b>Value</b> member (0x00000800).</p>
</dd>

### -field PresentCountValid

<dd>
<p>A UINT value that specifies whether the value set in the <b>PresentCount</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-present.md">D3DKMT_PRESENT</a> structure is valid. </p>
<p>Setting this member is equivalent to setting the thirteenth bit of the 32-bit <b>Value</b> member (0x00001000).</p>
</dd>

### -field Rotate

<dd>
<p>[in] A UINT value that specifies whether to rotate the presentation data to match the current orientation of the screen during the presentation bit-block transfer (bitblt). The current orientation of the screen is set in the <b>Rotation</b> member of a <a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-present-path-transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure, which is set in the <b>ContentTransformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-present-path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure for the video present path.</p>
<p>The display miniport driver should rotate the data only if the <b>Rotate</b> bit-field flag is set. Even if the driver determines that the current orientation of the screen is rotated from the presentation data and <b>Rotate</b> is not set, the driver should not rotate the data.</p>
<p>Setting this member is equivalent to setting the fourteenth bit of the 32-bit <b>Value</b> member (0x00002000).</p>
</dd>

### -field PresentToBitmap

<dd>
<p>A UINT value that specifies whether to present to a bitmap. </p>
<p>Setting this member is equivalent to setting the fifteenth bit of the 32-bit <b>Value</b> member (0x00004000).</p>
<p>Supported starting with Windows 7.</p>
</dd>

### -field RedirectedFlip

<dd>
<p>A UINT value that specifies whether to redirect a flip to a new surface.</p>
<p>Setting this member is equivalent to setting the sixteenth bit of the 32-bit <b>Value</b> member (0x00008000).</p>
<p>Supported starting with Windows 7.</p>
</dd>

### -field RedirectedBlt

<dd>
<p>A UINT value that specifies whether to redirect a bitblt to a new surface. </p>
<p>Setting this member is equivalent to setting the seventeenth bit of the 32-bit <b>Value</b> member (0x00010000).</p>
<p>Supported starting with Windows 7.</p>
</dd>

### -field FlipStereo

<dd>
<p>Specifies whether the driver should flip both left and right images of a stereo allocation.</p>
<p>If the <b>FlipOnNextVSync</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-setvidpnsourceaddress-flags.md">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure is  set, the driver should complete the flip to the left image on the next VSync and then complete the flip to the right image on the following VSync.</p>
<p>If the <b>FlipImmediate</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-setvidpnsourceaddress-flags.md">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure is  set, the driver should immediately start to scan out from the new allocation. For example, if the driver was scanning a right image, it should start the new scan from the same relative offset in the right image of the new allocation.</p>
<p>The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.</p>
<p>For more requirements, see the Remarks section.</p>
<p>Setting this member is equivalent to setting the    eighteenth bit of the 32-bit <b>Value</b> member (0x00020000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field FlipStereoTemporaryMono

<dd>
<p>Specifies whether the driver should use the left image of a stereo allocation for the right and left portions of a stereo frame. The driver performs the same present operation as with <b>FlipStereo</b>, except that it should scan out only from the left image to produce both images of a stereo frame.</p>
<p>This member should  be set only if the driver reports support for this option in the current display mode by setting the <b>Type</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-source-mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure to D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN.</p>
<p>The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.</p>
<p>The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.</p>
<p>For more requirements, see the Remarks section.</p>
<p>Setting this member is equivalent to setting the    nineteenth bit of the 32-bit <b>Value</b> member (0x00040000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field FlipStereoPreferRight

<dd>
<p>Specifies that when the driver clones a stereo primary allocation to a mono monitor, it should use the right image.</p>
<p>The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.</p>
<p>For more requirements, see the Remarks section.</p>
<p>Setting this member is equivalent to setting the    twentieth bit of the 32-bit <b>Value</b> member (0x00080000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field BltStereoUseRight

<dd>
<p>Specifies that when the driver presents from a stereo allocation to a mono allocation, it should use the right image. If not set, the driver should use the left image.</p>
<p>Setting this member is equivalent to setting the    twenty-first bit of the 32-bit <b>Value</b> member (0x00100000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field PresentHistoryTokenOnly

<dd>
<p>Specifies that the driver should submit only a present history token.</p>
<p>A <i>present history token</i> is a data packet that the rendering app submits to inform the Desktop Window Manager (DWM) that rendering is complete and the swap chain back buffer is ready to be presented.</p>
<p>Setting this member is equivalent to setting the    twenty-second bit of the 32-bit <b>Value</b> member (0x00200000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field PresentRegionsValid

<dd>
<p>Specifies that the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-present.md">D3DKMT_PRESENT</a>.<b>pPresentRegions</b> member is a valid pointer (not <b>NULL</b>).</p>
<p>Setting this member is equivalent to setting the twenty-third    bit of the 32-bit <b>Value</b> member (0x00400000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field PresentDDA

<dd>
<p>This member is reserved and should be set to zero.</p>
<p>Setting this member is equivalent to setting the twenty-fourth    bit of the 32-bit <b>Value</b> member (0x00800000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field ProtectedContentBlankedOut

<dd>
<p>This member is reserved and should be set to zero.</p>
<p>Setting this member is equivalent to setting the    twenty-fifth bit of the 32-bit <b>Value</b> member (0x01000000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field RemoteSession

<dd>
<p>Specifies that the present operation is directed to a remote session.</p>
<p>Setting this member is equivalent to setting the    twenty-sixth bit of the 32-bit <b>Value</b> member (0x02000000).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 6 bits (0xFC000000) of the 32-bit <b>Value</b> member to zeros.</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 9 bits (0xFF800000) of the 32-bit <b>Value</b> member to zeros.</p>
</dd>

### -field Value

<dd>
<p>A 32-bit value that identifies how to perform the present operation.</p>
</dd>
</dl>

## -remarks
<p>If any of the <b>FlipStereo</b>, <b>FlipStereoTemporaryMono</b>, or <b>FlipStereoPreferRight</b>  members are set, these conditions apply:</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-present-path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-present-path-transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a>
</dt>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-displaymode.md">D3DKMT_DISPLAYMODE</a>
</dt>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-present.md">D3DKMT_PRESENT</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-setvidpnsourceaddress-flags.md">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-setvidpnsourceaddress.md">DXGKARG_SETVIDPNSOURCEADDRESS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_PRESENTFLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>