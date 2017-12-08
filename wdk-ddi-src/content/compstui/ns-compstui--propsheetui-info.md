---
UID: NS.compstui._PROPSHEETUI_INFO
title: PROPSHEETUI_INFO
author: windows-driver-content
description: The PROPSHEETUI_INFO structure is used as an input parameter to PFNPROPSHEETUI-typed functions.
old-location: print\propsheetui_info.htm
old-project: print
ms.assetid: b21c3ee1-13e8-4796-af45-6ba60e84df4e
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: PROPSHEETUI_INFO, PROPSHEETUI_INFO, *PPROPSHEETUI_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PROPSHEETUI_INFO
req.alt-loc: compstui.h
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
req.iface: 
---

# PROPSHEETUI_INFO structure



## -description
<p>The PROPSHEETUI_INFO structure is used as an input parameter to <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed functions.</p>


## -syntax

````
typedef struct _PROPSHEETUI_INFO {
  WORD            cbSize;
  WORD            Version;
  WORD            Flags;
  WORD            Reason;
  HANDLE          hComPropSheet;
  PFNCOMPROPSHEET pfnComPropSheet;
  LPARAM          lParamInit;
  ULONG_PTR       UserData;
  ULONG_PTR       Result;
} PROPSHEETUI_INFO, *PPROPSHEETUI_INFO;
````


## -struct-fields
<dl>

### -field cbSize

<dd>
<p>CPSUI-supplied size, in bytes, of the PROPSHEETUI_INFO structure.</p>
</dd>

### -field Version

<dd>
<p>CPSUI-supplied version number of the PROPSHEETUI_INFO structure. The current version number is defined by PROPSHEETUI_INFO_VERSION in compstui.h.</p>
</dd>

### -field Flags

<dd>
<p>CPSUI-supplied bit flags. The following flag is defined:</p>
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>PSUIINFO_UNICODE</p>
</td>
<td>
<p>If set, the calling application uses Unicode characters.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field Reason

<dd>
<p>CPSUI-supplied constant specifying the action to be performed on the property sheet by the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed function to which the PROPSHEETUI_INFO structure was passed. One of the following constants will be supplied:</p>
<ul>
<li>
<p>PROPSHEETUI_REASON_DESTROY</p>
</li>
<li>
<p>PROPSHEETUI_REASON_GET_ICON</p>
</li>
<li>
<p>PROPSHEETUI_REASON_GET_INFO_HEADER</p>
</li>
<li>
<p>PROPSHEETUI_REASON_INIT</p>
</li>
<li>
<p>PROPSHEETUI_REASON_SET_RESULT</p>
</li>
</ul>
<dl>
<dd>
<p>For information about the meaning of each constant, see the Remarks section of the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> description.</p>
</dd>
</dl>
</dd>

### -field hComPropSheet

<dd>
<p>CPSUI-supplied handle to a property sheet <a href="https://msdn.microsoft.com/b4c40c15-df16-4af0-81c8-9e70d26ba598">group parent</a>. This handle can be passed to CPSUI's <a href="print.compropsheet">ComPropSheet</a> function.</p>
</dd>

### -field pfnComPropSheet

<dd>
<p>Address of CPSUI's <a href="print.compropsheet">ComPropSheet</a> function.</p>
</dd>

### -field lParamInit

<dd>
<p>Value received as the <i>lParam</i> parameter for the associated PFNPROPSHEETUI-typed function, when the function was first called with a <b>Reason</b> of PROPSHEETUI_REASON_INIT. For information about what this value can be, see the description of <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>.</p>
<p>This value is supplied by CPSUI, and is valid for all <b>Reason</b> values.</p>
</dd>

### -field UserData

<dd>
<p>Optional, private value or pointer supplied by the associated <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed function, initially set to zero by CPSUI. If the function stores a value in <b>UserData</b>, then for subsequent calls to the function, the stored value or pointer is unchanged unless changed by the function.</p>
</dd>

### -field Result

<dd>
<p>Result value supplied by the associated <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed function, initially set to zero by CPSUI. If the function stores a result value in <b>Result</b>, then for subsequent calls to the function, the stored value is unchanged unless changed by the function.</p>
<p>If the PFNPROPSHEETUI-typed function's address was specified as an argument to <a href="print.commonpropertysheetui">CommonPropertySheetUI</a>, the last value stored in <b>Result</b> is returned to <b>CommonPropertySheetUI</b> in the location pointed to by its <i>pResult</i> argument.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Compstui.h (include Compstui.h)</dt>
</dl>
</td>
</tr>
</table>