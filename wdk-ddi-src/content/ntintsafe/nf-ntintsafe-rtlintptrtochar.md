---
UID: NF.ntintsafe.RtlIntPtrToChar
title: RtlIntPtrToChar function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type CHAR.
old-location: kernel\rtlintptrtochar.htm
old-project: kernel
ms.assetid: 96FC52D7-E383-451A-BB30-9C677F254DE2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlIntPtrToChar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlIntPtrToChar
req.alt-loc: Ntintsafe.h
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
---

# RtlIntPtrToChar function



## -description
Converts a value of type <b>INT_PTR</b> to a value of type <b>CHAR</b>.


## -syntax

````
NTSTATUS RtlIntPtrToChar(
  _In_  INT_PTR iOperand,
  _Out_ CHAR    *pch
);
````


## -parameters

### -param iOperand [in]

The value to be converted.

### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>