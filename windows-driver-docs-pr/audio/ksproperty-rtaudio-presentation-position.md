---
title: KSPROPERTY\_RTAUDIO\_PRESENTATION\_POSITION
description: KSPROPERTY\_RTAUDIO\_PRESENTATION\_POSITION returns stream presentation information.
ms.assetid: 333A7432-B78A-4F61-B70D-D4F651F90AF7
keywords: ["KSPROPERTY_RTAUDIO_PRESENTATION_POSITION Audio Devices"]
topic_type:
- apiref
api_name:
- KSPROPERTY_RTAUDIO_PRESENTATION_POSITION
api_location:
- Ksmedia.h
api_type:
- HeaderDef
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# KSPROPERTY\_RTAUDIO\_PRESENTATION\_POSITION


KSPROPERTY\_RTAUDIO\_PRESENTATION\_POSITION returns stream presentation information.

### <span id="Usage_Summary_Table"></span><span id="usage_summary_table"></span><span id="USAGE_SUMMARY_TABLE"></span>Usage Summary Table

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Get</th>
<th align="left">Set</th>
<th align="left">Target</th>
<th align="left">Property descriptor type</th>
<th align="left">Property value type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Yes</p></td>
<td align="left"><p>No</p></td>
<td align="left"><p>Pin</p></td>
<td align="left"><p>[<strong>KSPROPERTY</strong>](https://msdn.microsoft.com/library/windows/hardware/ff564262)</p></td>
<td align="left"><p>[<strong>KSAUDIO_PRESENTATION_POSITION</strong>](https://msdn.microsoft.com/library/windows/hardware/ff537497)</p></td>
</tr>
</tbody>
</table>

 

The property descriptor (instance data) is a [**KSPROPERTY**](https://msdn.microsoft.com/library/windows/hardware/ff564262) structure. Before sending the request, the client loads the structure with values that indicate the preferred base address for the register.

The property value is a [**KSAUDIO\_PRESENTATION\_POSITION**](https://msdn.microsoft.com/library/windows/hardware/hh450865) structure that represents a recent presentation position in the audio data stream.

### <span id="Return_Value"></span><span id="return_value"></span><span id="RETURN_VALUE"></span>Return Value

A KSPROPERTY\_RTAUDIO\_PRESENTATION\_POSITION property request returns STATUS\_SUCCESS to indicate that it has completed successfully. Otherwise, the request returns an appropriate failure status code.

Remarks
-------

The OS may periodically get this property from the driver to retrieve recent presentation position information from the driver in order to allow upper layers to synchronize video or other activity with the audio stream.

The value returned in the u64PositionInBlocks member of [**KSAUDIO\_PRESENTATION\_POSITION**](https://msdn.microsoft.com/library/windows/hardware/hh450865) should be consistent with the packet count returned by KSPROPERTY\_RTAUDIO\_PACKETCOUNT and the driver’s interpretation of the packet number passed to SetWritePacket. In other words, the first sample of packet 0 is block 0.

This does not mean that KSPROPERTY\_RTAUDIO\_PACKETCOUNT and KSPROPERTY\_RTAUDIO\_PRESENTATION\_POSITION, if called simultaneously, would return values that refer to the same sample. KSPROPERTY\_RTAUDIO\_PACKETCOUNT returns information about the samples transferred from the WaveRT buffer to the hardware, while KSPROPERTY\_RTAUDIO\_PRESENTATION\_POSITION returns information about samples presented at the output of the system. These are two different pieces of information.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Version</p></td>
<td align="left"><p>Available in Windows 10 and later Windows operating systems.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Header</p></td>
<td align="left">Ksmedia.h</td>
</tr>
</tbody>
</table>

## <span id="see_also"></span>See also


[KSPROPSETID\_RTAudio](kspropsetid-rtaudio.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[audio\audio]:%20KSPROPERTY_RTAUDIO_PRESENTATION_POSITION%20%20RELEASE:%20%2811/22/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





