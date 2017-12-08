---
UID: NS.ntddk._WHEA_XPF_MC_BANK_DESCRIPTOR
title: WHEA_XPF_MC_BANK_DESCRIPTOR
author: windows-driver-content
description: The WHEA_XPF_MC_BANK_DESCRIPTOR structure describes a bank of machine check registers for an x86 or x64 processor.
old-location: whea\whea_xpf_mc_bank_descriptor.htm
old-project: whea
ms.assetid: e5360f75-53cf-4025-9a1c-665c098329dd
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_XPF_MC_BANK_DESCRIPTOR, WHEA_XPF_MC_BANK_DESCRIPTOR, *PWHEA_XPF_MC_BANK_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_XPF_MC_BANK_DESCRIPTOR
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# WHEA_XPF_MC_BANK_DESCRIPTOR structure



## -description
<p>The WHEA_XPF_MC_BANK_DESCRIPTOR structure describes a bank of machine check registers for an x86 or x64 processor.</p>


## -syntax

````
typedef struct _WHEA_XPF_MC_BANK_DESCRIPTOR {
  UCHAR             BankNumber;
  BOOLEAN           ClearOnInitialization;
  UCHAR             StatusDataFormat;
  XPF_MC_BANK_FLAGS Flags;
  ULONG             ControlMsr;
  ULONG             StatusMsr;
  ULONG             AddressMsr;
  ULONG             MiscMsr;
  ULONGLONG         ControlData;
} WHEA_XPF_MC_BANK_DESCRIPTOR, *PWHEA_XPF_MC_BANK_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field BankNumber

<dd>
<p>The processor machine check register bank number.</p>
</dd>

### -field ClearOnInitialization

<dd>
<p>A Boolean value that indicates that the status registers for the bank are to be cleared by the operating system during initialization.</p>
</dd>

### -field StatusDataFormat

<dd>
<p>The format of the data in the register bank's status register. Possible values are:</p>
<p></p>
<dl>

### -field WHEA_XPF_MC_BANK_STATUSFORMAT_IA32MCA

<dd>
<p>IA32 machine check architecture.</p>
</dd>

### -field WHEA_XPF_MC_BANK_STATUSFORMAT_Intel64MCA

<dd>
<p>Intel64 machine check architecture.</p>
</dd>

### -field WHEA_XPF_MC_BANK_STATUSFORMAT_AMD64MCA

<dd>
<p>AMD64 machine check architecture.</p>
</dd>
</dl>
</dd>

### -field Flags

<dd>
<p>An XPF_MC_BANK_FLAGS union that indicates which of the members of the WHEA_XPF_MC_BANK_DESCRIPTOR structure can be written to by the operating system. The XPF_MC_BANK_FLAGS union is defined as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _XPF_MC_BANK_FLAGS {
  struct {
    UCHAR  ClearOnInitializationRW:1;
    UCHAR  ControlDataRW:1;
    UCHAR  Reserved:6;
  };
  UCHAR  AsUCHAR;
} XPF_MC_BANK_FLAGS, *PXPF_MC_BANK_FLAGS;</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -field ClearOnInitializationRW

<dd>
<p>A single bit that indicates that the operating system can write to the <b>ClearOnInitialization</b> member of the WHEA_XPF_MC_BANK_DESCRIPTOR structure.</p>
</dd>

### -field ControlDataRW

<dd>
<p>A single bit that indicates that the operating system can write to the <b>ControlData</b> member of the WHEA_XPF_MC_BANK_DESCRIPTOR structure.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use.</p>
</dd>

### -field AsUCHAR

<dd>
<p>A UCHAR representation of contents of the XPF_MC_BANK_FLAGS union.</p>
</dd>
</dl>
</dd>

### -field ControlMsr

<dd>
<p>The model-specific register address of the register bank's IA32_MCi_CTL register. For more information about the IA32_MCi_CTL register, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.</p>
</dd>

### -field StatusMsr

<dd>
<p>The model-specific register address of the register bank's IA32_MCi_STATUS register. For more information about the IA32_MCi_STATUS register, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.</p>
</dd>

### -field AddressMsr

<dd>
<p>The model-specific register address of the register bank's IA32_MCi_ADDR register. For more information about the IA32_MCi_ADDR register, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.</p>
</dd>

### -field MiscMsr

<dd>
<p>The model-specific register address of the register bank's IA32_MCi_MISC register. For more information about the IA32_MCi_MISC register, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>.</p>
</dd>

### -field ControlData

<dd>
<p>The value that the operating system writes to the register bank's control register during initialization.</p>
</dd>
</dl>

## -remarks
<p>An array of WHEA_XPF_MC_BANK_DESCRIPTOR structures is contained in the <a href="..\ntddk\ns-ntddk--whea-xpf-cmc-descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a> and <a href="..\ntddk\ns-ntddk--whea-xpf-mce-descriptor.md">WHEA_XPF_MCE_DESCRIPTOR</a> structures.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\ns-ntddk--whea-xpf-cmc-descriptor.md">WHEA_XPF_CMC_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-xpf-mce-descriptor.md">WHEA_XPF_MCE_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_MC_BANK_DESCRIPTOR structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>