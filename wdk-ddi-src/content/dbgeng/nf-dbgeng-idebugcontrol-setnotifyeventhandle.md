---
UID: NF.dbgeng.IDebugControl.SetNotifyEventHandle
title: IDebugControl::SetNotifyEventHandle
author: windows-driver-content
description: The SetNotifyEventHandle method sets the event that will be signaled after the next exception in a target.
old-location: debugger\setnotifyeventhandle.htm
old-project: debugger
ms.assetid: 0c0059a7-4b0f-4b74-b543-ad5904d40033
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl, SetNotifyEventHandle, IDebugControl::SetNotifyEventHandle
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
req.alt-api: IDebugControl.SetNotifyEventHandle,IDebugControl2.SetNotifyEventHandle,IDebugControl3.SetNotifyEventHandle
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
req.iface: IDebugControl
---

# IDebugControl::SetNotifyEventHandle method



## -description
<p>The <b>SetNotifyEventHandle</b> method sets the event that will be signaled after the next <a href="wdkgloss.e#wdkgloss.exception#wdkgloss.exception"><i>exception</i></a> in a target.</p>


## -syntax

````
HRESULT SetNotifyEventHandle(
  [in] ULONG64 Handle
);
````


## -parameters
<dl>

### -param Handle [in]

<dd>
<p>Specifies the handle of the event to signal.  If <i>Handle</i> is <b>NULL</b>, no event will be signaled.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>After setting the event to signal, and after the next exception occurs in a target, when the engine resumes execution in the target, the event will be signaled.</p>

<p>The event will only be signaled once.  After it has been signaled, <b>GetNotifyEventHandle</b> will return <b>NULL</b>, unless this method is called to set another event to signal.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="debugger.setnotifyeventhandle">SetNotifyEventHandle</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetNotifyEventHandle method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>