---
UID: NS.scsi._SES_CONFIGURATION_DIAGNOSTIC_PAGE
title: SES_CONFIGURATION_DIAGNOSTIC_PAGE
author: windows-driver-content
description: TBD.
old-location: storage\ses_configuration_diagnostic_page.htm
old-project: storage
ms.assetid: 0FD748D6-F598-44D1-A8D3-E63764CB90C6
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SES_CONFIGURATION_DIAGNOSTIC_PAGE, SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SES_CONFIGURATION_DIAGNOSTIC_PAGE
req.alt-loc: scsi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# SES_CONFIGURATION_DIAGNOSTIC_PAGE structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>TBD</p>


## -syntax

````
typedef struct _SES_CONFIGURATION_DIAGNOSTIC_PAGE {
  UCHAR                    PageCode;
  UCHAR                    NumberOfSecondarySubEnclosures;
  UCHAR                    PageLength[2];
  UCHAR                    GenerationCode[4];
  SES_ENCLOSURE_DESCRIPTOR Descriptors[ANYSIZE_ARRAY];
} SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE;
````


## -struct-fields
<dl>

### -field PageCode

<dd>
<p>Specifies the diagnostic page being sent or requested based on the value. For a Microcode Control diagnostic page, the value should be 0x01.</p>
</dd>

### -field NumberOfSecondarySubEnclosures

<dd>
<p>Specifies the number of separate subenclosures included in
the enclosure descriptor list, not including the primary subenclosure. If this is set to zero, only the primary subenclosure exists.</p>
</dd>

### -field PageLength

<dd>
<p>Specifies the length of the diagnostic page, in bytes.</p>
</dd>

### -field GenerationCode

<dd>
<p>Specifies the value of the generation code.</p>
</dd>

### -field Descriptors

<dd>
<p>Specifies the enclosure descriptors for the primary and secondary enclosures. The primary enclosure is the first index.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 10, version 1709 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Scsi.h (include Minitape.h or Storport.h)</dt>
</dl>
</td>
</tr>
</table>