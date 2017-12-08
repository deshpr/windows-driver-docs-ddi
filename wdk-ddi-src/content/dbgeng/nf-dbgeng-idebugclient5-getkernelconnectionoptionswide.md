---
UID: NF.dbgeng.IDebugClient5.GetKernelConnectionOptionsWide
title: IDebugClient5::GetKernelConnectionOptionsWide
author: windows-driver-content
description: The GetKernelConnectionOptionsWide method returns the connection options for the current kernel target.
old-location: debugger\getkernelconnectionoptionswide.htm
old-project: debugger
ms.assetid: f85ef2cf-704a-4a7c-aeeb-483a7b1fdc8f
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugClient5, GetKernelConnectionOptionsWide, IDebugClient5::GetKernelConnectionOptionsWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugClient5.GetKernelConnectionOptionsWide
req.alt-loc: dbgeng.h
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
req.iface: IDebugClient5
---

# IDebugClient5::GetKernelConnectionOptionsWide method



## -description
<p>The <b>GetKernelConnectionOptionsWide</b> method returns the connection options for the current kernel target.</p>


## -syntax

````
HRESULT GetKernelConnectionOptionsWide(
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG OptionsSize
);
````


## -parameters
<dl>

### -param Buffer [out, optional]

<dd>
<p>Specifies the buffer to receive the connection options.</p>
</dd>

### -param BufferSize [in]

<dd>
<p>Specifies the size in characters of the buffer <i>Buffer</i>.</p>
</dd>

### -param OptionsSize [out, optional]

<dd>
<p>Receives the size in characters of the connection options.  If <i>OptionsSize</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>The size of the string was greater than the size of the buffer, so it was truncated to fit into the buffer.</p><dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl><p>The current target is not a standard live kernel target.</p>

<p> </p>

## -remarks
<p>This method is available only for live kernel targets that are not local and not connected through eXDI.</p>

<p>The connection options returned are the same options used to connect to the kernel.</p>

<p>For more information about connecting to live kernel-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552005">Live Kernel-Mode Targets</a>.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="debugger.attachkernel">AttachKernel</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetKernelConnectionOptionsWide method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>