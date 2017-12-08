---
UID: NC.ndischimney.NDIS_TCP_OFFLOAD_RECEIVE_INDICATE
title: NDIS_TCP_OFFLOAD_RECEIVE_INDICATE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadReceiveHandler function to indicate that received network data is available for consumption by a client application.
old-location: netvista\ndistcpoffloadreceivehandler.htm
old-project: netvista
ms.assetid: a45dede9-6559-4207-a49f-d9627054433a
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: BINARY_DATA, BINARY_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisTcpOffloadReceiveHandler
req.alt-loc: ndischimney.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.iface: 
---

# NDIS_TCP_OFFLOAD_RECEIVE_INDICATE callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>An offload target calls the 
  <b>NdisTcpOffloadReceiveHandler</b> function to indicate that received network data is available for
  consumption by a client application.</p>


## -prototype

````
NDIS_STATUS NdisTcpOffloadReceiveHandler(
  _In_  NDIS_HANDLE      NdisOffloadHandle,
  _In_  PNET_BUFFER_LIST NetBufferList,
  _In_  NDIS_STATUS      Status,
  _Out_ PULONG           BytesConsumed
);
````


## -parameters
<dl>

### -param NdisOffloadHandle [in]

<dd>
<p>A handle that identifies the offloaded TCP connection on which the indication is being made. When
     the connection was offloaded, this handle was supplied in the 
     <b>NdisOffloadHandle</b> member of the 
     <a href="..\ndischimney\ns-ndischimney--ndis-miniport-offload-block-list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was associated with the connection state.</p>
</dd>

### -param NetBufferList [in]

<dd>
<p>A pointer to a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. Each 
      <b>NET_BUFFER_LIST</b> structure
      describes a list of 
      <a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a> structures. Each 
      <b>NET_BUFFER</b> structure in the list maps to a
      chain of 
      <a href="..\wdm\ns-wdm--mdl.md">memory descriptor lists (MDLs)</a>. The MDLs contain the
      received data. The MDLs are locked so that they remain resident, but they are not mapped into system
      memory.</p>
<p>The 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure
      specified by 
      <i>NetBufferList</i> must be a stand-alone structure and cannot be the first
      structure in a linked list of 
      <b>NET_BUFFER_LIST</b> structures.
      Offload targets can work around this limitation by chaining as many MDLs as necessary to the same 
      <a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a> in an offload receive
      indication.</p>
</dd>

### -param Status [in]

<dd>
<p>The offload target must supply the following status value:
     </p>
<p></p>
<dl>

### -param NDIS_STATUS_SUCCESS

<dd>
<p>This indicates that the host stack can retain ownership of the NET_BUFFER_LIST structures and
       associated structures until it returns these structures to the 
       <a href="..\ndischimney\nc-ndischimney-w-tcp-offload-receive-return-handler.md">
       MiniportTcpOffloadReceiveReturn</a> function of the offload target.</p>
</dd>
</dl>
</dd>

### -param BytesConsumed [out]

<dd>
<p>A pointer to a ULONG-typed variable that receives the number of bytes that were consumed by the
     client application.</p>
</dd>
</dl>

## -returns
<p>The 
     <b>NdisTcpOffloadReceiveHandler</b> function can return one of the following values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The client application consumed all the indicated receive data.</p><dl>
<dt><b>NDIS_STATUS_OFFLOAD_DATA_NOT_ACCEPTED</b></dt>
</dl><p>The client application rejected all the indicated receive data.</p><dl>
<dt><b>NDIS_STATUS_OFFLOAD_DATA_PARTIALLY_ACCEPTED</b></dt>
</dl><p>The client application consumed a subset of the indicated receive data. The amount of data, in
       bytes, that was consumed by the client application is returned in the variable specified by the 
       <i>BytesConsumed</i> parameter.</p>

<p> </p>

## -remarks
<p>Receive buffers are posted to the 
    <a href="..\ndischimney\nc-ndischimney-w-tcp-offload-receive-handler.md">
    MiniportTcpOffloadReceive</a> function of the offload target. If preposted receive requests (buffers
    supplied by the client application) are available for the connection, the offload target should transfer
    the receive data by calling the 
    <a href="..\ndischimney\nc-ndischimney-ndis-tcp-offload-receive-complete.md">
    NdisTcpOffloadReceiveComplete</a> function. For more information, see 
    <a href="netvista.delivery_algorithm">Delivery Algorithm</a>.</p>

<p>All receive requests must be completed by the offload target (even if they are zero-byte receive requests).</p>

<p>After an offload target has indicated receive data and that data has been refused, the offload target
    cannot indicate that data again until the host stack posts a receive request:</p>

<p>Normal receive requests</p>

