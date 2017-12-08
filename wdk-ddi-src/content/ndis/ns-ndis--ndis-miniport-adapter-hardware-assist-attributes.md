---
UID: NS.ndis._NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
title: NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
author: windows-driver-content
description: The NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure specifies the hardware-assisted attributes of the network adapter.
old-location: netvista\ndis_miniport_adapter_hardware_assist_attributes.htm
old-project: netvista
ms.assetid: b0662a2c-feb6-4d66-89c9-586c2859b78b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.iface: 
---

# NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure



## -description
<p>The <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure specifies the hardware-assisted attributes of the network adapter.</p>


## -syntax

````
typedef struct _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES {
  NDIS_OBJECT_HEADER                Header;
  PNDIS_HD_SPLIT_ATTRIBUTES         HDSplitAttributes;
#if (NDIS_SUPPORT_NDIS620)
  PNDIS_RECEIVE_FILTER_CAPABILITIES HardwareReceiveFilterCapabilities;
  PNDIS_RECEIVE_FILTER_CAPABILITIES CurrentReceiveFilterCapabilities;
  PNDIS_NIC_SWITCH_CAPABILITIES     HardwareNicSwitchCapabilities;
  PNDIS_NIC_SWITCH_CAPABILITIES     CurrentNicSwitchCapabilities;
#endif 
#if NDIS_SUPPORT_NDIS630
  PNDIS_SRIOV_CAPABILITIES          HardwareSriovCapabilities;
  PNDIS_SRIOV_CAPABILITIES          CurrentSriovCapabilities;
  PNDIS_QOS_CAPABILITIES            HardwareQosCapabilities;
  PNDIS_QOS_CAPABILITIES            CurrentQosCapabilities;
#endif 
} NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES.
     </p>
<p>To indicate the version of the <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure, set the 
     <b>Revision</b> member to one of the following values:</p>
<p></p>
<dl>

### -field NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_3

<dd>
<p>Added various members for NDIS 6.30.</p>
<p>Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_3.</p>
</dd>

### -field NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_2

<dd>
<p>Added the 
        <b>HardwareReceiveFilterCapabilities</b>, 
        <b>CurrentReceiveFilterCapabilities</b>, 
        <b>HardwareNicSwitchCapabilities</b>, and 
        <b>CurrentNicSwitchCapabilities</b> members for NDIS 6.20.</p>
<p>Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_2.</p>
</dd>

### -field NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_1

<dd>
<p>Original version for NDIS 6.1.</p>
<p>Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES_REVISION_1.</p>
</dd>
</dl>
</dd>

### -field HDSplitAttributes

<dd>
<p>A pointer to an 
     <a href="..\ndis\ns-ndis--ndis-hd-split-attributes.md">NDIS_HD_SPLIT_ATTRIBUTES</a> structure
     that represents the header-data split capabilities that the network adapter provides. If the network adapter does not support the header-data split feature, set 
     <b>HDSplitAttributes</b> to <b>NULL</b>.</p>
</dd>

### -field HardwareReceiveFilterCapabilities

<dd>
<p>A pointer to an 
     <a href="..\ntddndis\ns-ntddndis--ndis-receive-filter-capabilities.md">
     NDIS_RECEIVE_FILTER_CAPABILITIES</a> structure. This structure specifies the hardware receive
     filtering capabilities of the network adapter. This value can be <b>NULL</b> if the network adapter does not
     support receive filtering.</p>
<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>CurrentReceiveFilterCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>

### -field CurrentReceiveFilterCapabilities

<dd>
<p>A pointer to an NDIS_RECEIVE_FILTER_CAPABILITIES structure. This structure specifies the receive
     filtering capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the
     network adapter does not support receive filtering.</p>
<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>HardwareReceiveFilterCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>

### -field HardwareNicSwitchCapabilities

<dd>
<p>A pointer to an 
     <a href="..\ntddndis\ns-ntddndis--ndis-nic-switch-capabilities.md">
     NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the hardware NIC switch
     capabilities of the network adapter. This value can be <b>NULL</b> if the network adapter does not support
     NIC switch features or receive filtering.</p>
<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>CurrentNicSwitchCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>

### -field CurrentNicSwitchCapabilities

<dd>
<p>A pointer to an <a href="..\ntddndis\ns-ntddndis--ndis-nic-switch-capabilities.md">NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the NIC switch
     capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the network adapter does not support NIC switch features or receive filtering.</p>
<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>HardwareNicSwitchCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>

### -field HardwareSriovCapabilities

<dd>
<p>A pointer to an <a href="..\ntddndis\ns-ntddndis--ndis-sriov-capabilities.md">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter hardware. This value can be <b>NULL</b> if the network adapter does not support SR-IOV.</p>
<p>For more information on SR-IOV, see <a href="netvista.single_root_i_o_virtualization__sr-iov_">Single Root I/O Virtualization (SR-IOV)</a>.</p>
<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>CurrentSriovCapabilities</b>, <b>HardwareNicSwitchCapabilities</b>, and <b>CurrentNicSwitchCapabilities</b> members must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>

### -field CurrentSriovCapabilities

<dd>
<p>A pointer to an <a href="..\ntddndis\ns-ntddndis--ndis-sriov-capabilities.md">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the SR-IOV capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the network adapter does not support SR-IOV. </p>
<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>HardwareSriovCapabilities</b>, <b>HardwareNicSwitchCapabilities</b>, and <b>CurrentNicSwitchCapabilities</b> members must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>

### -field HardwareQosCapabilities

<dd>
<p>A pointer to an <a href="..\ntddndis\ns-ntddndis--ndis-qos-capabilities.md">NDIS_QOS_CAPABILITIES</a> structure. This structure specifies the hardware capabilities that the network adapter supports for NDIS quality of service (QoS) over the IEEE 802.1 Data Center Bridging (DCB) interface. This value can be <b>NULL</b> if the network adapter does not support NDIS QoS hardware capabilities for DCB. </p>
<p>For more information, see <a href="netvista.ndis_qos_for_data_center_bridging">NDIS QoS for Data Center Bridging</a>.</p>
<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>CurrentQosCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>

### -field CurrentQosCapabilities

<dd>
<p>A pointer to an <a href="..\ntddndis\ns-ntddndis--ndis-qos-capabilities.md">NDIS_QOS_CAPABILITIES</a> structure. This structure specifies the hardware capabilities that are currently enabled on the network adapter for NDIS QoS over the DCB interface. This value can be <b>NULL</b> if the network adapter does not support NDIS QoS hardware capabilities for DCB. </p>
<p>If the adapter supports NDIS QoS capabilties but those capabilities are disabled, the miniport driver must set all members of the <a href="..\ntddndis\ns-ntddndis--ndis-qos-capabilities.md">NDIS_QOS_CAPABILITIES</a> structure (with the exception of the <b>Header</b> member) to zero.</p>
<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>HardwareQosCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
</dd>
</dl>

## -remarks
<p>To register the hardware-assisted capabilities of the underlying network adapter, the miniport driver calls the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function from its 
    <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a> function. The driver passes 
    an initialized <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b>
    structure to the <i>MiniportAttributes</i> parameter of this function. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-hd-split-attributes.md">NDIS_HD_SPLIT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-nic-switch-capabilities.md">NDIS_NIC_SWITCH_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-receive-filter-capabilities.md">
   NDIS_RECEIVE_FILTER_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-qos-capabilities.md">NDIS_QOS_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-sriov-capabilities.md">NDIS_SRIOV_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>