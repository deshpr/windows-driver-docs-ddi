---
UID: NE.d3dumddi._D3DDDI_CERTIFICATETYPE
title: D3DDDI_CERTIFICATETYPE
author: windows-driver-content
description: The D3DDDI_CERTIFICATETYPE enumeration contains values that identify certificate types.
old-location: display\d3dddi_certificatetype.htm
old-project: display
ms.assetid: 0e3835af-0ccf-4f41-96e3-beff5fdecd36
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_CERTIFICATETYPE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_CERTIFICATETYPE
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

# D3DDDI_CERTIFICATETYPE enumeration



## -description
<p>The D3DDDI_CERTIFICATETYPE enumeration contains values that identify certificate types. </p>


## -syntax

````
typedef enum _D3DDDI_CERTIFICATETYPE { 
  D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL  = 1,
  D3DDDI_CERTTYPE_CRYPTOSESSION          = 2
} D3DDDI_CERTIFICATETYPE;
````


## -enum-fields
<dl>

### -field D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL

<dd>
<p>The value specifies that the certificate type is an authenticated channel. </p>
</dd>

### -field D3DDDI_CERTTYPE_CRYPTOSESSION

<dd>
<p>The value specifies that the certificate type is an encryption session. </p>
</dd>
</dl>

## -remarks
<p>The user-mode display driver receives a D3DDDI_CERTIFICATETYPE-typed value in the <b>CertificateType</b> member of the <a href="..\d3dumddi\ns-d3dumddi--ddicertificateinfo.md">DDICERTIFICATEINFO</a> structure. The <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-getcaps.md">D3DDDIARG_GETCAPS</a> structure points to DDICERTIFICATEINFO when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_GETCERTIFICATE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>D3DDDI_CERTIFICATETYPE is supported beginning with the Windows 7 operating system.</p>
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
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-getcaps.md">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--ddicertificateinfo.md">DDICERTIFICATEINFO</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-getcaps.md">GetCaps</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_CERTIFICATETYPE enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>