<p>If the host stack posts normal receive requests, the offload target must complete these requests
      before making any receive indications. For more information see 
      <a href="netvista.delivery_algorithm">Delivery Algorithm</a>.</p>

<p>Zero-byte receive requests</p>

<p>The host stack can post a zero-byte receive request to enable receive indications by the offload
      target. A zero-byte receive request is one in which the value of the 
      <b>DataLength</b> member (for more information, see 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure) is zero. A
      zero-byte receive request does not consume any buffered data.</p>

<p>During initialization, the offload target should allocate two pools of buffers, each of which contains
    NET_BUFFER_LIST structures and NET_BUFFER structures. The offload target uses one pool for making receive
    indications through the TCP chimney when calling the 
    <b>
    NdisTcpOffloadReceiveHandler</b> function. The offload target uses the other pool for making receive
    indications through the nonoffload NDIS interface when calling the 
    <a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
    NdisMIndicateReceiveNetBufferLists</a> function.</p>

<p>Each allocated NET_BUFFER_LIST structure must have only one NET_BUFFER structure associated with it.
    The number of such structures to allocate is up to the driver writer. For more information about
    allocating such structures, see 
    <a href="netvista.miniport_driver_buffer_management">Miniport Driver Buffer
    Management</a>.</p>

<p>Provided that it is not making a delayed acknowledgment, the offload target should acknowledge
    received data as soon as the offload target has internal buffers into which it can deposit the data. The
    offload target can acknowledge received data before, during, or after calling the 
    <b>NdisTcpOffloadReceiveHandler</b> function.</p>

<p>The offload target always supplies a 
    <i>Status</i> value of NDIS_STATUS_SUCCESS when calling the 
    <b>NdisTcpOffloadReceiveHandler</b> function. This indicates that the host stack can retain ownership of
    the NET_BUFFER_LIST structures and associated structures until it returns these structures to the offload
    target.</p>

<p>If the host stack returns NDIS_STATUS_SUCCESS, indicating that the client application accepted and
      consumed the receive data, the host stack will return the NET_BUFFER_LIST structures to the 
      <a href="..\ndischimney\nc-ndischimney-w-tcp-offload-receive-return-handler.md">
      MiniportTcpOffloadReceiveReturn</a> function of the offload target. The host stack will set the
      variable specified by the 
      <i>BytesConsumed</i> parameter to the number of bytes that were indicated by the offload target.</p>

<p>If the host stack returns NDIS_STATUS_NOT_ACCEPTED, indicating that the client application rejected
      the receive data, the offload target resumes ownership of the indicated NET_BUFFER_LIST structures on
      return of the 
      <b>NdisTcpOffloadReceiveHandler</b> function. The offload target must buffer the receive data in
      anticipation that the client application will post receive buffers on the connection. After the client
      application posts receive buffers, the offload target copies the buffered receive data into the posted
      buffers and completes the posted buffers by calling the 
      <a href="..\ndischimney\nc-ndischimney-ndis-tcp-offload-receive-complete.md">
      NdisTcpOffloadReceiveComplete</a> function. For more information, see 
      <a href="netvista.delivery_algorithm">Delivery Algorithm</a>. The host stack will
      set the variable specified by the 
      <i>BytesConsumed</i> parameter to zero.</p>

<p>If the host stack returns NDIS_STATUS_OFFLOAD_DATA_PARTIALLY_ACCEPTED, indicating that the client
      application consumed a subset of the receive data, the offload target resumes ownership of the
      indicated NET_BUFFER_LIST structures when the 
      <b>NdisTcpOffloadReceiveHandler</b> function returns. The host stack will set the variable specified by
      the 
      <i>BytesConsumed</i> parameter to a non-zero value that specifies the amount of data, in bytes, that was
      consumed by the client application. The offload target must buffer the remaining receive data in
      anticipation that the client application will post the receive buffers on the connection.</p>

<p>Note that the offload target never supplies a 
    <i>Status</i> value of NDIS_STATUS_RESOURCES when calling the 
    <b>NdisTcpOffloadReceiveHandler</b> function.</p>

<p>In the 
    <b>RcvIndicationSize</b> member of the TCP_OFFLOAD_STATE_CACHED structure, the host stack can specify the
    optimum number of data bytes that the offload target should supply in a single call to the 
    <b>NdisTcpOffloadReceiveHandler</b> function. For more information, see 
    <a href="netvista.using_the_specified_receive_indication_size">Using the Specified
    Receive Indication Size</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--mdl.md">MDL</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-tcp-offload-receive-handler.md">MiniportTcpOffloadReceive</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-tcp-offload-receive-return-handler.md">
   MiniportTcpOffloadReceiveReturn</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_OFFLOAD_RECEIVE_INDICATE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>