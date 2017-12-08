---
UID: NF.prcomoem.IPrintCoreHelper.WhyConstrained
title: IPrintCoreHelper::WhyConstrained
author: windows-driver-content
description: The IPrintCoreHelper::WhyConstrained method provides a list of options that are constraining the specified feature-option pair in the current configuration.
old-location: print\iprintcorehelper_whyconstrained.htm
old-project: print
ms.assetid: de3fdbd4-9647-4369-9c23-4779aa768b1b
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintCoreHelper, WhyConstrained, IPrintCoreHelper::WhyConstrained
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintCoreHelper.WhyConstrained
req.alt-loc: prcomoem.h
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
req.iface: IPrintCoreHelper
req.product: Windows 10 or later.
---

# IPrintCoreHelper::WhyConstrained method



## -description
<p>The <b>IPrintCoreHelper::WhyConstrained</b> method provides a list of options that are constraining the specified feature-option pair in the current configuration.</p>


## -syntax

````
HRESULT WhyConstrained(
  [in]  const DEVMODE              *pDevmode,
  [in]        DWORD                cbSize,
  [in]        PCSTR                pszFeatureKeyword,
  [in]        PCSTR                pszOptionKeyword,
  [out] const PRINT_FEATURE_OPTION **ppFOConstraints,
  [out]       DWORD                *pdwNumOptions
);
````


## -parameters
<dl>

### -param pDevmode [in]

<dd>
<p>A pointer to a <a href="display.devmodew">DEVMODEW</a> structure. If this pointer is provided, <b>IPrintCoreHelper::WhyConstrained</b> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from either <a href="print.iprintoemps_devmode">IPrintOemPS::DevMode</a> or <a href="print.iprintoemuni_devmode">IPrintOemUni::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.</p>
</dd>

### -param cbSize [in]

<dd>
<p>The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter. </p>
</dd>

### -param pszFeatureKeyword [in]

<dd>
<p>A pointer to an ANSI string that contains the name of the feature. The feature name should correspond to the keyword that is used in the GPD or PPD file.</p>
</dd>

### -param pszOptionKeyword [in]

<dd>
<p>A pointer to an ANSI string that contains the name of the option. The option name should correspond to the keyword that is used in the GPD or PPD file.</p>
</dd>

### -param ppFOConstraints [out]

<dd>
<p>A pointer to an array of <a href="..\prcomoem\ns-prcomoem--print-feature-option.md">PRINT_FEATURE_OPTION</a> elements. When <b>IPrintCoreHelper::WhyConstrained</b> returns, the array contains a list of feature-element pairs of the options that constrain the options that are specified in the <i>pszOptionKeyword </i>parameter.</p>
</dd>

### -param pdwNumOptions [out]

<dd>
<p>A pointer to a variable that receives the number of feature-option pairs in the array that is pointed to by the <i>ppFOConstraints</i> parameter.</p>
</dd>
</dl>

## -returns
<p><b>IPrintCoreHelper::WhyConstrained</b> should return one of the following values.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The operation succeeded.</p><dl>
<dt><b>E_INVALIDARG</b></dt>
</dl><p>One or more of the arguments is invalid, or the feature was not supported.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>Memory for the result array could not be allocated.</p>

<p> </p>

## -remarks
<p>If the specified feature-option pair is not constrained, <b>IPrintCoreHelper::WhyConstrained</b> will return S_OK but will return with *<i>pdwFOPairs</i> set to 0 and with *<i>ppFOConstraints</i>[0] set to <b>NULL</b>.</p>

<p>Note that the results from this method might not contain all of the options that affect the currently selected option. For Unidrv drivers, this list will include at least one option from each set of constraints that is active. If there are invalid combinations that list more than two feature-option pairs, however, only one option from the combination will be included in the list.</p>

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
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintcorehelper_enumconstrainedoptions">IPrintCoreHelper::EnumConstrainedOptions</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelper::WhyConstrained method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>