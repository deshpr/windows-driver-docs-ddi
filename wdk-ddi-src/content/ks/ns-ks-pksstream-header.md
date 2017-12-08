---
UID: NS.ks.PKSSTREAM_HEADER
title: PKSSTREAM_HEADER
author: windows-driver-content
description: The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin.
old-location: stream\ksstream_header.htm
old-project: stream
ms.assetid: c1057dcf-2988-460d-b006-f6cf16ec969e
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSSTREAM_HEADER, KSSTREAM_HEADER, *PKSSTREAM_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSSTREAM_HEADER
req.alt-loc: ks.h
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

# PKSSTREAM_HEADER structure



## -description
<p>The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin.</p>


## -syntax

````
typedef struct {
  ULONG    Size;
  ULONG    TypeSpecificFlags;
  KSTIME   PresentationTime;
  LONGLONG Duration;
  ULONG    FrameExtent;
  ULONG    DataUsed;
  PVOID    Data;
  ULONG    OptionsFlags;
  ULONG    Reserved;
} KSSTREAM_HEADER, *PKSSTREAM_HEADER;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Specifies the size, in bytes, of the structure. This should be at least <b>sizeof</b>(KSSTREAM_HEADER).</p>
</dd>

### -field TypeSpecificFlags

<dd>
<p>Specifies flags that are specific to a data format. The only flag currently supported for <i>TypeSpecificFlags</i> is KS_AM_UseNewCSSKey. This flag indicates that the hardware decoder should switch to the next queued CSS (Content Scramble System) decryption key, because the data sample that immediately follows the header is the first data sample to which a new title key applies.</p>
</dd>

### -field PresentationTime

<dd>
<p>A <a href="stream.kstime">KSTIME</a> structure that specifies the presentation time for the related stream buffer in 100-nanosecond units. For more information, see the <b>Remarks</b> section.</p>
</dd>

### -field Duration

<dd>
<p>Specifies the duration of this stream segment in the same units as the presentation time (100-nanosecond units). Set to zero when not used.</p>
</dd>

### -field FrameExtent

<dd>
<p>Specifies the size of the entire frame. The region within the frame extent is available to the filter, and the resulting valid data size for the stream operation is reflected in the <b>DataUsed</b> member.</p>
</dd>

### -field DataUsed

<dd>
<p>For a write operation, this member specifies the number of bytes within the frame that are valid when submitting a frame to a lower-level driver. The headers are not modified on a write operation; however, the <b>Information</b> member of the IO_STATUS_BLOCK structure contains the total number of bytes actually written. For a read operation, this member is not used when submitting a frame to a lower-level driver and must be set to zero. On return, this member contains the number of bytes actually filled in this frame and the <b>Information</b> member of the IO_STATUS_BLOCK structure contains the size of the list of headers actually used. Note that if the minidriver specifies KSPIN_FLAG_GENERATE_MAPPINGS in <a href="..\ks\ns-ks--kspin-descriptor-ex.md">KSPIN_DESCRIPTOR_EX</a>, when a stream pointer is advanced past a frame, <b>DataUsed</b> is set to <b>Count</b> minus <b>Remaining</b> (members of <a href="..\ks\ns-ks--ksstream-pointer-offset.md">KSSTREAM_POINTER_OFFSET</a>). If the driver does not specify this flag, the minidriver is responsible for setting <b>DataUsed</b>.</p>
</dd>

### -field Data

<dd>
<p>Specifies the virtual address of the data buffer.</p>
</dd>

### -field OptionsFlags

<dd>
<p>
  Specifies a variety of attributes of the data stream. The <b>OptionsFlags</b> member can have the values listed in the following table.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_DATADISCONTINUITY</p>
</td>
<td>
<p>Specifies that there has been a discontinuity in the data stream before the data that is contained in this packet. This implies that the filter might need to reset its internal state before processing the data. No actual data buffer need be attached.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_DURATIONVALID</p>
</td>
<td>
<p>
          Specifies that the <b>Duration</b> member of this structure is valid.
        </p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_ENDOFPHOTOSEQUENCE</p>
