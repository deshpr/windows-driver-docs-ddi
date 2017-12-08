---
UID: NC.dot11wdi.NDIS_WDI_TX_SEND_PAUSE_IND
title: NDIS_WDI_TX_SEND_PAUSE_IND
author: windows-driver-content
description: The NdisWdiTxSendPauseIndication callback function pauses transmissions on a given port to a given peer or peer-TID combination.
old-location: netvista\ndiswditxsendpauseindication.htm
old-project: netvista
ms.assetid: A8001D08-36B8-4557-A763-103BDC807CA4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE, *PSYNTHVOICEPRIORITY_INSTANCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisWdiTxSendPauseIndication
req.alt-loc: dot11wdi.h
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
req.iface: ISynthSinkDMus
---

# NDIS_WDI_TX_SEND_PAUSE_IND callback



## -description
<p>The NdisWdiTxSendPauseIndication callback function pauses transmissions on a given port to a given peer or peer-TID combination.</p>
<p>This is a callback inside <a href="..\dot11wdi\ns-dot11wdi--ndis-wdi-data-api.md">NDIS_WDI_DATA_API</a>.</p>


## -prototype

````
NDIS_WDI_TX_SEND_PAUSE_IND NdisWdiTxSendPauseIndication;

VOID NdisWdiTxSendPauseIndication(
  _In_ NDIS_HANDLE         NdisMiniportDataPathHandle,
  _In_ WDI_PORT_ID         PortId,
  _In_ WDI_PEER_ID         PeerId,
  _In_ UINT32              ExTidBitmask,
  _In_ WDI_TX_PAUSE_REASON TxPauseReason
)
{ ... }
````


## -parameters
<dl>

### -param NdisMiniportDataPathHandle [in]

<dd>
<p>The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport-wdi-tal-txrx-initialize.md">MiniportWdiTalTxRxInitialize</a>.</p>
</dd>

### -param PortId [in]

<dd>
<p>The port ID. Wildcards are accepted.</p>
</dd>

### -param PeerId [in]

<dd>
<p>The peer ID. Wildcards are accepted.</p>
</dd>

### -param ExTidBitmask [in]

<dd>
<p>The Extended TID bitmask. See <i>Remarks</i> section for more information.</p>
</dd>

### -param TxPauseReason [in]

<dd>
<p>TX pause reason bitmask, specified as <a href="..\dot11wdi\ne-dot11wdi--wdi-tx-pause-reason.md">WDI_TX_PAUSE_REASON</a> value(s). See <i>Remarks</i> section for more information.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>In the <i>ExTidBitmask</i> parameter, the <i>i</i><sup>th</sup> bit represents extended TID <i>i </i>(the least significant bit is bit 0) .</p>

<p>The <a href="..\dot11wdi\ne-dot11wdi--wdi-tx-pause-reason.md">WDI_TX_PAUSE_REASON</a> bitmask may contain a set of pause reasons. The pauses reasons are cumulative, so an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_CREDIT</b> followed by an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_IHV1</b> requires an <a href="..\dot11wdi\nc-dot11wdi-ndis-wdi-tx-send-restart-ind.md">NdisWdiTxSendRestartIndication</a> with a pause reason of (<b>WDI_TX_PAUSE_REASON_CREDIT</b> | <b>WDI_TX_PAUSE_REASON_IHV1</b>) for the set of queues to be unpaused.</p>

<p>If the pause reason is <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/target does not issue an <a href="..\dot11wdi\nc-dot11wdi-ndis-wdi-tx-send-restart-ind.md">NdisWdiTxSendRestartIndication</a> to any of the affected queues until it has received an <a href="..\dot11wdi\nc-dot11wdi-miniport-wdi-tx-tal-queue-in-order.md">MiniportWdiTxTalQueueInOrder</a> notification for that queue</p>

<p>If <b>TargetPriorityQueueing</b> is true, <a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a> must be a wildcard.  Only port or adapter pauses are allowed in this mode.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dot11wdi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dot11wdi\ns-dot11wdi--ndis-wdi-data-api.md">NDIS_WDI_DATA_API</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-miniport-wdi-tx-tal-queue-in-order.md">MiniportWdiTxTalQueueInOrder</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-ndis-wdi-tx-send-restart-ind.md">NdisWdiTxSendRestartIndication</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
</dt>
<dt>
<a href="..\dot11wdi\ne-dot11wdi--wdi-tx-pause-reason.md">WDI_TX_PAUSE_REASON</a>
</dt>
<dt>
<a href="netvista.wdi_txrx_capabilities">WDI_TXRX_CAPABILITIES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_SEND_PAUSE_IND callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>