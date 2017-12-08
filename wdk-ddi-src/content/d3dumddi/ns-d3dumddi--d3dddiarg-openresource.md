---
UID: NS.d3dumddi._D3DDDIARG_OPENRESOURCE
title: D3DDDIARG_OPENRESOURCE
author: windows-driver-content
description: The D3DDDIARG_OPENRESOURCE structure contains information for opening a shared resource.
old-location: display\d3dddiarg_openresource.htm
old-project: display
ms.assetid: eb1b7317-2e54-4e61-a3e5-b5ac0c09064e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDIARG_OPENRESOURCE, D3DDDIARG_OPENRESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_OPENRESOURCE
req.alt-loc: d3dumddi.h
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

# D3DDDIARG_OPENRESOURCE structure



## -description
<p>The D3DDDIARG_OPENRESOURCE structure contains information for opening a shared resource.</p>


## -syntax

````
typedef struct _D3DDDIARG_OPENRESOURCE {
  UINT                      NumAllocations;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7)
  union {
    D3DDDI_OPENALLOCATIONINFO  *pOpenAllocationInfo;
    D3DDDI_OPENALLOCATIONINFO2 *pOpenAllocationInfo2;
  };
#else 
  D3DDDI_OPENALLOCATIONINFO *pOpenAllocationInfo;
#endif 
  D3DKMT_HANDLE             hKMResource;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  HANDLE                    hResource;
  D3DDDI_ROTATION           Rotation;
  D3DDDI_OPENRESOURCEFLAGS  Flags;
} D3DDDIARG_OPENRESOURCE;
````


## -struct-fields
<dl>

### -field NumAllocations

<dd>
<p>[in] The number of elements in the array that is specified by <b>pOpenAllocationInfo</b>. <b>NumAllocations</b> represents the number of allocations to open.</p>
</dd>

### -field pOpenAllocationInfo

<dd>
<p>[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.</p>
</dd>

### -field pOpenAllocationInfo2

<dd>
<p>This member is reserved and should be set to zero.</p>
<p>This member is available beginning with Windows 7.</p>
</dd>

### -field pOpenAllocationInfo

<dd>
<p>[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.</p>
</dd>

### -field hKMResource

<dd>
<p>[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations. </p>
<p>This kernel-mode handle represents an existing shared resource that was previously created through a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a> function. </p>
</dd>

### -field pPrivateDriverData

<dd>
<p>[in] A pointer to private data that was passed to the display miniport driver when the resource was created. This data is per resource and not per allocation like the private data in each allocation's <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a> structure. </p>
</dd>

### -field PrivateDriverDataSize

<dd>
<p>[in] The size, in bytes, of the private data that is pointed to by <b>pPrivateDriverData</b>.</p>
</dd>

### -field hResource

<dd>
<p>[in/out] A handle to the resource that is associated with the allocations. </p>
<p>The user-mode display driver should save this handle and use it to identify the resource anytime that the driver calls back into the Microsoft Direct3D runtime. The user-mode display driver should generate a unique handle and pass it back to the Direct3D runtime. The Direct3D runtime uses this handle in driver calls to identify the resource.</p>
</dd>

### -field Rotation

<dd>
<p>[in] A <a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-rotation.md">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the shared primary resource. </p>
<p>When the primary resource is used with a full-screen device and is rotated, the driver might be required to create interim allocations to handle the full-screen device. The <b>Fullscreen</b> bitfield flag is set in the <b>Flags</b> member to indicate that the primary resource is used with a full-screen device.</p>
</dd>

### -field Flags

<dd>
<p>[in] A <a href="..\d3dumddi\ns-d3dumddi--d3dddi-openresourceflags.md">D3DDDI_OPENRESOURCEFLAGS</a> structure that identifies the type of resource to open. </p>
</dd>
</dl>

## -remarks
<p>The <b>Primary</b> and <b>SharedResource</b> bit-field flags are set in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt--d3dddiarg-createresource.md">D3DDDIARG_CREATERESOURCE</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a> function to create a shared primary resource.</p>

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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddi-openresourceflags.md">D3DDDI_OPENRESOURCEFLAGS</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-rotation.md">D3DDDI_ROTATION</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddiarg-createresource.md">D3DDDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-openresource.md">OpenResource</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_OPENRESOURCE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>