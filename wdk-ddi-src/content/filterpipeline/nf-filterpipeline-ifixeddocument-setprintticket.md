---
UID: NF.filterpipeline.IFixedDocument.SetPrintTicket
title: IFixedDocument::SetPrintTicket
author: windows-driver-content
description: The SetPrintTicket method inserts a print ticket into the fixed document.
old-location: print\ifixeddocument_setprintticket.htm
old-project: print
ms.assetid: 701c53d5-bb1e-4003-9505-19b9c46689c6
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IFixedDocument, SetPrintTicket, IFixedDocument::SetPrintTicket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IFixedDocument.SetPrintTicket
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: IFixedDocument
---

# IFixedDocument::SetPrintTicket method



## -description
<p>The <b>SetPrintTicket</b> method inserts a print ticket into the fixed document.</p>


## -syntax

````
HRESULT SetPrintTicket(
  [in] IPartPrintTicket *pPrintTicket
);
````


## -parameters
<dl>

### -param pPrintTicket [in]

<dd>
<p>A pointer to the print ticket to be inserted.</p>
</dd>
</dl>

## -returns
<p><b>SetPrintTicket</b> returns an <b>HRESULT</b> value.</p>

## -remarks


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
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IDL</p>
</th>
<td width="70%">
<dl>
<dt>Filterpipeline.idl</dt>
</dl>
</td>
</tr>
</table>