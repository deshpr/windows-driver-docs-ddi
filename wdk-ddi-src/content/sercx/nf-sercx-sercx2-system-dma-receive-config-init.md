---
UID: NF.sercx.SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT
title: SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT
author: windows-driver-content
description: The SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT function initializes a SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure.
old-location: serports\sercx2_system_dma_receive_config_init.htm
old-project: serports
ms.assetid: 9BD18E2C-731D-4C7D-8363-67136521B4A7
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level.
req.iface: 
req.product: Windows 10 or later.
---

# SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT function



## -description
<p>The <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</b> function initializes a <a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure.</p>


## -syntax

````
VOID SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT(
  _Out_ SERCX2_SYSTEM_DMA_RECEIVE_CONFIG *Config,
  _In_  size_t                           MaximumTransferLength,
  _In_  PHYSICAL_ADDRESS                 Address,
  _In_  DMA_WIDTH                        DmaWidth,
  _In_  PCM_PARTIAL_RESOURCE_DESCRIPTOR  DmaDescriptor
);
````


## -parameters
<dl>

### -param Config [out]

<dd>
<p>A pointer to the <a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure that is to be initialized.</p>
</dd>

### -param MaximumTransferLength [in]

<dd>
<p>The value to load into the <b>MaximumTransferLength</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.</p>
</dd>

### -param Address [in]

<dd>
<p>The value to load into the <b>DeviceAddress</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.</p>
</dd>

### -param DmaWidth [in]

<dd>
<p>The value to load into the <b>DmaWidth</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.</p>
</dd>

### -param DmaDescriptor [in]

<dd>
<p>The value to load into the <b>DmaDescriptor</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>Your serial controller driver must use either this function or the <a href="..\sercx\nf-sercx-sercx2-system-dma-receive-config-init-new-data-notification.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a> function to initialize a <a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method.</p>

<p><b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b>), and sets four additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</b> call.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>
</dt>
<dt>
<a href="..\sercx\ns-sercx--sercx2-system-dma-receive-config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2-system-dma-receive-config-init-new-data-notification.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>