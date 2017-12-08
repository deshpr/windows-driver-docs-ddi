---
UID: NF.prcomoem.IPrintCoreHelperUni.GetFontSubstitution
title: IPrintCoreHelperUni::GetFontSubstitution
author: windows-driver-content
description: The IPrintCoreHelperUni::GetFontSubstitution method indicates which device font, if any, is used as a substitution font for a specified TrueType font.
old-location: print\iprintcorehelperuni_getfontsubstitution.htm
old-project: print
ms.assetid: f11b3b85-d01b-4133-9279-bff0001e04f9
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintCoreHelperUni, GetFontSubstitution, IPrintCoreHelperUni::GetFontSubstitution
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
req.alt-api: IPrintCoreHelperUni.GetFontSubstitution
req.alt-loc: Prcomoem.h
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
req.iface: IPrintCoreHelperUni
req.product: Windows 10 or later.
---

# IPrintCoreHelperUni::GetFontSubstitution method



## -description
<p>The <code>IPrintCoreHelperUni::GetFontSubstitution</code> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.</p>


## -syntax

````
STDMETHOD GetFontSubstitution(
  [in]  PCWSTR pszTrueTypeFontName,
  [out] PCWSTR *ppszDevFontName
);
````


## -parameters
<dl>

### -param pszTrueTypeFontName [in]

<dd>
<p>A pointer to a null-terminated Unicode string that contains the name of a TrueType font. </p>
</dd>

### -param ppszDevFontName [out]

<dd>
<p>A pointer to a variable that receives the address of a null-terminated Unicode string. This string contains the name of the device font that will be used in place of the TrueType font specified in the <i>pszFontName</i> parameter. If there is no device font that can serve as a substitute for the specified TrueType font, this parameter will be set to <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p><code>IPrintCoreHelperUni::GetFontSubstitution</code> should return one of the following values.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method read the option for the specified feature.</p><dl>
<dt><b>E_FAIL</b></dt>
</dl><p>The font that was requested does not exist or was not a TrueType font.</p><dl>
<dt><b>E_INVALIDARG</b></dt>
</dl><p>One or more of the arguments is invalid.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>The core driver was not able to service the request because there was insufficient memory.</p><dl>
<dt><b>E_UNEXPECTED, or other return codes not listed here</b></dt>
</dl><p>The core driver seems to be in an invalid state. The caller should return a failure code.</p>

<p> </p>

## -remarks
<p>If an application attempts to print text that uses the TrueType font specified in the <i>pszTrueTypeFontName</i> parameter, that text will instead be printed in the device font specified in the <i>ppszDevFontName</i> parameter. The device font name must be that of a valid, installed font.</p>

<p>A font is identified by its font face name, which appears in the <b>lfFaceName</b> member of the LOGFONT structure.</p>

<p>To obtain a list of available fonts, create an information context for the current printer, and call <b>SetGraphicsMode</b>(hIC, GM_ADVANCED). Then enumerate device fonts by calling <b>EnumFontFamilies</b>. The callback parameter (see <b>EnumFontFamProc</b> in the Microsoft Windows SDK documentation) of <b>EnumFontFamilies</b> should filter for device fonts by incrementing a counter for each font for which the bitwise AND result (FontType &amp; TRUETYPE_FONTTYPE) is nonzero.</p>

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
<a href="print.iprintcorehelperuni_setfontsubstitution">IPrintCoreHelperUni::SetFontSubstitution</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperUni::GetFontSubstitution method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>