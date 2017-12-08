---
UID: NF.dbgeng.IDebugControl.GetBreakpointById
title: IDebugControl::GetBreakpointById
author: windows-driver-content
description: The GetBreakpointById method returns the breakpoint with the specified breakpoint ID.
old-location: debugger\getbreakpointbyid.htm
old-project: debugger
ms.assetid: 6873609d-7f5a-474d-8b48-fee9f93c812b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl, GetBreakpointById, IDebugControl::GetBreakpointById
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
req.alt-api: IDebugControl.GetBreakpointById,IDebugControl2.GetBreakpointById,IDebugControl3.GetBreakpointById
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

# IDebugControl::GetBreakpointById method



## -description
<p>The <b>GetBreakpointById</b>  method returns the breakpoint with the specified breakpoint ID.</p>


## -syntax

````
HRESULT GetBreakpointById(
  [in]  ULONG             Id,
  [out] PDEBUG_BREAKPOINT *Bp
);
````


## -parameters
<dl>

### -param Id [in]

<dd>
<p>Specifies the breakpoint ID of the breakpoint to return.</p>
</dd>

### -param Bp [out]

<dd>
<p>Receives the breakpoint.</p>
</dd>
</dl>

## -returns
<p>This method can also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl><p>No breakpoint was found with the given ID, or the breakpoint with the specified ID does not belong to the current process, or the breakpoint with the given ID is private (see <a href="debugger.getflags">GetFlags</a>).</p>

<p> </p>

## -remarks
<p>If the specified breakpoint does not belong to the current process, the method will fail.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetBreakpointById method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>