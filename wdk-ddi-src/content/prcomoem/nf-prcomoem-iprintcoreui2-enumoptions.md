---
UID: NF:prcomoem.IPrintCoreUI2.EnumOptions
title: IPrintCoreUI2::EnumOptions method
author: windows-driver-content
description: The IPrintCoreUI2::EnumOptions method enumerates the available options of a specific feature.
old-location: print\iprintcoreui2_enumoptions.htm
old-project: print
ms.assetid: 9ae20927-6ef4-4566-939c-967ce1d99874
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: EnumOptions method [Print Devices], IPrintCoreUI2 interface, IPrintCoreUI2, IPrintCoreUI2::EnumOptions, IPrintCoreUI2 interface [Print Devices], EnumOptions method, EnumOptions method [Print Devices], print_unidrv-pscript_ui_bacd11be-a1da-4322-b893-6227b5ad1bc1.xml, print.iprintcoreui2_enumoptions, prcomoem/IPrintCoreUI2::EnumOptions, EnumOptions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintCoreUI2.EnumOptions
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintCoreUI2::EnumOptions method


## -description


The <code>IPrintCoreUI2::EnumOptions</code> method enumerates the available options of a specific feature.


## -syntax


````
HRESULT EnumOptions(
  [in]  POEMUIOBJ poemuiobj,
  [in]  DWORD     dwFlags,
  [in]  PCSTR     pszFeatureKeyword,
  [out] PSTR      pmszOptionList,
  [in]  DWORD     cbSize,
  [out] PDWORD    pcbNeeded
);
````


## -parameters




### -param poemuiobj [in]

Pointer to the current context, an <a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pszFeatureKeyword [in]

Pointer to a caller-supplied buffer containing an ASCII string specifying a feature keyword whose options are requested.


### -param pmszOptionList [out]

Pointer to a caller-supplied buffer that receives a NULL-delimited list, in MULTI_SZ format, containing the option keywords for the feature keyword pointed to by <i>pszFeatureKeyword</i>. This list is terminated with two null characters. 

Set this parameter to <b>NULL</b> to simply query for the size (*<i>pcbNeeded</i>) of the option list without having the list filled in.


### -param cbSize [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszOptionList</i>.


### -param pcbNeeded [out]

Pointer to a memory location that receives the actual size, in bytes, of the option list.


## -returns


This method must return one of the following values.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pmszOptionList</i>).

The method was called with <i>pmszOptionList</i> set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The string pointed to by <i>pszFeatureKeyword</i> is not a recognized feature.

The <i>poemuiobj</i> parameter pointed to an invalid context object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
(Pscript only)

The Pscript5 driver feature is not supported under the current configuration.

The Pscript5 driver feature is supported under the current configuration, but the Pscript5 driver feature's options are not enumerable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The method failed

</td>
</tr>
</table> 



## -remarks


This method is supported only for Windows XP Pscript5 plug-ins, not for Unidrv plug-ins. 

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

For more information, see <a href="https://msdn.microsoft.com/6ce16d28-eff7-4701-a592-046f364cda44">Using EnumOptions</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553050">IPrintCoreUI2::EnumFeatures</a>

<a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::EnumOptions method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
