---
UID: NS.d3dkmddi._DXGKARG_RENDER
title: DXGKARG_RENDER
author: windows-driver-content
description: The DXGKARG_RENDER structure describes members for generating a direct memory access (DMA) buffer from a command buffer.
old-location: display\dxgkarg_render.htm
old-project: display
ms.assetid: 592553cb-21db-4c8d-b855-d9bc6a2d9579
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGKARG_RENDER, DXGKARG_RENDER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_RENDER
req.alt-loc: d3dkmddi.h
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

# DXGKARG_RENDER structure



## -description
<p>The DXGKARG_RENDER structure describes members for generating a direct memory access (DMA) buffer from a command buffer.</p>


## -syntax

````
typedef struct _DXGKARG_RENDER {
  const VOID CONST         *pCommand;
  const UINT               CommandLength;
  VOID                     *pDmaBuffer;
  UINT                     DmaSize;
  VOID                     *pDmaBufferPrivateData;
  UINT                     DmaBufferPrivateDataSize;
  DXGK_ALLOCATIONLIST      *pAllocationList;
  UINT                     AllocationListSize;
  D3DDDI_PATCHLOCATIONLIST *pPatchLocationListIn;
  UINT                     PatchLocationListInSize;
  D3DDDI_PATCHLOCATIONLIST *pPatchLocationListOut;
  UINT                     PatchLocationListOutSize;
  UINT                     MultipassOffset;
  UINT                     DmaBufferSegmentId;
  PHYSICAL_ADDRESS         DmaBufferPhysicalAddress;
} DXGKARG_RENDER;
````


## -struct-fields
<dl>

### -field pCommand

<dd>
<p>[in] A pointer to the start of the command buffer.</p>
<div class="alert"><b>Note</b>  When <a href="display.dxgkddirender">DxgkDdiRender</a> is called, the display miniport driver must validate the buffer. See Remarks in <b>DxgkDdiRender</b> for important info on how the driver should access this member.</div>
<div> </div>
</dd>

### -field CommandLength

<dd>
<p>[in] The size, in bytes, of the command buffer that <b>pCommand</b> points to.</p>
</dd>

### -field pDmaBuffer

<dd>
<p>[out] A pointer to the start of the DMA buffer, which is aligned on 4 KB. This buffer can be sent through DMA to the graphics hardware. Before the display miniport driver returns from the <a href="display.dxgkddirender">DxgkDdiRender</a> or <a href="display.dxgkddirenderkm">DxgkDdiRenderKm</a> functions, the driver should set <b>pDmaBuffer</b> to the next empty byte that follows the last byte that the driver wrote to, or the driver should point to the location (one byte beyond the buffer space) if no more space is available. This location would have been correct if the buffer was large enough.</p>
</dd>

### -field DmaSize

<dd>
<p>[in] The size, in bytes, of the DMA buffer that <b>pDmaBuffer</b> points to.</p>
</dd>

### -field pDmaBufferPrivateData

<dd>
<p>[in] A pointer to a driver-resident private data structure that is used for generating the DMA buffer that <b>pDmaBuffer</b> points to.</p>
</dd>

### -field DmaBufferPrivateDataSize

<dd>
<p>[in] The number of bytes that remain in the private data structure that <b>pDmaBufferPrivateData</b> points to for the current operation.</p>
</dd>

### -field pAllocationList

<dd>
<p>[in] An array of <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-allocationlist.md">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that the DMA buffer references. Each allocation that is referenced should appear once for optimal performance.</p>
</dd>

### -field AllocationListSize

<dd>
<p>[in] The available number of elements in the array that <b>pAllocationList</b> specifies, which represents the number of allocation specifications to send through DMA to the graphics hardware.</p>
</dd>

### -field pPatchLocationListIn

<dd>
<p>[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a> structures for the patch-location list that the user-mode display driver provides in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-rendercb.md">pfnRenderCb</a> function.</p>
<div class="alert"><b>Note</b>  When <a href="display.dxgkddirender">DxgkDdiRender</a> is called, the display miniport driver must validate the buffer. See Remarks in <b>DxgkDdiRender</b> for important info on how the driver should access this member.</div>
<div> </div>
</dd>

### -field PatchLocationListInSize

<dd>
<p>[in] The number of elements in the patch-location list that <b>pPatchLocationListIn</b> specifies.</p>
</dd>

### -field pPatchLocationListOut

<dd>
<p>[in/out] An array of <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a> structures for the patch-location list that the display miniport driver fills in. Before the driver returns from a call to its <a href="display.dxgkddirender">DxgkDdiRender</a> or <a href="display.dxgkddirenderkm">DxgkDdiRenderKm</a> functions, the driver must set <b>pPatchLocationListOut</b> to the next <b>D3DDDI_PATCHLOCATIONLIST</b> element that follows the last <b>D3DDDI_PATCHLOCATIONLIST</b> element that the driver updated.</p>
</dd>

### -field PatchLocationListOutSize

<dd>
<p>[in] The number of elements in the patch-location list that <b>pPatchLocationListOut</b> specifies. The display miniport driver is not required to fill all of the elements in the entire list; the driver must use only elements that are necessary to describe the patch location within the DMA buffer. </p>
</dd>

### -field MultipassOffset

<dd>
<p>[in/out] A UINT value that specifies the progress of the rendering operation if the display miniport driver's <a href="display.dxgkddirender">DxgkDdiRender</a> or <a href="display.dxgkddirenderkm">DxgkDdiRenderKm</a> functions must return <b>STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER</b> to obtain a new DMA buffer. When the driver's <i>DxgkDdiRender</i> or <i>DxgkDdiRenderKm</i> function is first called with a new command buffer, <b>MultipassOffset</b> is initialized to zero. Before the driver returns from the <i>DxgkDdiRender</i> or <i>DxgkDdiRenderKm</i> calls, the driver sets this member to show translation progress for subsequent <i>DxgkDdiRender</i> or <i>DxgkDdiRenderKm</i> call with the same command buffer. The DirectX graphics kernel subsystem does not change the value further. </p>
</dd>

### -field DmaBufferSegmentId

<dd>
<p>[in] The identifier of the memory segment that the DMA buffer was paged in. If the identifier is zero, the DMA buffer is not correctly paged in.</p>
</dd>

### -field DmaBufferPhysicalAddress

<dd>
<p>[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.</p>
</dd>
</dl>

## -remarks
<p>
    Support for the <a href="display.dxgkddirenderkm">DxgkDdiRenderKm</a> function is added beginning with Windows 7 for display adapters that support <a href="https://msdn.microsoft.com/03db58e6-a6d5-4b6f-ba71-d22a985f9c57">GDI Hardware Acceleration</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-allocationlist.md">DXGK_ALLOCATIONLIST</a>
</dt>
<dt>
<a href="display.dxgkddirender">DxgkDdiRender</a>
</dt>
<dt>
<a href="display.dxgkddirenderkm">DxgkDdiRenderKm</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-rendercb.md">pfnRenderCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_RENDER structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>