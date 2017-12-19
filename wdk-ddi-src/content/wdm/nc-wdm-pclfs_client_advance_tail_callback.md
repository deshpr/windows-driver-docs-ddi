---
UID: NC.wdm.PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK
title: PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK
author: windows-driver-content
description: The ClfsAdvanceTailCallback function advances the base log sequence number (LSN) of the client's log.
old-location: kernel\clfsadvancetailcallback.htm
old-project: kernel
ms.assetid: e5c3ac56-9e9f-40b8-b8a8-2eb4d41bca52
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsAdvanceTailCallback
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= APC_LEVEL
req.product: Windows 10 or later.
---

# PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback



## -description
The <i>ClfsAdvanceTailCallback</i> function advances the base log sequence number (LSN) of the client's log.



## -prototype

````
PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK ClfsAdvanceTailCallback;

NTSTATUS ClfsAdvanceTailCallback(
  _In_ PLOG_FILE_OBJECT LogFile,
  _In_ PCLFS_LSN        TargetLsn,
  _In_ PVOID            ClientData
)
{ ... }
````


## -parameters

### -param LogFile [in]

A pointer to a <a href="kernel.log_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream whose tail should be advanced.


### -param TargetLsn [in]

A pointer to a <a href="kernel.clfs_lsn">CLFS_LSN</a> structure that contains the LSN that the client should advance its tail to or beyond.


### -param ClientData [in]

A pointer to client-supplied information. You specify this data in the <b>AdvanceTailCallbackData</b> member of the <a href="kernel.clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a> structure. 


## -returns
The <i>ClfsAdvanceTailCallback</i> function should return either STATUS_PENDING or an error status. A return value of STATUS_PENDING indicates that the request to move the client's log tail will be completed asynchronously. The <b>ClfsMgmtAdvanceTailCallback</b> function must not return STATUS_SUCCESS, even if it completes synchronously.


## -remarks
The <i>ClfsAdvanceTailCallback</i> function is called when CLFS management requests that the client advance its log tail.

The <i>ClfsAdvanceTailCallback</i> function must only perform a minimal amount of processing before returning. For example, the <i>ClfsAdvanceTailCallback</i> function might follow this procedure:

If the request cannot be processed, return an error status.

If the request can be processed, create and queue a work item to perform the actions that are required to move the client's tail, and then return STATUS_PENDING. For more information on queuing a worker thread, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.

When a client calls the <a href="kernel.clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a> routine to register with CLFS management, the client provides both a pointer to the <i>ClfsAdvanceTailCallback</i> function and the custom data that will be passed as a parameter to the <i>ClfsAdvanceTailCallback</i> function when this function is called.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Called at IRQL &lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a>
</dt>
<dt>
<a href="kernel.clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a>
</dt>
<dt>
<a href="kernel.clfsmgmttailadvancefailure">ClfsMgmtTailAdvanceFailure</a>
</dt>
<dt>
<a href="kernel.clfsadvancelogbase">ClfsAdvanceLogBase</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