</td>
<td>
<p>Indicates that this frame represents the end of a photo sequence.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM</p>
</td>
<td>
<p>Indicates that this frame represents the end of the data stream.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_FLUSHONPAUSE</p>
</td>
<td>
<p>If the stream is paused, this buffer should be flushed. This flag is used, for example, by live data sources, where a pause renders the current data stale.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_FRAMEINFO</p>
</td>
<td>
<p>Indicates that there is a KS_FRAME_INFO structure following KSSTREAM_HEADER.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_LOOPEDDATA</p>
</td>
<td>
<p>This data buffer is the start of looped data. The driver should loop on this data until explicitly stopped.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_METADATA</p>
</td>
<td>
<p>Indicates that there is a KSSTREAM_METADATA_INFO that follows KS_FRAME_INFO after the KSSTREAM_HEADER. 
		  This flag is present only if KSPROPERTY_CAMERACONTROL_EXTENDED_METADATA is supported.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_PREROLL</p>
</td>
<td>
<p>The data in this buffer is used to prime the device state. This is a stream-specific option.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_SPLICEPOINT</p>
</td>
<td>
<p>The data stream is at a natural point for splicing. A client uses this, for example, when sending data that uses inter-frame compression, such as MPEG video, to indicate that it is safe to splice at this point.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_TIMEDISCONTINUITY</p>
</td>
<td>
<p>There is a discontinuity in the data stream after this packet. This flag can be used for positional oriented interfaces to indicate an end of stream data. No actual data buffer need be attached.</p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_TIMEVALID</p>
</td>
<td>
<p>
          Specifies that the <b>PresentationTime</b> member of this structure is valid. Indicates that this buffer has a valid timestamp associated with it.
        </p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_TYPECHANGED</p>
</td>
<td>
<p>
          Signifies that the data format for this stream has changed. If this flag is set, the <b>Data</b> member contains a <a href="stream.ksdataformat">KSDATAFORMAT</a> structure that contains the new format. This flag is valid only for streams that have previously negotiated dynamic type changing. For a write operation, include the new data format in place of a media sample. If the media-specific extension size is modified, this header must be the last header in a list of headers for the given stream request. During a read request, any further I/O remains pending until the new format is retrieved through KSPROPERTY_CONNECTION_DATAFORMAT. For a write operation, the header must not be extended, and must be the only header in the write operation.
        </p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_VRAM_DATA_TRANSFER</p>
</td>
<td>
<p>
          Specifies that the stream header's <i>Data</i> member points to a structure of type <a href="stream.vram_surface_info">VRAM_SURFACE_INFO</a>. The system-supplied KS proxy module sets this flag to indicate that it is <a href="https://msdn.microsoft.com/e3ab3a10-42af-488f-9b13-d2c6d5aac615">capturing directly to VRAM</a>.
        </p>
</td>
</tr>
<tr>
<td>
<p>KSSTREAM_HEADER_OPTIONSF_BUFFEREDTRANSFER</p>
</td>
<td>
<p>
          Specifies that the <i>Data</i> member of KSSTREAM_HEADER contains a kernel-mode copy of the original buffer. Ksproxy sets this flag for small data transfers during WVDDM (Windows Vista Display Driver Model) capture. If this flag is not set, KS uses direct I/O into the <i>Data</i> buffer.
        </p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field Reserved

<dd>
<p>Reserved for internal use.</p>
</dd>
</dl>

## -remarks
<p>This structure can be followed in memory by additional information specific to the type of data in the data packet.</p>

<p>The presentation time is typically in 100-nanosecond units; however, the standard format of this time is based on the data format. You can normalize presentation time by using as a scaling fractional the KSSTREAM_HEADER.PresentationTime.Numerator divided by the KSSTREAM_HEADER.PresentationTime.Denominator .</p>

<p>A conversion should use the numerator first, then the denominator, in order to reduce rounding errors. For example, an audio stream might present the current time as a byte offset in the data stream:</p>

<p>On an IOCTL_KS_READ_STREAM, portions of the stream header are filled in by the call. Each KSSTREAM_HEADER.DataUsed element contains the actual number of bytes read, which is less than or equal to each KSSTREAM_HEADER.FrameExtent. The pIrp-&gt;IoStatus.Information element contains the total size of the header data to return, which is at least one <b>sizeof</b>(KSSTREAM_HEADER).</p>

<p>On an IOCTL_KS_WRITE_STREAM, the member elements must be initialized, and each KSSTREAM_HEADER.DataUsed element contains the number of bytes to write. The actual number of total bytes written is returned in pIrp-&gt;IoStatus.Information. This is less than or equal to the total of all KSSTREAM_HEADER.DataUsed elements in the headers.</p>

<p>If you are using the <a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a> interface to obtain timestamps to place in the <b>PresentationTime</b> member of KSSTREAM_HEADER, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a> for more information.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksdataformat">KSDATAFORMAT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSSTREAM_HEADER structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>