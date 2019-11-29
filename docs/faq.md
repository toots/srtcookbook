# FAQ

## What applications support SRT?

Open source: srt-live-transmit, FFmpeg, WireShark, GStreamer

Corporate: Haivision Media Gateway, Haivision KB, Haivision Makito X

## I get error messages "tsbpd wrap period begins/ends". What does it mean?

Messages about TSBPD wrap period are informational. These are not errors.

For more information please see the [TSBPD Wrapping Period](protocol/tsbpd/latency.md#tsbpd-wrapping-period) section.

Issues on GitHub: [\#642](https://github.com/Haivision/srt/issues/642#issuecomment-539099521).

## I get error messages "No room to store incoming packet..." What does it mean?

This error message is usually related to the buffer sizes. See also \#703.

The Default receiver buffer size is approximately 96 Mbits.
You might probably need to increase the buffer size, by appending to the following URI
"srt://0.0.0.0:9999?pkt\_size=1316&mode=listener"
the following querry values can be added:
sndbuf - Send buffer size \(in bytes\)
rcvbuf - Receive buffer size \(in bytes\)

Other FFmpeg SRT URI options can be found [here](https://github.com/FFmpeg/FFmpeg/blob/master/libavformat/libsrt.c#L92).


