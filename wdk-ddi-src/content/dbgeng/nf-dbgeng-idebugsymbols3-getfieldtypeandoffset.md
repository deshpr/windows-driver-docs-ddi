---
UID: NF.dbgeng.IDebugSymbols3.GetFieldTypeAndOffset
title: IDebugSymbols3::GetFieldTypeAndOffset
author: windows-driver-content
description: The GetFieldTypeAndOffset method returns the type of a field and its offset within a container.
old-location: debugger\getfieldtypeandoffset.htm
old-project: debugger
ms.assetid: a73a3bb5-f9f4-41d7-9df7-c7f36a01d157
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSymbols3, GetFieldTypeAndOffset, IDebugSymbols3::GetFieldTypeAndOffset
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
req.alt-api: IDebugSymbols3.GetFieldTypeAndOffset
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
req.iface: IDebugSymbols3
---

# IDebugSymbols3::GetFieldTypeAndOffset method



## -description
<p>The <b>GetFieldTypeAndOffset</b>  method returns the type of a field and its offset within a container.</p>


## -syntax

````
HRESULT GetFieldTypeAndOffset(
  [in]            ULONG64 Module,
  [in]            ULONG   ContainerTypeId,
  [in]            PCSTR   Field,
  [out, optional] PULONG  FieldTypeId,
  [out, optional] PULONG  Offset
);
````


## -parameters
<dl>

### -param Module [in]

<dd>
<p>Specifies the module containing the types of both the container and the field.</p>
</dd>

### -param ContainerTypeId [in]

<dd>
<p>Specifies the type ID for the container's type.  Examples of containers include structures, unions, and classes.</p>
</dd>

### -param Field [in]

<dd>
<p>Specifies the name of the field whose type and offset are requested.  Subfields may be specified by using a dot-separated path.</p>
</dd>

### -param FieldTypeId [out, optional]

<dd>
<p>Receives the type ID of the field.</p>
</dd>

### -param Offset [out, optional]

<dd>
<p>Receives the offset of the field <i>Field</i> from the base memory location of an instance of the container.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl><p>The field <i>Field</i> could not be found in the type specified by <i>ContainerTypeId</i>.</p>

<p> </p>

## -remarks
<p>An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the type of this field and its location relative to the location of MyStruct structure can be found by passing "MyField.MySubField" as the <i>Field</i> parameter to this method.</p>

<p>For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.  For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="debugger.getfieldoffset2">GetFieldOffset</a>
</dt>
<dt>
<a href="debugger.gettypeid">GetTypeId</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetFieldTypeAndOffset method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>