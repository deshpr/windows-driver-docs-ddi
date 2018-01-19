---
UID : NN:dmusicks.IAllocatorMXF
title : IAllocatorMXF
author : windows-driver-content
description : The IAllocatorMXF interface manages buffer storage for DirectMusic streams.
old-location : audio\iallocatormxf.htm
old-project : audio
ms.assetid : 4ed81d77-e140-4633-8582-d21170ecc645
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ISynthSinkDMus, ISynthSinkDMus::SyncToMaster, SyncToMaster
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : dmusicks.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IAllocatorMXF
req.alt-loc : dmusicks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DMUS_STREAM_TYPE
---

# IAllocatorMXF interface

The <code>IAllocatorMXF</code> interface manages buffer storage for DirectMusic streams. The DMus port driver implements this interface and exposes it to the DMus miniport driver. The DMus port driver creates an <code>IAllocatorMXF</code> object and passes a pointer to this object to the DMus miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a> method. <code>IAllocatorMXF</code> inherits from the <a href="..\dmusicks\nn-dmusicks-imxf.md">IMXF</a> interface.

<code>IAllocatorMXF</code> is the interface through which the miniport driver communicates with the port driver's internal <a href="https://msdn.microsoft.com/8f263288-2f79-4f1d-b740-d78d40f47b32">allocator</a>, which allocates and manages the reuse of a pool of <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structures. Each structure can contain a time-stamped MIDI event.

The allocator also abstracts the allocation of the additional memory that is needed to store large events. The <b>uData</b> member of DMUS_KERNEL_EVENT is a union that is the size of a pointer: four bytes on a 32-bit system and eight bytes on a 64-bit system. If the data is small enough to fit in that space, then <b>uData</b> will contain the actual MIDI data. If the data for that event is larger than the 4- or 8-byte pointer, however, the <b>cbEvent</b> member indicates this fact and <b>uData</b> contains a pointer to a buffer instead of the actual MIDI data. This buffer is managed by the allocator and is a constant size for any port-driver implementation.

## Methods

<p>The <b>IAllocatorMXF</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [dmusicks.IAllocatorMXF.GetBuffer](nf-dmusicks-iallocatormxf-getbuffer.md) | The GetBuffer method allocates a buffer for long MIDI events. |
| [dmusicks.IAllocatorMXF.GetBufferSize](nf-dmusicks-iallocatormxf-getbuffersize.md) | The GetBufferSize method gets the buffer size from the allocator. |
| [dmusicks.IAllocatorMXF.GetMessage](nf-dmusicks-iallocatormxf-getmessage.md) | The GetMessage method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse DMUS_KERNEL_EVENT structures. |
| [dmusicks.IAllocatorMXF.PutBuffer](nf-dmusicks-iallocatormxf-putbuffer.md) | This method is not currently used by the miniport driver. The PutBuffer method passes a buffer to the allocator, but this occurs automatically when IMXF::PutMessage is called anyway. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | dmusicks.h |
| **DLL** |  |