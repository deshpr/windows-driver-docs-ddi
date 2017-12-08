---
UID: NF.prcomoem.IPrintOemUni.TextOutAsBitmap
title: IPrintOemUni::TextOutAsBitmap
author: windows-driver-content
description: The IPrintOemUni::TextOutAsBitmap method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.
old-location: print\iprintoemuni_textoutasbitmap.htm
old-project: print
ms.assetid: 2c144eb7-6279-490a-813c-6c0ae995c6ad
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintOemUni, TextOutAsBitmap, IPrintOemUni::TextOutAsBitmap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemUni.TextOutAsBitmap
req.alt-loc: prcomoem.h
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
req.iface: IPrintOemUni
req.product: Windows 10 or later.
---

# IPrintOemUni::TextOutAsBitmap method



## -description
<p>The <code>IPrintOemUni::TextOutAsBitmap</code> method allows a rendering plug-in to create a bitmap image of a text string, in case a downloadable font is not available.</p>


## -syntax

````
HRESULT TextOutAsBitmap(
   SURFOBJ  *pso,
   STROBJ   *pstro,
   FONTOBJ  *pfo,
   CLIPOBJ  *pco,
   RECTL    *prclExtra,
   RECTL    *prclOpaque,
   BRUSHOBJ *pboFore,
   BRUSHOBJ *pboOpaque,
   POINTL   *pptlOrg,
   MIX      mix
);
````


## -parameters
<dl>

### -param pso 

<dd>
<p>Pointer to a <a href="display.surfobj">SURFOBJ</a> structure that describes the surface on which to write. </p>
</dd>

### -param pstro 

<dd>
<p>Pointer to a <a href="display.strobj">STROBJ</a> structure that defines the glyphs to be rendered and the positions in which to place them. </p>
</dd>

### -param pfo 

<dd>
<p>Pointer to a <a href="display.fontobj">FONTOBJ</a> structure from which to retrieve information about the font and its glyphs. </p>
</dd>

### -param pco 

<dd>
<p>Pointer to a <a href="display.clipobj">CLIPOBJ</a> structure that defines the clip region through which all rendering must be done. The driver cannot affect any pixels outside the clip region. </p>
</dd>

### -param prclExtra 

<dd>
<p>Pointer to a RECTL structure. GDI always sets this parameter to <b>NULL</b> in calls to this function. It should be ignored by the driver. </p>
</dd>

### -param prclOpaque 

<dd>
<p>Pointer to a <a href="display.rectl">RECTL</a> structure that represents a single opaque rectangle. This rectangle is bottom-right exclusive. Pixels within this rectangle (those that are not foreground and not clipped) are to be rendered with the opaque brush. This rectangle always bounds the text to be drawn. If this parameter is <b>NULL</b>, no opaque pixels are to be rendered. </p>
</dd>

### -param pboFore 

<dd>
<p>Pointer to a <a href="display.brushobj">BRUSHOBJ</a> structure that represents the brush object to be used for the foreground pixels. This brush will always be a solid color brush.</p>
</dd>

### -param pboOpaque 

<dd>
<p>Pointer to a BRUSHOBJ structure that represents the opaque pixels. Both the foreground and background mix modes for this brush are assumed to be R2_COPYPEN. Unless the driver sets the GCAPS_ARBRUSHOPAQUE capabilities bit in the <i>flGraphicsCaps</i> member of the DEVINFO structure, it will always be called with a solid color brush. </p>
</dd>

### -param pptlOrg 

<dd>
<p>Pointer to a <a href="display.pointl">POINTL</a> structure that defines the brush origin for both brushes.</p>
</dd>

### -param mix 

<dd>
<p>The foreground and background raster operations (mix modes) for <i>pboFore</i>. </p>
</dd>
</dl>

## -returns
<p>The method must return one of the following values.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The operation succeeded.</p><dl>
<dt><b>E_FAIL</b></dt>
</dl><p>The operation failed.</p><dl>
<dt><b>E_NOTIMPL</b></dt>
</dl><p>The method is not implemented.</p>

<p> </p>

## -remarks
<p>The <code>IPrintOemUni::TextOutAsBitmap</code> method is called from Unidrv's <a href="print.iprintoemdriveruni_drvunitextout">IPrintOemDriverUni::DrvUniTextOut</a> method, if that method cannot create the text string using downloadable fonts, either because the font is not available or is rotated. <code>IPrintOemUni::TextOutAsBitmap</code> should create a bitmap image of the text and send it to the print device.</p>

<p>The <code>IPrintOemUni::TextOutAsBitmap</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="print.iprintoemuni_getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "TextOutAsBitmap" as input.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintoemdriveruni_drvunitextout">IPrintOemDriverUni::DrvUniTextOut</a>
</dt>
<dt>
<a href="print.iprintoemuni_getimplementedmethod">IPrintOemUni::GetImplementedMethod</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::TextOutAsBitmap method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>