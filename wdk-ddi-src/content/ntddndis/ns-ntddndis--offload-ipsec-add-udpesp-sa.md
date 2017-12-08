---
UID: NS.ntddndis._OFFLOAD_IPSEC_ADD_UDPESP_SA
title: OFFLOAD_IPSEC_ADD_UDPESP_SA
author: windows-driver-content
description: The OFFLOAD_IPSEC_ADD_UDPESP_SA structure contains information for each security association (SA) that a miniport driver adds for UDP-encapsulated ESP packets to a NIC.
old-location: netvista\offload_ipsec_add_udpesp_sa.htm
old-project: netvista
ms.assetid: 4d3f554f-2733-4896-827c-14e92e8034ce
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: OFFLOAD_IPSEC_ADD_UDPESP_SA, OFFLOAD_IPSEC_ADD_UDPESP_SA, *POFFLOAD_IPSEC_ADD_UDPESP_SA
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
req.alt-api: OFFLOAD_IPSEC_ADD_UDPESP_SA
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

# OFFLOAD_IPSEC_ADD_UDPESP_SA structure



## -description
<p>The OFFLOAD_IPSEC_ADD_UDPESP_SA structure contains information for each security association (SA)
  that a miniport driver adds for UDP-encapsulated ESP packets to a NIC.</p>


## -syntax

````
typedef struct _OFFLOAD_IPSEC_ADD_UDPESP_SA {
  IPAddr                               SrcAddr;
  IPMask                               SrcMask;
  IPAddr                               DstAddr;
  IPMask                               DstMask;
  ULONG                                Protocol;
  USHORT                               SrcPort;
  USHORT                               DstPort;
  IPAddr                               SrcTunnelAddr;
  IPAddr                               DstTunnelAddr;
  USHORT                               Flags;
  SHORT                                NumSAs;
  OFFLOAD_SECURITY_ASSOCIATION         SecAssoc[OFFLOAD_MAX_SAS];
  HANDLE                               OffloadHandle;
  OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY EncapTypeEntry;
  HANDLE                               EncapTypeEntryOffldHandle;
  ULONG                                KeyLen;
  UCHAR                                KeyMat[1];
} OFFLOAD_IPSEC_ADD_UDPESP_SA, *POFFLOAD_IPSEC_ADD_UDPESP_SA;
````


## -struct-fields
<dl>

### -field SrcAddr

<dd>
<p>The IP address of the source host (the host sending the packets).</p>
</dd>

### -field SrcMask

<dd>
<p>The subnet mask for the source IP address.</p>
</dd>

### -field DstAddr

<dd>
<p>The IP address of the destination host (the host receiving the packets).</p>
</dd>

### -field DstMask

<dd>
<p>The subnet mask for the destination IP address.</p>
</dd>

### -field Protocol

<dd>
<p>The IP protocol. The encoding of 
     <b>Protocol</b> is identical to that of the Protocol field in an IP header. The
     value should be 11 (hexadecimal), which specifies UDP.</p>
</dd>

### -field SrcPort

<dd>
<p>A source TCP or UDP port. If 
     <b>SrcPort</b> is set to zero, the SA applies to any source TCP/UDP port.</p>
</dd>

### -field DstPort

<dd>
<p>A destination TCP or UDP port. If DestPort is set to zero, the SA applies to any source TCP/UDP
     port.</p>
</dd>

### -field SrcTunnelAddr

<dd>
<p>The IP address for the source endpoint, such as a connector, of a tunnel. The miniport driver uses
     
     <b>SrcTunnelAddr</b> as the source address for the tunnel IP header of packets
     sent on the SA. 
     <b>SrcTunnelAddr</b> is specified only for an SA that applies to the tunnel
     portion of a packet. 
     <b>SrcTunnelAddr</b> is set to zero for an SA that applies to the transport
     portion of a packet.</p>
</dd>

### -field DstTunnelAddr

<dd>
<p>The IP address for the destination endpoint, such as a connector, of a tunnel. The miniport driver
     uses 
     <b>DestTunnelAddr</b> as the destination address for the tunnel IP header of
     packets sent on the SA. 
     <b>DestTunnelAddr</b> is specified only for an SA that applies to the tunnel
     portion of a packet. 
     <b>DestTunnelAddr</b> is set to zero for an SA that applies to the transport
     portion of a packet.</p>
</dd>

### -field Flags

<dd>
<p>A bitmask that indicates whether the SA that is being added is an inbound or outbound SA as
     follows:
     </p>
<p></p>
<dl>

### -field OFFLOAD_INBOUND_SA

<dd>
<p>Specifies an inbound SA.</p>
</dd>

### -field OFFLOAD_OUTBOUND_SA

<dd>
<p>Specifies an outbound SA.</p>
</dd>
</dl>
</dd>

### -field NumSAs

<dd>
<p>The number of elements in the 
     <b>SecAssoc</b> array. Each element in the array is an 
     <a href="..\ntddndis\ns-ntddndis--offload-security-association.md">
     OFFLOAD_SECURITY_ASSOCIATION</a> structure.</p>
</dd>

### -field SecAssoc

<dd>
<p>A variable-length array that contains the information about the Internet Protocol security (IPsec)
     operations (AH or ESP) for the SA. The information for each IPsec operations is formatted as an
     OFFLOAD_SECURITY_ASSOCIATION structure.
     </p>
