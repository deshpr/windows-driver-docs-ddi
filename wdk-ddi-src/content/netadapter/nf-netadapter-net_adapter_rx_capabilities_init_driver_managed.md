---
UID: NF:netadapter.NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED
title: NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED function
author: windows-driver-content
description: The NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED method initializes a NET_ADAPTER_RX_CAPABILITIES structure for a net adapter that would like to specify driver-managed receive buffer allocation and attachment.
ms.assetid: d3b29896-25ef-4d96-99db-799408fb207f
ms.author: windowsdriverdev
ms.date: 02/14/2018
ms.topic: function
ms.keywords: NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED
product: Windows
targetos: Windows
---

# NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED** method initializes a [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure for a net adapter that would like to specify driver-managed receive buffer allocation and attachment.

## -parameters

### -param RxCapabilities
A pointer to a driver-allocated [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure.

### -param EvtAdapterReturnRxBuffer
A pointer to the client driver's *EVT_NET_ADAPTER_RETURN_RX_BUFFER* callback function. For more information, see the Remarks section.

### -param MaximumFragmentBufferSize
The maximum fragment buffer size, in bytes, that the adapter can receive.

### -param MaximumNumberOfQueues
The maximum number of receive queues that the adapter supports.

## -returns
This method does not return a value.

## -remarks
This method is one of three possible methods to call in order to initialize a [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure. Which one the client driver should call depends on how it would like to allocate receive buffers and if it would like to use DMA.

The client driver must call **NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED** to initialize its **NET_ADAPTER_RX_CAPABILITIES** structure if it would like to perform manual receive buffer allocation and attachment. By calling this method, the Rx capabilities structure's **AllocationMode** member is set to **NetRxFragmentBufferAllocationModeDriver** and the **AttachmentMode** member is set to **NetRxFragmentBufferAttachmentModeDriver**. In this case, it must also provide a pointer to its *EVT_NET_ADAPTER_RETURN_RX_BUFFER* callback function in the structure for the operating system to invoke once the system has finished with the receive buffer.

The minimum NetAdapterCx version for **NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED** is 1.2.

### EvtNetAdapterReturnRxBuffer

Implement this optional callback function to perform cleanup on a [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffer for which you previously specified manual fragment allocation and attachment.

The syntax for this callback is as follows.

```C++
//Declaration

EVT_NET_ADAPTER_RETURN_RX_BUFFER EvtNetAdapterReturnRxBuffer; 

// Definition

VOID EvtNetAdapterReturnRxBuffer 
(
	_In_	NETADAPTER	Adapter,
	_In_	PVOID		RxBufferVirtualAddress,
	_In_	PVOID		RxBufferReturnContext
)
{...}

typedef EVT_NET_ADAPTER_RETURN_RX_BUFFER *PFN_NET_ADAPTER_RETURN_RX_BUFFER;
```

#### Parameters

##### Adapter 
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

##### RxBufferVirtualAddress 
A pointer to the virtual address of the [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffer. Cast this member to a **PNET_PACKET_FRAGMENT** to retrieve the fragment.

##### RxBufferReturnContext 
A pointer to a driver-allocated context space structure.

#### Remarks

Register your implementation of this callback function by setting the appropriate member of [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure and then calling [NetAdapterSetDatapathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md) during *[EVT_NET_ADAPTER_SET_CAPABILITIES](nc-netadapter-evt_net_adapter_set_capabilities.md)*.

This callback function is optional unless the net adapter client driver initializes its [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure using the [NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md) method. By using this initialization method, the driver tells the operating system that it is managing allocation and attachment of [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive bufffers manually, so it must provide this callback function in this case for the operating system to invoke once the system is finished with the buffer.

## -see-also

[NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_system_managed.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA](nf-netadapter-net_adapter_rx_capabilities_init_system_managed_dma.md)