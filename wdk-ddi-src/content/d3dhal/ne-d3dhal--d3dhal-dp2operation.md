---
UID: NE.d3dhal._D3DHAL_DP2OPERATION
title: D3DHAL_DP2OPERATION
author: windows-driver-content
description: The D3DHAL_DP2OPERATION enumerated type specifies the D3dDrawPrimitives2 operation in the bCommand member of the D3DHAL_DP2COMMAND structure.
old-location: display\d3dhal_dp2operation.htm
old-project: display
ms.assetid: d6ff2f23-0b51-4bfc-8172-84a5a39f7785
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DTRANSFORMCAPS, D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_DP2OPERATION
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

# D3DHAL_DP2OPERATION enumeration



## -description
<p>The D3DHAL_DP2OPERATION enumerated type specifies the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> operation in the <b>bCommand</b> member of the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure. The enumerators of D3DHAL_DP2OPERATION can specify either primitive-rendering or nonprimitive-rendering operations. The enumerators of D3DHAL_DP2OPERATION can also specify that the driver returned responses to previously issued queries. </p>


## -syntax

````
typedef enum _D3DHAL_DP2OPERATION { 
  D3DDP2OP_POINTS                    = 1,
  D3DDP2OP_INDEXEDLINELIST           = 2,
  D3DDP2OP_INDEXEDTRIANGLELIST       = 3,
  D3DDP2OP_RENDERSTATE               = 8,
  D3DDP2OP_LINELIST                  = 15,
  D3DDP2OP_LINESTRIP                 = 16,
  D3DDP2OP_INDEXEDLINESTRIP          = 17,
  D3DDP2OP_TRIANGLELIST              = 18,
  D3DDP2OP_TRIANGLESTRIP             = 19,
  D3DDP2OP_INDEXEDTRIANGLESTRIP      = 20,
  D3DDP2OP_TRIANGLEFAN               = 21,
  D3DDP2OP_INDEXEDTRIANGLEFAN        = 22,
  D3DDP2OP_TRIANGLEFAN_IMM           = 23,
  D3DDP2OP_LINELIST_IMM              = 24,
  D3DDP2OP_TEXTURESTAGESTATE         = 25,
  D3DDP2OP_INDEXEDTRIANGLELIST2      = 26,
  D3DDP2OP_INDEXEDLINELIST2          = 27,
  D3DDP2OP_VIEWPORTINFO              = 28,
  D3DDP2OP_WINFO                     = 29,
  D3DDP2OP_SETPALETTE                = 30,
  D3DDP2OP_UPDATEPALETTE             = 31,
#if (DIRECT3D_VERSION >= 0x0700)
  D3DDP2OP_ZRANGE                    = 32,
  D3DDP2OP_SETMATERIAL               = 33,
  D3DDP2OP_SETLIGHT                  = 34,
  D3DDP2OP_CREATELIGHT               = 35,
  D3DDP2OP_SETTRANSFORM              = 36,
  D3DDP2OP_TEXBLT                    = 38,
  D3DDP2OP_STATESET                  = 39,
  D3DDP2OP_SETPRIORITY               = 40,
#endif 
  D3DDP2OP_SETRENDERTARGET           = 41,
  D3DDP2OP_CLEAR                     = 42,
#if (DIRECT3D_VERSION >= 0x0700)
  D3DDP2OP_SETTEXLOD                 = 43,
  D3DDP2OP_SETCLIPPLANE              = 44,
#endif 
#if (DIRECT3D_VERSION >= 0x0800)
  D3DDP2OP_CREATEVERTEXSHADER        = 45,
  D3DDP2OP_DELETEVERTEXSHADER        = 46,
  D3DDP2OP_SETVERTEXSHADER           = 47,
  D3DDP2OP_SETVERTEXSHADERCONST      = 48,
  D3DDP2OP_SETSTREAMSOURCE           = 49,
  D3DDP2OP_SETSTREAMSOURCEUM         = 50,
  D3DDP2OP_SETINDICES                = 51,
  D3DDP2OP_DRAWPRIMITIVE             = 52,
  D3DDP2OP_DRAWINDEXEDPRIMITIVE      = 53,
  D3DDP2OP_CREATEPIXELSHADER         = 54,
  D3DDP2OP_DELETEPIXELSHADER         = 55,
  D3DDP2OP_SETPIXELSHADER            = 56,
  D3DDP2OP_SETPIXELSHADERCONST       = 57,
  D3DDP2OP_CLIPPEDTRIANGLEFAN        = 58,
  D3DDP2OP_DRAWPRIMITIVE2            = 59,
  D3DDP2OP_DRAWINDEXEDPRIMITIVE2     = 60,
  D3DDP2OP_DRAWRECTPATCH             = 61,
  D3DDP2OP_DRAWTRIPATCH              = 62,
  D3DDP2OP_VOLUMEBLT                 = 63,
  D3DDP2OP_BUFFERBLT                 = 64,
  D3DDP2OP_MULTIPLYTRANSFORM         = 65,
  D3DDP2OP_ADDDIRTYRECT              = 66,
  D3DDP2OP_ADDDIRTYBOX               = 67,
#endif 
#if (DIRECT3D_VERSION >= 0x0900)
  D3DDP2OP_CREATEVERTEXSHADERDECL    = 71,
  D3DDP2OP_DELETEVERTEXSHADERDECL    = 72,
  D3DDP2OP_SETVERTEXSHADERDECL       = 73,
  D3DDP2OP_CREATEVERTEXSHADERFUNC    = 74,
  D3DDP2OP_DELETEVERTEXSHADERFUNC    = 75,
  D3DDP2OP_SETVERTEXSHADERFUNC       = 76,
  D3DDP2OP_SETVERTEXSHADERCONSTI     = 77,
  D3DDP2OP_SETSCISSORRECT            = 79,
  D3DDP2OP_SETSTREAMSOURCE2          = 80,
  D3DDP2OP_BLT                       = 81,
  D3DDP2OP_COLORFILL                 = 82,
  D3DDP2OP_SETVERTEXSHADERCONSTB     = 83,
  D3DDP2OP_CREATEQUERY               = 84,
  D3DDP2OP_SETRENDERTARGET2          = 85,
  D3DDP2OP_SETDEPTHSTENCIL           = 86,
  D3DDP2OP_RESPONSECONTINUE          = 87,
  D3DDP2OP_RESPONSEQUERY             = 88,
  D3DDP2OP_GENERATEMIPSUBLEVELS      = 89,
  D3DDP2OP_DELETEQUERY               = 90,
  D3DDP2OP_ISSUEQUERY                = 91,
  D3DDP2OP_SETPIXELSHADERCONSTI      = 93,
  D3DDP2OP_SETPIXELSHADERCONSTB      = 94,
  D3DDP2OP_SETSTREAMSOURCEFREQ       = 95,
  D3DDP2OP_SURFACEBLT                = 96,
  D3DDP2OP_SETCONVOLUTIONKERNELMONO  = 97,
  D3DDP2OP_COMPOSERECTS              = 98

#endif } D3DHAL_DP2OPERATION;
````


## -enum-fields
<dl>

### -field D3DDP2OP_POINTS

<dd>
<p>Draws a list of indexed or nonindexed points. Each list is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2points.md">D3DHAL_DP2POINTS</a> structures.</p>
</dd>

### -field D3DDP2OP_INDEXEDLINELIST

<dd>
<p>Draws a list of lines, with each line specified by a pair of vertex indexes. The indexed line list is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2indexedlinelist.md">D3DHAL_DP2INDEXEDLINELIST</a> structures.</p>
</dd>

### -field D3DDP2OP_INDEXEDTRIANGLELIST

<dd>
<p>Draws a list of triangles. Each triangle is specified by three indexes into the vertex buffer, one index per triangle vertex. The triangle list is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2indexedtrianglelist.md">D3DHAL_DP2INDEXEDTRIANGLELIST</a> structures.</p>
</dd>

### -field D3DDP2OP_RENDERSTATE

<dd>
<p>Specifies a render state change that requires processing. The rendering state to change is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2renderstate.md">D3DHAL_DP2RENDERSTATE</a> structures.</p>
</dd>

### -field D3DDP2OP_LINELIST

<dd>
<p>Draws a list of lines. Each line is specified by a pair of vertices. The vertices are processed in sequential order starting at an initial specified vertex index. The line list is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2linelist.md">D3DHAL_DP2LINELIST</a> structure.</p>
</dd>

### -field D3DDP2OP_LINESTRIP

<dd>
<p>Draws a connected strip of lines defined by a sequence of vertices starting at an initial specified vertex index. The line strip is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2linestrip.md">D3DHAL_DP2LINESTRIP</a> structure.</p>
</dd>

### -field D3DDP2OP_INDEXEDLINESTRIP

<dd>
<p>Draws a connected strip of lines defined by a sequence of vertex indexes. Each line in the connected strip is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2indexedlinestrip.md">D3DHAL_DP2INDEXEDLINESTRIP</a> structure.</p>
</dd>

### -field D3DDP2OP_TRIANGLELIST

<dd>
<p>Draws a list of triangles. Each triangle is specified by three vertices that are processed starting at an initial specified vertex index. The triangles are processed in sequential order. The triangle list is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2trianglelist.md">D3DHAL_DP2TRIANGLELIST</a> structure.</p>
</dd>

### -field D3DDP2OP_TRIANGLESTRIP

<dd>
<p>Draws a connected strip of triangles. Each triangle is specified by a sequence of vertices starting at an initial specified vertex index. The three most current vertices are used to draw each triangle. The triangle strip is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2trianglestrip.md">D3DHAL_DP2TRIANGLESTRIP</a> structure.</p>
</dd>

### -field D3DDP2OP_INDEXEDTRIANGLESTRIP

<dd>
<p>Draws a connected strip of triangles that are specified by a sequence of vertex indexes. The three most current vertex indexes are used to draw each triangle. Each triangle in the connected strip is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2indexedtrianglestrip.md">D3DHAL_DP2INDEXEDTRIANGLESTRIP</a> structure.</p>
</dd>

### -field D3DDP2OP_TRIANGLEFAN

<dd>
<p>Draws a triangle fan. The fan is specified by a sequence of vertices that start at an initial specified vertex index. The triangle fan is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2trianglefan.md">D3DHAL_DP2TRIANGLEFAN</a> structure.</p>
</dd>

### -field D3DDP2OP_INDEXEDTRIANGLEFAN

<dd>
<p>Draws a triangle fan. The triangle fan is specified by a sequence of vertex indexes. Each triangle in the fan is specified by a <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2indexedtrianglefan.md">D3DHAL_DP2INDEXEDTRIANGLEFAN</a> structure.</p>
</dd>

### -field D3DDP2OP_TRIANGLEFAN_IMM

<dd>
<p>Draws a triangle fan. The fan is specified by a sequence of vertices stored in the command stream (immediate data). The <b>wPrimitiveCount</b> member of the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure specifies the number of triangles to render. The type and size of the vertices are specified by the <b>dwVertexType</b> member of the <a href="..\d3dhal\ns-d3dhal--d3dhal-drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure.</p>
</dd>

### -field D3DDP2OP_LINELIST_IMM

<dd>
<p>Draws a set of lines. Each line is specified by a pair of vertices stored in the command stream (immediate data). The <b>wPrimitiveCount</b> member of the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure specifies how many pairs of vertices follow. The type and size of the vertices are determined by the <b>dwVertexType</b> member of the <a href="..\d3dhal\ns-d3dhal--d3dhal-drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure.</p>
</dd>

### -field D3DDP2OP_TEXTURESTAGESTATE

<dd>
<p>Specifies a texture render state change that requires processing. The render state to change is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2texturestagestate.md">D3DHAL_DP2TEXTURESTAGESTATE</a> structures. The value in the <b>TSState</b> member specifies the texture state to be updated.</p>
</dd>

### -field D3DDP2OP_INDEXEDTRIANGLELIST2

<dd>
<p>Draws a list of triangles. Each triangle is specified by three indexes into the vertex buffer, one index per triangle vertex. The triangle list is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2indexedtrianglelist2.md">D3DHAL_DP2INDEXEDTRIANGLELIST2</a> structures.</p>
</dd>

### -field D3DDP2OP_INDEXEDLINELIST2

<dd>
<p>Draws a list of lines. Each line is specified by a pair of vertex indexes, with each offset from the beginning of the vertex buffer by a fixed amount. The indexed line list is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2indexedlinelist.md">D3DHAL_DP2INDEXEDLINELIST</a> structures.</p>
</dd>

### -field D3DDP2OP_VIEWPORTINFO

<dd>
<p>Specifies the clipping rectangle that is used for guard-band clipping by guard-band aware drivers. The clipping rectangle (that is, the viewing rectangle) is specified by the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2viewportinfo.md">D3DHAL_DP2VIEWPORTINFO</a> structure.</p>
</dd>

### -field D3DDP2OP_WINFO

<dd>
<p>Specifies the w range for w buffering. This range is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2winfo.md">D3DHAL_DP2WINFO</a> structures.</p>
</dd>

### -field D3DDP2OP_SETPALETTE

<dd>
<p>Specifies that the palette is being set for a texture. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2setpalette.md">D3DHAL_DP2SETPALETTE</a>.</p>
</dd>

### -field D3DDP2OP_UPDATEPALETTE

<dd>
<p>Specifies that a texture palette is to be updated. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2updatepalette.md">D3DHAL_DP2UPDATEPALETTE</a>.</p>
</dd>

### -field D3DDP2OP_ZRANGE

<dd>
<p>Specifies the range of z values. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2zrange.md">D3DHAL_DP2ZRANGE</a>.</p>
</dd>

### -field D3DDP2OP_SETMATERIAL

<dd>
<p>Sets the properties for a material. D3DHAL_DP2SETMATERIAL is a D3DMATERIAL7 structure (described in the DirectX SDK documentation) that is used to set the material properties.</p>
</dd>

### -field D3DDP2OP_SETLIGHT

<dd>
<p>Specifies that a light is being set. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2setlight.md">D3DHAL_DP2SETLIGHT</a>.</p>
</dd>

### -field D3DDP2OP_CREATELIGHT

<dd>
<p>Creates a light. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2createlight.md">D3DHAL_DP2CREATELIGHT</a>.</p>
</dd>

### -field D3DDP2OP_SETTRANSFORM

<dd>
<p>Sets up a transform. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2settransform.md">D3DHAL_DP2SETTRANSFORM</a>.</p>
</dd>

### -field D3DDP2OP_TEXBLT

<dd>
<p>Specifies a blt operation from a source texture to a destination texture. It is used as a more efficient alternative to the DirectDraw <a href="display.ddblt">DdBlt</a> DDI. It is specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2texblt.md">D3DHAL_DP2TEXBLT</a> structures. Because Direct3D drivers maintain all the state necessary to do a blt (for example, texture handles and blending modes), a blt can be accomplished with just the information in the D3DDP2OP_TEXBLT opcode. This new token signals the driver that a texture has to be transferred from system memory into local or nonlocal video memory.</p>
</dd>

### -field D3DDP2OP_STATESET

<dd>
<p>Specifies a state-set operation to perform. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2stateset.md">D3DHAL_DP2STATESET</a>.</p>
</dd>

### -field D3DDP2OP_SETPRIORITY

<dd>
<p>Sets the priority of a managed texture. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2setpriority.md">D3DHAL_DP2SETPRIORITY</a>.</p>
</dd>

### -field D3DDP2OP_SETRENDERTARGET

<dd>
<p>Sets the render target. Direct3D drivers must respond to this opcode exactly the same as with the older <i>SetRenderTarget</i> callback. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2setrendertarget.md">D3DHAL_DP2SETRENDERTARGET</a>.</p>
</dd>

### -field D3DDP2OP_CLEAR

<dd>
<p>Specifies a clear operation. Replaces the <i>Clear</i> and <i>Clear2</i> callbacks. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2clear.md">D3DHAL_DP2CLEAR</a>.</p>
</dd>

### -field D3DDP2OP_SETTEXLOD

<dd>
<p>Indicates that the level of detail (LOD) for MIP maps is being set. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2settexlod.md">D3DHAL_DP2SETTEXLOD</a>.</p>
</dd>

### -field D3DDP2OP_SETCLIPPLANE

<dd>
<p>Specifies that a user-defined clip plane is being used. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2setclipplane.md">D3DHAL_DP2SETCLIPPLANE</a>.</p>
</dd>

### -field D3DDP2OP_CREATEVERTEXSHADER

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver when a vertex shader is created. This token gives the driver the opportunity to convert the vertex shader declaration and code into a hardware specific format and associate this information with the given shader handle. See D3DHAL_DP2CREATEVERTEXSHADER.

</dl>
</dd>

### -field D3DDP2OP_DELETEVERTEXSHADER

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to notify the driver of the deletion of a vertex shader and to give the driver an opportunity to clean up any driver side resources associated with the given vertex shader. Note that this uses the same structure (D3DHAL_DP2VERTEXSHADER) as D3DDP2OP_SETVERTEXSHADER.

</dl>
</dd>

### -field D3DDP2OP_SETVERTEXSHADER

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is passed to the driver to set the current vertex shader. All subsequent drawing operations should use the given shader until another is selected. Note that this uses the same structure (D3DHAL_DP2VERTEXSHADER) as D3DDP2OP_DELETEVERTEXSHADER.

</dl>
</dd>

### -field D3DDP2OP_SETVERTEXSHADERCONST

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is passed to the driver to set one or more vertex shader constant registers with float values. The constant registers are specified by a D3DHAL_DP2SETVERTEXSHADERCONST structure. One or more vectors of four single precision floating-point values immediately follow the D3DHAL_DP2SETVERTEXSHADERCONST data structure in the DP2 stream. 

</dl>
</dd>

### -field D3DDP2OP_SETSTREAMSOURCE

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field Binds a vertex stream source to a vertex buffer. See D3DHAL_DP2SETSTREAMSOURCE.

</dl>
</dd>

### -field D3DDP2OP_SETSTREAMSOURCEUM

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field Binds a vertex stream source to a user memory buffer. See D3DHAL_DP2SETSTREAMSOURCEUM.

</dl>
</dd>

### -field D3DDP2OP_SETINDICES

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field Sets the current index buffer. See D3DHAL_DP2SETINDICES.

</dl>
</dd>

### -field D3DDP2OP_DRAWPRIMITIVE

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to draw nonindexed primitives. D3DDP2OP_DRAWPRIMITIVE2 is used if the vertex data has been transformed by the runtime. The primitives are specified by one or more D3DHAL_DP2DRAWPRIMITIVE structures.

</dl>
</dd>

### -field D3DDP2OP_DRAWINDEXEDPRIMITIVE

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to draw indexed primitives. D3DDP2OP_DRAWINDEXEDPRIMITIVE2 is used if the vertex data has been transformed by the runtime. The indexed primitives are specified by one or more D3DHAL_DP2DRAWINDEXEDPRIMITIVE structures.

</dl>
</dd>

### -field D3DDP2OP_CREATEPIXELSHADER

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver when a pixel shader is created. This token gives the driver the opportunity to convert the pixel shader code into a hardware specific format and associate this information with the given shader handle. See D3DHAL_DP2CREATEPIXELSHADER.

</dl>
</dd>

### -field D3DDP2OP_DELETEPIXELSHADER

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to notify the driver of the deletion of a pixel shader and to give the driver an opportunity to clean up any driver side resources associated with the given pixel shader. Note that this uses the same structure (D3DHAL_DP2PIXELSHADER) as D3DDP2OP_SETVPIXELSHADER.

</dl>
</dd>

### -field D3DDP2OP_SETPIXELSHADER

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is passed to the driver to set the current pixel shader. All subsequent drawing operations should use the given shader until another is selected. Note that this uses the same structure (D3DHAL_DP2PIXELSHADER) as D3DDP2OP_DELETEPIXELSHADER.

</dl>
</dd>

### -field D3DDP2OP_SETPIXELSHADERCONST

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is passed to the driver to set one or more pixel shader constant registers. See D3DHAL_DP2SETPIXELSHADERCONST.

</dl>
</dd>

### -field D3DDP2OP_CLIPPEDTRIANGLEFAN

<dd>
<p>
      DirectX 8.0 and later versions only.This token is sent to the driver to draw transformed, clipped triangle fans. This token is a replacement for the DirectX 7.0 tokens that used inline vertices in the command stream. The triangle fans are specified by one or more <a href="..\d3dhal\ns-d3dhal--d3dhal-clippedtrianglefan.md">D3DHAL_CLIPPEDTRIANGLEFAN</a> structures.</p>
</dd>

### -field D3DDP2OP_DRAWPRIMITIVE2

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to draw nonindexed primitives where the vertex data has been transformed by the runtime. Stream zero contains transform and lit vertices and is the only stream that should be accessed. The primitives are specified by one or more D3DHAL_DP2DRAWPRIMITIVE2 structures.

</dl>
</dd>

### -field D3DDP2OP_DRAWINDEXEDPRIMITIVE2

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to draw indexed primitives if the vertex data has been transformed by the runtime. Stream zero contains transform and lit vertices and is the only stream that should be accessed. The indexed primitives are specified by one or more D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structures.

</dl>
</dd>

### -field D3DDP2OP_DRAWRECTPATCH

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to draw a new rectangular patch, to draw a cached rectangular patch, or to update the specification of a previously defined patch. The patches are specified by one or more D3DHAL_DP2DRAWRECTPATCH structures.

</dl>
</dd>

### -field D3DDP2OP_DRAWTRIPATCH

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field This token is sent to the driver to draw a new triangular patch, to draw a cached triangular patch, or to update the specification of a previously defined patch. The patches are specified by one or more D3DHAL_DP2DRAWTRIPATCH structures.

</dl>
</dd>

### -field D3DDP2OP_VOLUMEBLT

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field Specifies a blt operation from a source volume texture to a destination volume texture. It is specified by one or more D3DHAL_DP2VOLUMEBLT structures.

</dl>
</dd>

### -field D3DDP2OP_BUFFERBLT

<dd>
<dl>

### -field 
      DirectX 8.0 and later versions only.
      


### -field Specifies a blt operation from a source vertex or index buffer to a destination vertex or index buffer. It is specified by one or more D3DHAL_DP2BUFFERBLT structures.

</dl>
</dd>

### -field D3DDP2OP_MULTIPLYTRANSFORM

<dd>
<p>
      DirectX 8.0 and later versions only. Multiplies a current transform. See <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2multiplytransform.md">D3DHAL_DP2MULTIPLYTRANSFORM</a>.</p>
</dd>

### -field D3DDP2OP_ADDDIRTYRECT

<dd>
<dl>

### -field 
      DirectX 8.1 and later versions only.
      


### -field Specifies that a portion of a 2D resource--a 2D texture or cube texture--was dirtied in system memory. This 2D texture is specified in a D3DHAL_DP2ADDDIRTYRECT structure. This 2D texture must be reloaded into video memory before being used.

</dl>
</dd>

### -field D3DDP2OP_ADDDIRTYBOX

<dd>
<dl>

### -field 
      DirectX 8.1 and later versions only.
      


### -field Specifies that a portion of a 3D resource--a volume texture--was dirtied in system memory. This volume texture is specified in a D3DHAL_DP2ADDDIRTYBOX structure. This volume must be reloaded into video memory before being used.

</dl>
</dd>

### -field D3DDP2OP_CREATEVERTEXSHADERDECL

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is sent to the driver when a vertex shader declaration is created. This token gives the driver the opportunity to convert the vertex shader declaration into a hardware specific format and associate this information with the given shader handle. See D3DHAL_DP2CREATEVERTEXSHADERDECL.

</dl>
</dd>

### -field D3DDP2OP_DELETEVERTEXSHADERDECL

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is sent to the driver to notify the driver of the deletion of a vertex shader declaration and to give the driver an opportunity to clean up any driver side resources associated with the given vertex shader declaration. Note that this uses the same structure (D3DHAL_DP2VERTEXSHADER) as D3DDP2OP_DELETEVERTEXSHADER and D3DDP2OP_SETVERTEXSHADERDECL.

</dl>
</dd>

### -field D3DDP2OP_SETVERTEXSHADERDECL

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is passed to the driver to set the current vertex shader declaration. All subsequent drawing operations should use the given shader declaration until another is selected. Note that this uses the same structure (D3DHAL_DP2VERTEXSHADER) as D3DDP2OP_SETVERTEXSHADER and D3DDP2OP_DELETEVERTEXSHADERDECL.

</dl>
</dd>

### -field D3DDP2OP_CREATEVERTEXSHADERFUNC

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is sent to the driver when a vertex shader function is created. This token gives the driver the opportunity to convert the vertex shader code into a hardware specific format and associate this information with the given shader handle. See D3DHAL_DP2CREATEVERTEXSHADERFUNC.

</dl>
</dd>

### -field D3DDP2OP_DELETEVERTEXSHADERFUNC

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is sent to the driver to notify the driver of the deletion of a vertex shader function and to give the driver an opportunity to clean up any driver side resources associated with the given vertex shader function. Note that this uses the same structure (D3DHAL_DP2VERTEXSHADER) as D3DDP2OP_DELETEVERTEXSHADER and D3DDP2OP_SETVERTEXSHADERFUNC.

</dl>
</dd>

### -field D3DDP2OP_SETVERTEXSHADERFUNC

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is passed to the driver to set the current vertex shader function. All subsequent drawing operations should use the given shader function until another is selected. Note that this uses the same structure (D3DHAL_DP2VERTEXSHADER) as D3DDP2OP_SETVERTEXSHADER and D3DDP2OP_DELETEVERTEXSHADERFUNC.

</dl>
</dd>

### -field D3DDP2OP_SETVERTEXSHADERCONSTI

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is passed to the driver to set one or more vertex shader constant registers with integer values. The constant registers are specified by a D3DHAL_DP2SETVERTEXSHADERCONST structure. One or more vectors of four integer values immediately follow the D3DHAL_DP2SETVERTEXSHADERCONST data structure in the DP2 stream. 

</dl>
</dd>

### -field D3DDP2OP_SETSCISSORRECT

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Specifies to mark a portion of a 2D resource such as a 2D texture or cube texture. This 2D texture is specified by a D3DHAL_DP2SETSCISSORRECT structure, which is defined as a RECT structure. For more information about RECT, see the DirectX SDK documentation.

</dl>
</dd>

### -field D3DDP2OP_SETSTREAMSOURCE2

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Binds a portion of a vertex stream source to a vertex buffer. See D3DHAL_DP2SETSTREAMSOURCE2.

</dl>
</dd>

### -field D3DDP2OP_BLT

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Specifies a blt operation from a source surface to a destination surface. It is specified by one or more D3DHAL_DP2BLT structures.

</dl>
</dd>

### -field D3DDP2OP_COLORFILL

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Specifies a color-fill operation. See D3DHAL_DP2COLORFILL.

</dl>
</dd>

### -field D3DDP2OP_SETVERTEXSHADERCONSTB

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is passed to the driver to set one or more vertex shader constant registers with Boolean values. The constant registers are specified by a D3DHAL_DP2SETVERTEXSHADERCONST structure. An array of one or more Boolean values immediately follow the D3DHAL_DP2SETVERTEXSHADERCONST data structure in the DP2 stream. 

</dl>
</dd>

### -field D3DDP2OP_CREATEQUERY

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is sent to the driver to create driver-side resources for queries that the runtime subsequently issues for processing. The queries are specified by one or more D3DHAL_DP2CREATEQUERY structures. Before the runtime can request to create queries, the runtime must first send D3DGDI2_TYPE_GETD3DQUERYCOUNT and D3DGDI2_TYPE_GETD3DQUERYGetDriverInfo2 requests to determine if the driver supports any query types. For more information about GetDriverInfo2, see Supporting GetDriverInfo2.

</dl>
</dd>

### -field D3DDP2OP_SETRENDERTARGET2

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Sets a portion of the render target. See D3DHAL_DP2SETRENDERTARGET2.

</dl>
</dd>

### -field D3DDP2OP_SETDEPTHSTENCIL

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Sets a new depth buffer in the driver's current context. See the D3DHAL_DP2SETDEPTHSTENCIL structure.

</dl>
</dd>

### -field D3DDP2OP_RESPONSECONTINUE

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is returned by the driver in a response buffer and indicates that the driver was unable to write all the responses in the command buffer that the runtime supplied because the size of the buffer was too small. The driver writes as many responses as possible and uses the D3DDP2OP_RESPONSEQUERY token to indicate the presence of these responses. As a result of the D3DDP2OP_RESPONSECONTINUE token, the runtime subsequently resubmits an empty command buffer so that the driver can continue to write more responses.

</dl>
</dd>

### -field D3DDP2OP_RESPONSEQUERY

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is returned by the driver in a response buffer and indicates the presence of query data in the response buffer. The driver specifies one or more D3DHAL_DP2RESPONSEQUERY structures that identify previously issued queries and specify the size of the data related to the queries. Each D3DHAL_DP2RESPONSEQUERY is followed by its query data. 

</dl>
</dd>

### -field D3DDP2OP_GENERATEMIPSUBLEVELS

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Notifies the driver to automatically regenerate the sublevels of a mipmap texture using a specific filter type. This notification is specified with a D3DHAL_DP2GENERATEMIPSUBLEVELS structure. The driver receives this notification after performing some other operation that only accesses the top level of the mipmap texture. For example, a blit operation.

</dl>
</dd>

### -field D3DDP2OP_DELETEQUERY

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is sent to the driver to notify the driver of the deletion of queries and to give the driver an opportunity to clean up any driver-side resources associated with those queries. This notification is specified by one or more D3DHAL_DP2DELETEQUERY structures. 

</dl>
</dd>

### -field D3DDP2OP_ISSUEQUERY

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token requests that the driver process previously created queries. This request is specified by one or more D3DHAL_DP2ISSUEQUERY structures.

</dl>
</dd>

### -field D3DDP2OP_SETPIXELSHADERCONSTI

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is passed to the driver to set one or more pixel shader constant registers with integer values. The constant registers are specified by a D3DHAL_DP2SETPIXELSHADERCONST structure. One or more vectors of four integer values immediately follow the D3DHAL_DP2SETPIXELSHADERCONST data structure in the DP2 stream. 

</dl>
</dd>

### -field D3DDP2OP_SETPIXELSHADERCONSTB

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field This token is passed to the driver to set one or more pixel shader constant registers with Boolean values. The constant registers are specified by a D3DHAL_DP2SETPIXELSHADERCONST structure. An array of one or more Boolean values immediately follow the D3DHAL_DP2SETPIXELSHADERCONST data structure in the DP2 stream. 

</dl>
</dd>

### -field D3DDP2OP_SETSTREAMSOURCEFREQ

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Sets the frequency divisor of a stream source that is bound to a vertex buffer. See D3DHAL_DP2SETSTREAMSOURCEFREQ.

</dl>
</dd>

### -field D3DDP2OP_SURFACEBLT

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Specifies a blt operation from a source system memory surface to a destination video memory surface. It is specified by one or more D3DHAL_DP2SURFACEBLT structures.

</dl>
</dd>

### -field D3DDP2OP_SETCONVOLUTIONKERNELMONO

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Defines the resolution and weights of the kernel filter. See the D3DHAL_DP2SETCONVOLUTIONKERNELMONO structure.

</dl>
</dd>

### -field D3DDP2OP_COMPOSERECTS

<dd>
<dl>

### -field 
      DirectX 9.0 and later versions only.
      


### -field Composes two-dimensional areas from a source surface to a destination surface. See the D3DHAL_DP2COMPOSERECTS structure.

</dl>
</dd>
</dl>

## -remarks
<p>Note that because the D3DNTDP2OP_<i>XXX</i> enumerators are type defined as D3DDP2OP_<i>XXX</i> internally in the <i>Dx95type.h</i> file of the Windows Driver Kit (WDK), the shorter form is used here for clarity. Either form is valid on Windows 2000 and later implementations, but only the shorter form can be used on Windows 98/Me.</p>

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