<p>The TCP/IP transport specifies one or two OFFLOAD_SECURITY_ASSOCIATION structures in the buffer at 
     <b>SecAssoc</b>. Each OFFLOAD_SECURITY_ASSOCIATION structure indicates the type
     of operation--authentication or encryption/decryption--for which the SA specified in the structure is to
     be used. The order of the OFFLOAD_SECURITY_ASSOCIATION structures in the array indicates the order in
     which the miniport driver should perform the operations for each SA. Only one combination of operations
     is supported: encryption/decryption (ESP) followed by authentication (AH).</p>
</dd>

### -field OffloadHandle

<dd>
<p>The handle to the newly created SA. The miniport driver supplies this handle before completing the
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> request.
     The TCP/IP transport must specify this handle in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557028">NDIS_IPSEC_PACKET_INFO</a> structure before
     passing a send packet to the miniport driver. The TCP/IP transport must also specify this handle when
     deleting the SA with an 
     <a href="netvista.oid_tcp_task_ipsec_delete_sa">
     OID_TCP_TASK_IPSEC_DELETE_SA</a> request.</p>
</dd>

### -field EncapTypeEntry

<dd>
<p>The UDP-ESP encapsulation type and destination port of a parser entry. This information is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis--offload-ipsec-udpesp-encaptype-entry.md">
     OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY</a> structure.</p>
</dd>

### -field EncapTypeEntryOffldHandle

<dd>
<p>When 
     <b>Flags</b>= 
     <b>OFFLOAD_INBOUND_SA</b> and 
     <b>EncapTypeEntryOffldHandle</b> is <b>NULL</b>, the miniport driver should check
     whether the parser entry specified by 
     <b>EncapTypeEntry</b> is in the NIC's parser entry list. If it is not, the
     miniport driver should create a parser entry, using the encapsulation type and destination port
     specified in 
     <b>EncapTypeEntry</b>, add the parser entry to the parser entry list, and
     offload the specified SAs. The miniport driver should return a handle in 
     <b>EncapTypeEntryOffldHandle</b> that identifies the newly created parser entry.
     If the specified parser entry is already in the parser entry list, the miniport should simply return the
     handle in 
     <b>EncapTypeEntryOffldHandle</b> for the existing parser entry.
     </p>
<p>When 
     <b>Flags</b>= 
     <b>OFFLOAD_INBOUND_SA</b> and 
     <b>EncapTypeEntryOffldHandle</b> is non-<b>NULL</b>, 
     <b>EncapTypeEntryOffldHandle</b> contains the handle to a parser entry that
     already is in the NIC's parser entry list. In this case, the miniport driver should simply offload the
     specified SAs.</p>
<p>When 
     <b>Flags</b>= 
     <b>OFFLOAD_OUTBOUND_SA</b>, the miniport driver should ignore the 
     <b>EncapTypeEntryOffldHandle</b> parameter.</p>
</dd>

### -field KeyLen

<dd>
<p>The length, in bytes, of the buffer at 
     <b>KeyMat</b>.</p>
</dd>

### -field KeyMat

<dd>
<p>A variable-length array that contains keys for the SAs specified at 
     <b>SecAssoc</b>. If both a confidentiality (encryption/decryption) algorithm and
     an integrity (authentication) algorithm are specified by the 
     <b>ConfAlgo</b> and 
     <b>IntegrityAlgo</b> of an 
     <a href="..\ntddndis\ns-ntddndis--offload-security-association.md">
     OFFLOAD_SECURITY_ASSOCIATION</a> structure, the buffer at 
     <b>KeyMat</b> contains key information for the confirmation algorithm first,
     followed immediately by key information for the integrity algorithm.
     </p>
<p>The length of each key in the buffer at 
     <b>KeyMat</b> is specified by 
     <b>algoKeyLen</b> in the 
     <a href="..\ntddndis\ns-ntddndis--offload-algo-info.md">OFFLOAD_ALGO_INFO</a> structure that
     specifies the confidentiality or integrity algorithm. (An OFFLOAD_ALGO_INFO structure is a member of an
     OFFLOAD_SECURITY_ASSOCIATION structure.)</p>
</dd>
</dl>

## -remarks
<p>The OFFLOAD_IPSEC_ADD_UDPESP_SA structure is used with the 
    <a href="netvista.oid_tcp_task_ipsec_add_udpesp_sa">
    OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a> OID.</p>

<p>Note that the OFFLOAD_IPSEC_ADD_UDPESP_SA structure is almost identical to the 
    <a href="..\ntddndis\ns-ntddndis--offload-ipsec-add-sa.md">OFFLOAD_IPSEC_ADD_SA</a> structure used in
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> request.
    The only difference is that the OFFLOAD_IPSEC_ADD_UDPESP_SA structure contains the 
    <b>EncapTypeEntry</b> and the 
    <b>EncapTypeEntryOffldHandle</b> members.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557028">NDIS_IPSEC_PACKET_INFO</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--offload-algo-info.md">OFFLOAD_ALGO_INFO</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--offload-ipsec-add-sa.md">OFFLOAD_IPSEC_ADD_SA</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--offload-ipsec-udpesp-encaptype-entry.md">
   OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--offload-security-association.md">OFFLOAD_SECURITY_ASSOCIATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a>
</dt>
<dt>
<a href="netvista.oid_tcp_task_ipsec_add_udpesp_sa">
   OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569810">OID_TCP_TASK_IPSEC_DELETE_SA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_IPSEC_ADD_UDPESP_SA structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>