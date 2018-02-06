---
UID: NF:prcomoem.IPrintOemUni.Compression
title: IPrintOemUni::Compression method
author: windows-driver-content
description: The IPrintOemUni::Compression method can be used with Unidrv-supported printers to provide a customized bitmap compression method.
old-location: print\iprintoemuni_compression.htm
old-project: print
ms.assetid: 02524493-3842-462e-86f6-2ab35998c65e
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintoemuni_compression, IPrintOemUni, Compression method [Print Devices], IPrintOemUni interface, IPrintOemUni interface [Print Devices], Compression method, Compression, prcomoem/IPrintOemUni::Compression, IPrintOemUni::Compression, print_unidrv-pscript_rendering_47704483-1ab7-46a6-8a1e-07559fc6bde2.xml, Compression method [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemUni.Compression
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintOemUni::Compression method


## -description


The <code>IPrintOemUni::Compression</code> method can be used with Unidrv-supported printers to provide a customized bitmap compression method.


## -syntax


````
HRESULT Compression(
        PDEVOBJ pdevobj,
        PBYTE   pInBuf,
        PBYTE   pOutBuf,
        DWORD   dwInLen,
        DWORD   dwOutLen,
  [out] INT     *piResult
);
````


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pInBuf

Caller-supplied pointer to input scan line data.


### -param pOutBuf

Caller-supplied pointer to an output buffer to receive compressed scan line data.


### -param dwInLen

Caller-supplied length of the input data.


### -param dwOutLen

Caller-supplied length of the output buffer.


### -param piResult [out]

Receives a method-supplied result value. If the operation succeeds, this value should be the number of compressed bytes, which must not be larger than the value received for <i>dwOutLen</i>. If an error occurs, or if the method cannot compress, the result value should be -1.


## -returns


The method must return one of the following values.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table> 



## -remarks


The <code>IPrintOemUni::Compression</code> method is used by rendering plug-ins to compress scan line data before it is sent to the print spooler. The method's purpose is to provide support for printer-specific compression methods that are not supported by Unidrv.

If the <code>IPrintOemUni::Compression</code> method is defined, and if the printer's <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GPD</a> file contains a CmdEnableOEMComp command entry, Unidrv calls the method each time a scan line is ready to be sent to the print spooler. (For information about the CmdEnableOEMComp command, see <a href="https://msdn.microsoft.com/fd88d009-7612-49cc-810a-b0d09b4b75b3">Raster Data Compression Commands</a>.)

The <i>pInBuf</i> and <i>dwInLen</i> parameter values describe a buffer containing a scan line of image data to be compressed. The <i>pOutBuf</i> and <i>dwOutLen</i> parameter values describe the buffer into which the <code>IPrintOemUni::Compression</code> method should place the compressed data.

Before Unidrv sends a scan line to the print spooler, it tries every enabled compression method to determine which one creates the smallest data stream. After it determines the best compression algorithm (by compressing the data using each method), it spools the printer command that enables the printer to accept the best compressed format, then sends the compressed data to the printer.

Therefore, the <code>IPrintOemUni::Compression</code> method is called for every scan line, whether the compressed data returned by the method is actually used or not. When the method is called, <i>dwOutLen</i> contains the length returned by the best compression method Unidrv has tried up to then. (If no other methods have been tried, <i>dwOutLen</i> contains the uncompressed length.) If the algorithm cannot produce a compressed scan line that is equal to or shorter than <i>dwOutLen</i> bytes, it should return -1 in the location specified by <i>piResult</i>.

If, after Unidrv tries all enabled compression methods, the compressed data returned by <code>IPrintOemUni::Compression</code> has the smallest length, Unidrv sends the buffer to the print spooler, preceded by the command specified by the CmdEnableOEMComp command entry.

If possible, the method's compression algorithm should use the received <i>dwOutLen</i> value to determine whether it can stop the algorithm before completion, to save time if another compression method has already created a better result.

The <code>IPrintOemUni::Compression</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "Compression" as input.

