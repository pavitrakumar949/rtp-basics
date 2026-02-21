# RTP Basics: Media Layer in VoIP

### What is RTP?

- RTP (Real-time Transport Protocol) is used to carry audio and video in VoIP systems.
- SIP is responsible for setting up and managing the session.
- Once the session is established, RTP carries the actual voice data between endpoints.

##

### RTP and SIP Relationship

SIP handles signaling:
- Call setup (INVITE)
- Call progress (Ringing, OK)
- Call termination (BYE)

RTP handles media:
- Voice packets
- Audio stream transmission

SIP does not carry voice. RTP does.

##

### Why RTP Uses UDP

RTP typically runs over UDP because:

- Real-time communication requires low latency.
- Retransmitting lost audio packets would cause delay.
- Small packet loss is preferable to delayed speech.

In voice calls, timing is more important than perfect delivery.

##

### Basic RTP Concepts (Slightly-Advanced)

RTP includes:

- Sequence numbers (to detect lost packets)
- Timestamps (to maintain playback timing)
- SSRC (to identify the stream source)

These fields help maintain smooth audio delivery during the call.
