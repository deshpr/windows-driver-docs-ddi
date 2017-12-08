---
UID: NS.dbgeng._SYMBOL_INFO_EX
title: SYMBOL_INFO_EX
author: windows-driver-content
description: The SYMBOL_INFO_EX structure describes the extended line symbol information.
old-location: debugger\symbol_info_ex.htm
old-project: debugger
ms.assetid: BDB8179A-4A97-4E83-B4A4-7B8358B3510C
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SYMBOL_INFO_EX
req.alt-loc: DbgEng.h
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
req.iface: IDebugSystemObjects4
---

# SYMBOL_INFO_EX structure



## -description
<p>The SYMBOL_INFO_EX structure describes the extended line symbol information.</p>


## -syntax

````
typedef struct _SYMBOL_INFO_EX {
  ULONG   SizeOfStruct;
  ULONG   TypeOfInfo;
  ULONG64 Offset;
  ULONG   Line;
  ULONG   Displacement;
  ULONG   Reserved[4];
} SYMBOL_INFO_EX, *PSYMBOL_INFO_EX;
````


## -struct-fields
<dl>

### -field SizeOfStruct

<dd>
<p>Set to sizeof(SYMBOL_INFO_EX).</p>
</dd>

### -field TypeOfInfo

<dd>
<p>Type of the symbol information stored.  DEBUG_SYMINFO_BREAKPOINT_SOURCE_LINE is the only supported type.</p>
</dd>

### -field Offset

<dd>
<p>Address of the first line that does not correspond to compiler added glue line.</p>
</dd>

### -field Line

<dd>
<p>First line number that does not correspond to a compiler added glue line.</p>
</dd>

### -field Displacement

<dd>
<p>Line displacement: Offset between given address and the first instruction of the line.</p>
</dd>

### -field Reserved[4]

<dd>
<p>Reserved for future use. This parameter can be set to any value.</p>
</dd>
</dl>

## -remarks
<p>Glue lines are code lines added to the binary by the compiler/linker. Glue lines do not have corresponding lines in the original source code. They are added to bind together functionality inside of the PE generated binary, for example calling NET framework functions inside of a native binary.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>