---
UID: NC.ndischimney.W_UPDATE_OFFLOAD_HANDLER
title: W_UPDATE_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportUpdateOffload function updates previously offloaded TCP chimney state objects.
old-location: netvista\miniportupdateoffload.htm
old-project: netvista
ms.assetid: b98b2e21-8b28-4da0-9cc9-6fa8cb6e5be7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PD_BUFFER_VIRTUAL_SUBNET_INFO, PD_BUFFER_VIRTUAL_SUBNET_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportUpdateOffload
req.alt-loc: Ndischimney.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
---

# W_UPDATE_OFFLOAD_HANDLER callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]
The 
  <i>MiniportUpdateOffload</i> function updates previously offloaded TCP chimney state objects.


## -prototype

````
W_UPDATE_OFFLOAD_HANDLER MiniportUpdateOffload;

VOID MiniportUpdateOffload(
  _In_ NDIS_HANDLE              MiniportAdapterContext,
  _In_ PNDIS_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

The handle to an offload target-allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="netvista.ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.

### -param OffloadBlockList [in]

A pointer to an 
     <a href="netvista.ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state objects that are being updated. Only cached
     variables are updated.

## -returns
None

## -remarks
Only cached variables are updated.

The 
    <i>MiniportUpdateOffload</i> function stores the 
    <i>MiniportAdapterContext</i> handle and the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the update operation
    asynchronously by calling the 
    <a href="netvista.ndismupdateoffloadcomplete">
    NdisMUpdateOffloadComplete</a> function. The 
    <i>OffloadBlockList</i> pointer points to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that can either be
    a stand-alone structure or the root block list in an 
    <a href="netvista.offload_state_tree">offload state tree</a> that contains multiple
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. Such block lists, as well as any 
    <a href="netvista.offload_state_structures">offload state structures</a> that are
    associated with them, are valid until the miniport driver calls the 
    <b>
    NdisMUpdateOffloadComplete</b> function.

Before the 
    <i>MiniportUpdateOffload</i> function returns, the offload target uses the offload state tree passed to
    the 
    <i>MiniportUpdateOffload</i> function to update offloaded state:

The offload target copies the variable values from any state structures in the tree to the
      corresponding 
      <a href="netvista.offload_state_objects">offloaded state objects</a>. Only CACHED
      variables are updated.

The tree might indicate that path-to-neighbor links must be updated. For more information, see 
      <a href="netvista.linking_path_state_objects_to_a_new_neighbor_state_object">Linking
      Path State Objects to a New Neighbor State Object</a>. In this case, the offload target must update
      its internal representation of offloaded state to reflect the updated links.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="netvista.ndismupdateoffloadcomplete">NdisMUpdateOffloadComplete</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_UPDATE_OFFLOAD_HANDLER callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>