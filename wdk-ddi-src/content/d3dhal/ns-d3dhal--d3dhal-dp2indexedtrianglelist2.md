---
UID: NS.d3dhal._D3DHAL_DP2INDEXEDTRIANGLELIST2
title: D3DHAL_DP2INDEXEDTRIANGLELIST2
author: windows-driver-content
description: One or more D3DHAL_DP2INDEXEDTRIANGLELIST2 structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLELIST2, and are used to render a sequence of unconnected triangles using vertex indices.
old-location: display\d3dhal_dp2indexedtrianglelist2.htm
old-project: display
ms.assetid: 04d11aef-2766-42d6-abda-f0b25d53ef8f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2INDEXEDTRIANGLELIST2, D3DHAL_DP2INDEXEDTRIANGLELIST2, *LPD3DHAL_DP2INDEXEDTRIANGLELIST2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_DP2INDEXEDTRIANGLELIST2
req.alt-loc: d3dhal.h
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

# D3DHAL_DP2INDEXEDTRIANGLELIST2 structure



## -description
<p>One or more D3DHAL_DP2INDEXEDTRIANGLELIST2 structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDTRIANGLELIST2, and are used to render a sequence of unconnected triangles using vertex indices.</p>


## -syntax

````
typedef struct _D3DHAL_DP2INDEXEDTRIANGLELIST2 {
  WORD wV1;
  WORD wV2;
  WORD wV3;
} D3DHAL_DP2INDEXEDTRIANGLELIST2, *LPD3DHAL_DP2INDEXEDTRIANGLELIST2;
````


## -struct-fields
<dl>

### -field wV1

<dd>
<p>Specifies the index to the vertex buffer location containing coordinate data for the first vertex of the triangle.</p>
</dd>

### -field wV2

<dd>
<p>Specifies the index to the vertex buffer location containing coordinate data for the second vertex of the triangle.</p>
</dd>

### -field wV3

<dd>
<p>Specifies the index to the vertex buffer location containing coordinate data for the third vertex of the triangle.</p>
</dd>
</dl>

## -remarks
<p>The D3DHAL_DP2INDEXEDTRIANGLELIST2 structure specifies unconnected triangles to render with a vertex buffer. The vertex indexes are specified by <i>wV1</i>, <i>wV2</i>, and <i>wV3</i>. All edges are visible. The number of triangles to render (that is, the number of D3DHAL_DP2INDEXEDTRIANGLELIST2 structures to process) is specified by the <b>wPrimitiveCount</b> field of D3DHAL_DP2COMMAND. All indexes are relative to a vertex whose index is <i>wVStart</i> from <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a>. The sequence in the command stream is D3DHAL_DP2COMMAND followed by D3DHAL_DP2STARTVERTEX followed by <b>wPrimitiveCount</b>D3DHAL_DP2INDEXEDTRIANGLELIST2 structures.</p>

<p>The <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback parses D3DHAL_DP2INDEXEDTRIANGLELIST2 structure(s) from the command buffer and renders the triangles using vertex indexes when D3DHAL_DP2COMMAND is D3DDP2OP_INDEXEDTRIANGLELIST2. A D3DHAL_DP2STARTVERTEX structure immediately follows the D3DHAL_DP2COMMAND in the command stream. This allows a base index to be specified for all the indexes that follow it. Thus triangles can be easily relocated and no flags are necessary to specify the triangle edges as is the case with D3DDP2OP_INDEXEDTRIANGLELIST.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>D3DDP2OP_INDEXEDTRIANGLELIST</dt>
<dt>D3DDP2OP_INDEXEDTRIANGLELIST2</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2INDEXEDTRIANGLELIST2 structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>