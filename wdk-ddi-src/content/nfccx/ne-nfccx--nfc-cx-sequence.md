---
UID: NE.nfccx._NFC_CX_SEQUENCE
title: NFC_CX_SEQUENCE
author: windows-driver-content
description: The NFC_CX_SEQUENCE enumeration specifies sequences.
old-location: nfpdrivers\nfc_cx_sequence.htm
old-project: nfpdrivers
ms.assetid: 752451F9-74FC-48A8-B9B8-2CBD381B91D9
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: NPI_REGISTRATION_INSTANCE, NPI_REGISTRATION_INSTANCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NFC_CX_SEQUENCE
req.alt-loc: nfccx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Requires same
req.iface: 
---

# NFC_CX_SEQUENCE enumeration



## -description
<p>The NFC_CX_SEQUENCE enumeration specifies sequences.</p>


## -syntax

````
typedef enum _NFC_CX_SEQUENCE { 
  SequencePreInit              = 0,
  SequenceInitComplete         = 1,
  SequencePreRfDiscStart       = 2,
  SequenceRfDiscStartComplete  = 3,
  SequencePreRfDiscStop        = 4,
  SequenceRfDiscStopComplete   = 5,
  SequencePreNfceeDisc         = 6,
  SequenceNfceeDiscComplete    = 7,
  SequencePreShutdown          = 8,
  SequenceShutdownComplete     = 9,
  SequencePreRecovery          = 10,
  SequenceRecoveryComplete     = 11,
  SequenceMaximum              = 12
} NFC_CX_SEQUENCE;
````


## -enum-fields
<dl>

### -field SequencePreInit

<dd>
<p>This sequence is invoked by CX during the idle to init state transition, that is, prior to start of initialization by NFC CX. No NCI commands including CORE_RESET_CMD have been sent to the NFC controller by NFC CX. In this sequence, the client can invoke any non-NCI command. NCI commands should not be sent to the controller because neither CORE_RESET_CMD nor CORE_INIT_CMD has been sent to the controller.</p>
</dd>

### -field SequenceInitComplete

<dd>
<p>This sequence is invoked by CX during the idle to init state transition, that is, prior to start of initialization by NFC CX. No NCI commands including CORE_RESET_CMD has been sent to the NFC controller by NFC CX. In this sequence, the client can invoke any non-NCI command. NCI commands should not be sent to the controller since neither CORE_RESET_CMD nor CORE_INIT_CMD has been sent to the controller.</p>
</dd>

### -field SequencePreRfDiscStart

<dd>
<p>This sequence is invoked by CX prior to start of RF discovery i.e. through RF_DISCOVER_CMD. The client driver can use this opportunity to perform any related RF configuration including any optimizations to the discovery loop.</p>
</dd>

### -field SequenceRfDiscStartComplete

<dd>
<p>This sequence is invoked by CX immediately after the start of RF discovery. Any configuration post-discovery start can be supported through this extensibility point.</p>
</dd>

### -field SequencePreRfDiscStop

<dd>
<p>This sequence is invoked by CX prior to stopping the RF discovery loop.</p>
</dd>

### -field SequenceRfDiscStopComplete

<dd>
<p>This sequence is invoked immediately after discovery loop is stopped. The client driver can use this extensibility point to enable any standby mode configuration.</p>
</dd>

### -field SequencePreNfceeDisc

<dd>
<p>This sequence is invoked by CX prior to start of NFCEE discovery. The NFCEE discovery happens with the discovery loop deactivated. The client driver can use this sequence to enable any internal NFC-NFCEE interfaces which could have been disabled post-initialization for power optimizations. </p>
</dd>

### -field SequenceNfceeDiscComplete

<dd>
<p>This sequence is invoked immediately post-NFCEE discovery operation.</p>
</dd>

### -field SequencePreShutdown

<dd>
<p>This sequence is invoked prior to start of shutdown.</p>
</dd>

### -field SequenceShutdownComplete

<dd>
<p>This sequence is invoked by CX after shutdown sequence is complete. The client driver can clean up any NCI state maintained.</p>
</dd>

### -field SequencePreRecovery

<dd>
<p>This sequence is invoked by CX if it needs to perform a recovery sequence due to a fatal failure. The client driver can use this sequence to capture RAM dumps for diagnostic purposes.</p>
</dd>

### -field SequenceRecoveryComplete

<dd>
<p>This sequence is invoked by the CX after the completion of the recovery sequence and when the driver is back to the work-state.</p>
</dd>

### -field SequenceMaximum

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Nfccx.h (include Ncidef.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_SEQUENCE enumeration%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>