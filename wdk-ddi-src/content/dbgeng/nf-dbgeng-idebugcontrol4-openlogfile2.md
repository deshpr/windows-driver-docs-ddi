---
UID: NF.dbgeng.IDebugControl4.OpenLogFile2
title: IDebugControl4::OpenLogFile2
author: windows-driver-content
description: The OpenLogFile2 method opens a log file that will receive output from the client objects.
old-location: debugger\openlogfile2.htm
old-project: debugger
ms.assetid: 58550baa-8d15-43c7-b75d-1370c36e833d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl4, OpenLogFile2, IDebugControl4::OpenLogFile2
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
req.alt-api: IDebugControl4.OpenLogFile2
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
req.iface: IDebugControl4
---

# IDebugControl4::OpenLogFile2 method



## -description
<p>The <b>OpenLogFile2</b>  method opens a log file that will receive output from the <a href="debugger.client_objects#client_objects#client_objects">client objects</a>.</p>


## -syntax

````
HRESULT OpenLogFile2(
  [in] PCSTR File,
  [in] ULONG Flags
);
````


## -parameters
<dl>

### -param File [in]

<dd>
<p>Specifies the name of the log file.  <i>File</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger  was started.  If the file does not exist, it will be created.</p>
</dd>

### -param Flags [in]

<dd>
<p>Specifies the bit-flags that control the nature of the log file.  <i>Flags</i> can contain flags from the following table.</p>
<table>
<tr>
<th>Flag</th>
<th>Effect when set</th>
</tr>
<tr>
<td>
<p>DEBUG_LOG_APPEND</p>
</td>
<td>
<p>Output will be appended to the log file instead of discarding the contents of the log file.</p>
</td>
</tr>
<tr>
<td>
<p>DEBUG_LOG_UNICODE</p>
</td>
<td>
<p>The format of the log file will be Unicode instead of ASCII.</p>
</td>
</tr>
</table>
<p> </p>
<p>Alternatively, <i>Flags</i> can be set to DEBUG_LOG_DEFAULT for the default set of options that contains none of the flags.</p>
</dd>
</dl>

## -returns
<p>This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>Only one log file can be open at a time.  If there is already a log file open, it will be closed.</p>

<p>For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="debugger.openlogfile">OpenLogFile</a>
</dt>
<dt>
<a href="debugger.getlogfile2">GetLogFile2</a>
</dt>
<dt>
<a href="debugger.closelogfile">CloseLogFile</a>
</dt>
<dt>
<a href="debugger.getlogmask">GetLogMask</a>
</dt>
<dt>
<a href="debugger.setlogmask">SetLogMask</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564018">.logopen (Open Log File)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563986">.logappend (Append Log File)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::OpenLogFile2 method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>