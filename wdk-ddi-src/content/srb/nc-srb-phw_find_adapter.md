---
UID : NC:srb.PHW_FIND_ADAPTER
title : PHW_FIND_ADAPTER
author : windows-driver-content
description : The PHW_FIND_ADAPTER prototype declares a routine that uses supplied configuration to determine whether a specific HBA is supported and, if it is, to return configuration information about that adapter.
old-location : storage\phw_find_adapter.htm
old-project : storage
ms.assetid : 265dce25-cecb-4bd1-8f5f-1646779da296
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : srb.h
req.include-header : Storport.h, Srb.h, Storport.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : (*PHW_FIND_ADAPTER)
req.alt-loc : srb.h
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
req.typenames : "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product : Windows 10 or later.
---


# PHW_FIND_ADAPTER callback function
The PHW_FIND_ADAPTER prototype declares a routine that uses supplied configuration to determine whether a specific HBA is supported and, if it is, to return configuration information about that adapter.

## Syntax

```
PHW_FIND_ADAPTER PhwFindAdapter;

ULONG PhwFindAdapter(
  PVOID DeviceExtension,
  PVOID HwContext,
  PVOID BusInformation,
  PCHAR ArgumentString,
  PPORT_CONFIGURATION_INFORMATION ConfigInfo,
  PBOOLEAN Again
)
{...}
```

## Parameters

`DeviceExtension`

Pointer to the miniport driver's per-HBA storage area.

`HwContext`

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to a context value. For a description of the meaning of this member for a SCSI miniport driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>.

`BusInformation`

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to bus-type-specific information that the OS-specific port driver has gathered. For a complete description of the meaning of this member for a SCSI miniport driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>.

`ArgumentString`

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to a null-terminated ASCII string that contains device information such as a base parameter or an interrupt level from the registry. For a complete description of the meaning of this member for a SCSI miniport driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>.

`ConfigInfo`



`Again`

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to a BOOLEAN variable that informs the port driver whether it should call this routine again. For more information about the meaning of this member for a SCSI miniport driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>.


## Return Value

The routine declared by this prototype must return one of the following status values:
<dl>
<dt><b>SP_RETURN_FOUND</b></dt>
</dl>Indicates a supported HBA was found and that the HBA-relevant configuration information was successfully determined and set in the PORT_CONFIGURATION_INFORMATION structure.
<dl>
<dt><b>SP_RETURN_ERROR</b></dt>
</dl>Indicates an HBA was found but there was error obtaining the configuration information. If possible, such an error should be logged with <a href="..\srb\nf-srb-scsiportlogerror.md">ScsiPortLogError</a>.
<dl>
<dt><b>SP_RETURN_BAD_CONFIG</b></dt>
</dl>Indicates the supplied configuration information was invalid for the adapter.
<dl>
<dt><b>SP_RETURN_NOT_FOUND</b></dt>
</dl>Indicates no supported HBA was found for the supplied configuration information.

## Remarks

This declaration is used by both SCSI and StorPort miniport drivers.

For more information about the SCSI miniport driver's version of the routine associated with this declaration, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>. 

For more information about the Storport driver's version of the routine associated with this declaration, see <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | srb.h (include Storport.h, Srb.h, Storport.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>
</dt>
<dt>
<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_FIND_ADAPTER callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>