---
UID: NS.pep_x._PEP_PROCESSOR_IDLE_STATE
title: PEP_PROCESSOR_IDLE_STATE
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_STATE structure describes the capabilities of a processor idle state.
old-location: kernel\pep_processor_idle_state.htm
old-project: kernel
ms.assetid: 10CAB3CA-83BF-421B-81F5-2B42790B8928
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_PROCESSOR_IDLE_STATE, PEP_PROCESSOR_IDLE_STATE, *PPEP_PROCESSOR_IDLE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_PROCESSOR_IDLE_STATE
req.alt-loc: pep_x.h
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

# PEP_PROCESSOR_IDLE_STATE structure



## -description
<p>The <b>PEP_PROCESSOR_IDLE_STATE</b> structure describes the capabilities of a processor idle state.</p>


## -syntax

````
typedef struct _PEP_PROCESSOR_IDLE_STATE {
  union {
    ULONG  Ulong;
    struct {
      ULONG Interruptible  :1;
      ULONG CacheCoherent  :1;
      ULONG ThreadContextRetained  :1;
      ULONG CStateType  :4;
      ULONG Reserved  :25;
    };
  };
} PEP_PROCESSOR_IDLE_STATE, *PPEP_PROCESSOR_IDLE_STATE;
````


## -struct-fields
<dl>

### -field ( unnamed union )

<dd>
<p>A collection of flag bits and status fields that can be accessed either individually as bitfields, or together as a 32-bit unsigned integer value.</p>
<dl>

### -field Ulong

<dd>
<p>Flag bits and status fields accessed as a single 32-bit unsigned integer value.</p>
</dd>

### -field ( unnamed struct )

<dd>
<p>Flag bits and status fields accessed as individual bitfields.</p>
<dl>

### -field Interruptible

<dd>
<p>Whether the processor can respond to interrupts when in this idle state. Set this flag bit to 1 if the processor can respond to interrupts, and to 0 if it cannot.</p>
</dd>

### -field CacheCoherent

<dd>
<p>Whether the processor's local cache or caches remain coherent through the duration of this processor idle state. Set this flag bit to 1 if cache coherency is maintained in this idle state, and to 0 if it is not.</p>
</dd>

### -field ThreadContextRetained

<dd>
<p>Whether thread context is retained in this processor idle state. Set this flag bit to 1 if the processor hardware retains the thread context across the idle transition. Set to 0 if the processor uses the multiprocessor parking protocol to exit the idle state and return control to the operating system. For more information about this protocol, see the document titled "Multiprocessor Startup for ARM Platforms" at <a href="https://www.acpica.org/related-documents">https://www.acpica.org/related-documents</a>.</p>
</dd>

### -field CStateType

<dd>
<p>The C-state type of the processor idle state. Set this bitfield to zero if this idle state does not correspond to an ACPI-defined C-state. Otherwise, set this bitfield to the C-state number. That is, set <b>CStateType</b> = 1 for C1, set <b>CStateType</b> = 2 for C2, and so on. For more information about C-states, see section 8.1, "Processor Power States", of the Advanced Configuration and Control Specification, Revision 5.0 (<a href="http://www.acpi.info">ACPI 5.0 specification</a>).</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for future use.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The <b>IdleStates</b> member of the <a href="..\pep_x\ns-pep-x--pep-ppm-query-idle-states.md">PEP_PPM_QUERY_IDLE_STATES</a> structure is the first element in an array of <b>PEP_PROCESSOR_IDLE_STATE</b> structures.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pep_x.h (include Pepfx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\pep_x\ns-pep-x--pep-ppm-query-idle-states.md">PEP_PPM_QUERY_IDLE_STATES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_IDLE_STATE structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>