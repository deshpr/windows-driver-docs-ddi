---
UID: NF.wdfmemory.WdfMemoryCopyFromBuffer
title: WdfMemoryCopyFromBuffer function
author: windows-driver-content
description: The WdfMemoryCopyFromBuffer method copies the contents of a specified source buffer into a specified memory object's buffer.
old-location: wdf\wdfmemorycopyfrombuffer.htm
old-project: wdf
ms.assetid: 702d5239-48cd-4c11-90bc-a86ab27b8cfe
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfMemoryCopyFromBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfMemoryCopyFromBuffer
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, DriverCreate, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level (see Remarks section)
req.product: Windows 10 or later.
---

# WdfMemoryCopyFromBuffer function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfMemoryCopyFromBuffer</b> method copies the contents of a specified source buffer into a specified memory object's buffer.


## -syntax

````
NTSTATUS WdfMemoryCopyFromBuffer(
  _In_ WDFMEMORY DestinationMemory,
  _In_ size_t    DestinationOffset,
  _In_ PVOID     Buffer,
  _In_ size_t    NumBytesToCopyFrom
);
````


## -parameters

### -param DestinationMemory [in]

A handle to a framework memory object that represents the destination buffer.

### -param DestinationOffset [in]

An offset, in bytes, from the beginning of the destination buffer. The copy operation begins at the specified offset in the destination buffer.

### -param Buffer [in]

A pointer to a source buffer.

### -param NumBytesToCopyFrom [in]

The number of bytes to copy from the source buffer to the destination buffer. This value must not be greater than the size of the source buffer.

## -returns
<b>WdfMemoryCopyFromBuffer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>The byte offset that the <i>DestinationOffset</i> parameter specified was too large.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The size of the destination buffer that the <i>DestinationOffset</i> parameter specified, starting at the destination offset, was greater than the <i>NumBytesToCopyFrom</i> parameter.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
The framework verifies that the destination buffer is large enough to receive the amount of data that the <i>NumBytesToCopyFrom</i> parameter specifies.

For more information about framework memory objects, see <a href="wdf.using_memory_buffers">Using Memory Buffers</a>.

If the source or destination buffer was allocated from the pageable memory pool, the <b>WdfMemoryCopyFromBuffer</b> method must be called at IRQL &lt;= APC_LEVEL. Otherwise, the method can be called at any IRQL.

The following code example obtains a handle to the framework memory object that represents an I/O request's output buffer, and then it copies the contents of another buffer into the I/O request's output buffer.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfmemory.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level (see Remarks section)
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_bufafterreqcompletedintioctla">BufAfterReqCompletedIntIoctlA</a>, <a href="devtest.kmdf_bufafterreqcompletedioctla">BufAfterReqCompletedIoctlA</a>, <a href="devtest.kmdf_bufafterreqcompletedreada">BufAfterReqCompletedReadA</a>, <a href="devtest.kmdf_bufafterreqcompletedwritea">BufAfterReqCompletedWriteA</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_memafterreqcompletedintioctla">MemAfterReqCompletedIntIoctlA</a>, <a href="devtest.kmdf_memafterreqcompletedioctla">MemAfterReqCompletedIoctlA</a>, <a href="devtest.kmdf_memafterreqcompletedreada">MemAfterReqCompletedReadA</a>, <a href="devtest.kmdf_memafterreqcompletedwritea">MemAfterReqCompletedWriteA</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfmemorycopytobuffer">WdfMemoryCopyToBuffer</a>
</dt>
<dt>
<a href="wdf.wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfMemoryCopyFromBuffer method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>