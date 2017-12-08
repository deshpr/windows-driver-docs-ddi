---
UID: NS.ksmedia._KSAUDIO_PACKETSIZE_CONSTRAINTS2
title: KSAUDIO_PACKETSIZE_CONSTRAINTS2
author: windows-driver-content
description: The KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure describes the physical hardware constraints.
old-location: audio\ksaudio_packetsize_constraints2.htm
old-project: audio
ms.assetid: E87C7AA7-A48A-4569-ADD5-9DC143F919B6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KSAUDIO_PACKETSIZE_CONSTRAINTS2, KSAUDIO_PACKETSIZE_CONSTRAINTS2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_PACKETSIZE_CONSTRAINTS2
req.alt-loc: ksmedia.h
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

# KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure



## -description
<p>The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS2</b> structure describes the physical hardware constraints. It includes an array of 0 or more <a href="audio.ksaudio_packetsize_processingmode_constraint">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a> structures describing constraints specific to any signal processing modes.
The driver sets this property before calling <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a> or otherwise enabling its KS filter interface for its streaming pins.</p>


## -syntax

````
typedef struct _KSAUDIO_PACKETSIZE_CONSTRAINTS2 {
  ULONG                                                                                   MinPacketPeriodInHns;
  ULONG                                                                                   PacketSizeFileAlignment;
  ULONG                                                                                   MaxPacketSizeInBytes;
  ULONG                                                                                   NumProcessingModeConstraints;
  _Field_size_(NumProcessingModeConstraints) KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT ProcessingModeConstraints[ANYSIZE_ARRAY];
} KSAUDIO_PACKETSIZE_CONSTRAINTS2, *PKSAUDIO_PACKETSIZE_CONSTRAINTS2;
````


## -struct-fields
<dl>

### -field MinPacketPeriodInHns

<dd>
<p>The absolute minimum processing period supported by the driver expressed in hundred-nanosecond (HNS) units. This value can be 0 if the driver has no specific minimum processing period.</p>
</dd>

### -field PacketSizeFileAlignment

<dd>
<p>The byte size alignment requirement. Use one of these defined file alignment values:</p>
<dl><a id="FILE_BYTE_ALIGNMENT"></a><a id="file_byte_alignment"></a>
### -field FILE_BYTE_ALIGNMENT
<a id="FILE_WORD_ALIGNMENT"></a><a id="file_word_alignment"></a>
### -field FILE_WORD_ALIGNMENT
<a id="FILE_LONG_ALIGNMENT"></a><a id="file_long_alignment"></a>
### -field FILE_LONG_ALIGNMENT
<a id="FILE_QUAD_ALIGNMENT"></a><a id="file_quad_alignment"></a>
### -field FILE_QUAD_ALIGNMENT
<a id="FILE_OCTA_ALIGNMENT"></a><a id="file_octa_alignment"></a>
### -field FILE_OCTA_ALIGNMENT
<a id="FILE_32_BYTE_ALIGNMENT"></a><a id="file_32_byte_alignment"></a>
### -field FILE_32_BYTE_ALIGNMENT
<a id="FILE_64_BYTE_ALIGNMENT"></a><a id="file_64_byte_alignment"></a>
### -field FILE_64_BYTE_ALIGNMENT
<a id="FILE_128_BYTE_ALIGNMENT"></a><a id="file_128_byte_alignment"></a>
### -field FILE_128_BYTE_ALIGNMENT
<a id="FILE_256_BYTE_ALIGNMENT"></a><a id="file_256_byte_alignment"></a>
### -field FILE_256_BYTE_ALIGNMENT
<a id="FILE_512_BYTE_ALIGNMENT"></a><a id="file_512_byte_alignment"></a>
### -field FILE_512_BYTE_ALIGNMENT

</dl>
</dd>

### -field MaxPacketSizeInBytes

<dd>
<p>The absolute maximum packet size supported by the driver in bytes. This can be zero if the driver has no specific maximum packet size. This size should at least be large enough to support 10 ms buffer of any format supported by the pin. This size should also be greater or equal to MinPacketSize constraints. 
</p>
</dd>

### -field NumProcessingModeConstraints

<dd>
<p>The number of additional constraints for specific processing modes. This value can be 0.</p>
</dd>

### -field ProcessingModeConstraints

<dd>
<p>An array of 0 or more processing mode constraints. 
</p>
</dd>
</dl>

## -remarks
<p>The driver sets this variable length data structure as the value of the DEVPKEY_KsAudio_PacketSize_Constraints2 property on the PnP interface of the KS filter that has the streaming pins with the constraints. 
</p>

<p>For WaveRT drivers, this data structure describes the constraints for a WaveRT packet. Several WaveRT packets (typically 2) are concatenated to form the WaveRT buffer.</p>

<p>The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS2</b> struct is available  beginning with Windows 10, version 1607.</p>

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
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>