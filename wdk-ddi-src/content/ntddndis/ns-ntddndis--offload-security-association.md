---
UID: NS.ntddndis._OFFLOAD_SECURITY_ASSOCIATION
title: OFFLOAD_SECURITY_ASSOCIATION
author: windows-driver-content
description: The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).
old-location: netvista\offload_security_association.htm
old-project: netvista
ms.assetid: 2c392a13-4db4-4b22-aacf-4450eb1e191c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: OFFLOAD_SECURITY_ASSOCIATION,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OFFLOAD_SECURITY_ASSOCIATION
req.alt-loc: ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# OFFLOAD_SECURITY_ASSOCIATION structure



## -description
<p>The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).</p>


## -syntax

````
typedef struct _OFFLOAD_SECURITY_ASSOCIATION {
  OFFLOAD_OPERATION_E Operation;
  SPI_TYPE            SPI;
  OFFLOAD_ALGO_INFO   IntegrityAlgo;
  OFFLOAD_ALGO_INFO   ConfAlgo;
  OFFLOAD_ALGO_INFO   Reserved;
} OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION;
````


## -struct-fields
<dl>

### -field Operation

<dd>
<p>The Internet Protocol security (IPsec) operation for which the SA is to be used. The following
     operations are supported:
     </p>
<p></p>
<dl>

### -field AUTHENTICATE

<dd>
<p>The SA will be used for authentication (integrity checking).</p>
</dd>

### -field ENCRYPT

<dd>
<p>The SA will be used for encryption/decryption (confidentiality).</p>
</dd>
</dl>
</dd>

### -field SPI

<dd>
<p>The Security Parameters Index (SPI) for the SA.</p>
</dd>

### -field IntegrityAlgo

<dd>
<p>The integrity (authentication) algorithm for the SA, formatted as an 
     <a href="..\ntddndis\ns-ntddndis--offload-algo-info.md">OFFLOAD_ALGO_INFO</a> structure.</p>
</dd>

### -field ConfAlgo

<dd>
<p>The confidentiality (encryption/decryption) algorithm for the SA, formatted as an
     OFFLOAD_ALGO_INFO structure.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved.</p>
</dd>
</dl>

## -remarks
<p>The OFFLOAD_SECURITY_ASSOCIATION structure is used with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> and 
    <a href="netvista.oid_tcp_task_ipsec_add_udpesp_sa">
    OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a> OIDs.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis--offload-algo-info.md">OFFLOAD_ALGO_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a>
</dt>
<dt>
<a href="netvista.oid_tcp_task_ipsec_add_udpesp_sa">
   OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_SECURITY_ASSOCIATION structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>