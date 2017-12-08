---
UID: NF.prcomoem.IPrintCorePS2.DrvWriteSpoolBuf
title: IPrintCorePS2::DrvWriteSpoolBuf
author: windows-driver-content
description: The IPrintCorePS2::DrvWriteSpoolBuf method is provided by the Pscript5 driver so that a rendering plug-in can send printer data to the spooler.
old-location: print\iprintcoreps2_drvwritespoolbuf.htm
old-project: print
ms.assetid: 25405dd8-730e-4de6-af44-9dd584ed3087
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintCorePS2, DrvWriteSpoolBuf, IPrintCorePS2::DrvWriteSpoolBuf
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
req.alt-api: IPrintCorePS2.DrvWriteSpoolBuf
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
req.iface: IPrintCorePS2
req.product: Windows 10 or later.
---

# IPrintCorePS2::DrvWriteSpoolBuf method



## -description
<p>The <code>IPrintCorePS2::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can send printer data to the spooler.</p>


## -syntax

````
HRESULT DrvWriteSpoolBuf(
  [in]  PDEVOBJ pdevobj ,
  [in]  PVOID   pBuffer ,
  [in]  DWORD   cbSize ,
  [out] DWORD   *pdwResult 
);
````


## -parameters
<dl>

### -param pdevobj  [in]

<dd>
<p>Caller-supplied pointer to a <a href="..\printoem\ns-printoem--devobj.md">DEVOBJ</a> structure.</p>
</dd>

### -param pBuffer  [in]

<dd>
<p>Caller-supplied pointer to a buffer containing data to be sent to the print spooler.</p>
</dd>

### -param cbSize  [in]

<dd>
<p>Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pBuffer</i>. </p>
</dd>

### -param pdwResult  [out]

<dd>
<p>Receives a method-supplied value representing the number of bytes sent to the spooler.</p>
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
<p>This method has the same behavior as <a href="print.iprintoemdriverps_drvwritespoolbuf">IPrintOemDriverPS::DrvWriteSpoolBuf</a>. This method is supported for any Pscript5 render plug-ins.</p>

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
<a href="print.iprintoemdriverps_drvwritespoolbuf">IPrintOemDriverPS::DrvWriteSpoolBuf</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCorePS2::DrvWriteSpoolBuf method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>