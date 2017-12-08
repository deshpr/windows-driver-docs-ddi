---
UID: NF.ndis.NdisRawWritePortBufferUlong
title: NdisRawWritePortBufferUlong
author: windows-driver-content
description: NdisRawWritePortBufferUlong writes a specified number of ULONG values from a caller-supplied buffer to a given I/O port.
old-location: netvista\ndisrawwriteportbufferulong.htm
old-project: netvista
ms.assetid: f97aa977-289b-4a46-b724-9a5c1b468b74
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisRawWritePortBufferUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortBufferUlong   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortBufferUlong   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisRawWritePortBufferUlong
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
req.irql: Any level
req.iface: 
---

# NdisRawWritePortBufferUlong function



## -description
<p><b>NdisRawWritePortBufferUlong</b> writes a specified number of ULONG values from a caller-supplied buffer
  to a given I/O port.</p>


## -syntax

````
VOID NdisRawWritePortBufferUlong(
  _In_ ULONG_PTR Port,
  _In_ PULONG    Buffer,
  _In_ ULONG     Length
);
````


## -parameters
<dl>

### -param Port [in]

<dd>
<p>Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.</p>
</dd>

### -param Buffer [in]

<dd>
<p>Pointer to a caller-allocated resident buffer containing the ULONGs to be written.</p>
</dd>

### -param Length [in]

<dd>
<p>Specifies the number of ULONGs to write to the I/O port.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A miniport driver calls 
    <b>NdisRawWritePortBufferUlong</b> to transfer a sequence of ULONGs, one at a time, to a NIC.</p>

<p><b>NdisRawWritePortBufferUlong</b> runs fast because it need not map a bus-relative port address onto a
    host-dependent logical port address at every call.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/93b7f84a-e7bc-4c07-a05a-d28a307d26c7">NdisRawWritePortBufferUlong
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisRawWritePortBufferUlong
   (NDIS 5.1)</b>) in Windows XP.</p>
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
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawreadportbufferulong.md">NdisRawReadPortBufferUlong</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportbufferuchar.md">NdisRawWritePortBufferUchar</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportbufferushort.md">NdisRawWritePortBufferUshort</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportulong.md">NdisRawWritePortUlong</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawWritePortBufferUlong function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>