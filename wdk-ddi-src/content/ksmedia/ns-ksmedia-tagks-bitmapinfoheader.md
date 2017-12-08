---
UID: NS.ksmedia.tagKS_BITMAPINFOHEADER
title: tagKS_BITMAPINFOHEADER
author: windows-driver-content
description: The KS_BITMAPINFOHEADER structure describes details about the video stream, such as image dimensions and pixel depth.
old-location: stream\ks_bitmapinfoheader.htm
old-project: stream
ms.assetid: 77101494-97bb-4049-8c6c-cdb4ee82f312
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: tagKS_BITMAPINFOHEADER, KS_BITMAPINFOHEADER, *PKS_BITMAPINFOHEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_BITMAPINFOHEADER
req.alt-loc: ksmedia.h
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

# tagKS_BITMAPINFOHEADER structure



## -description
<p>The KS_BITMAPINFOHEADER structure describes details about the video stream, such as image dimensions and pixel depth. </p>


## -syntax

````
typedef struct tagKS_BITMAPINFOHEADER {
  DWORD biSize;
  LONG  biWidth;
  LONG  biHeight;
  WORD  biPlanes;
  WORD  biBitCount;
  DWORD biCompression;
  DWORD biSizeImage;
  LONG  biXPelsPerMeter;
  LONG  biYPelsPerMeter;
  DWORD biClrUsed;
  DWORD biClrImportant;
} KS_BITMAPINFOHEADER, *PKS_BITMAPINFOHEADER;
````


## -struct-fields
<dl>

### -field biSize

<dd>
<p>Specifies the size of the structure in bytes.</p>
</dd>

### -field biWidth

<dd>
<p>Specifies the width of the bitmap in pixels.</p>
</dd>

### -field biHeight

<dd>
<p>Specifies the height of the bitmap in pixels.</p>
</dd>

### -field biPlanes

<dd>
<p>Specifies the number of planes. This is always set to 1.</p>
</dd>

### -field biBitCount

<dd>
<p>Specifies the color bits per pixel. For example, 1, 4, 8, or 24.</p>
</dd>

### -field biCompression

<dd>
<p>Specifies the compression scheme.</p>
</dd>

### -field biSizeImage

<dd>
<p>Specifies the size of bitmap bits in bytes. (Only required if using compression.)</p>
</dd>

### -field biXPelsPerMeter

<dd>
<p>Specifies the horizontal resolution in pixels per meter.</p>
</dd>

### -field biYPelsPerMeter

<dd>
<p>Specifies the vertical resolution in pixels per meter.</p>
</dd>

### -field biClrUsed

<dd>
<p>Specifies the number of colors used in the image.</p>
</dd>

### -field biClrImportant

<dd>
<p>Specifies the number of important colors in the image.</p>
</dd>
</dl>

## -remarks
<p>This is the same structure as the user-mode GDI bitmap header (BITMAPINFOHEADER) structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>