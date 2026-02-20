# RTP Basics: Media Transport in VoIP

## What is RTP?

RTP (Real-time Transport Protocol) is used to carry audio and video media in VoIP systems.

SIP establishes the session.
RTP transports the actual encoded media once the session is active.

RTP typically runs over UDP.

---

## Why RTP Uses UDP

RTP prioritizes low latency over reliability.

UDP is used because:

- There is no connection setup delay.
- No retransmission delay.
- Real-time communication is more important than perfect delivery.

In voice communication, small packet loss is acceptable.
Delays caused by retransmission are not.

---

## Core RTP Concepts

### Sequence Number
Each RTP packet includes a sequence number.

Used to:
- Detect packet loss
- Detect out-of-order packets

### Timestamp
Indicates the sampling instant of the media.

Used to:
- Maintain correct playback timing
- Handle jitter

### SSRC (Synchronization Source)
Uniquely identifies the RTP stream source.

Important when multiple media streams exist (e.g., conference calls).

---

## Packet Loss and Jitter

Packet Loss:
Missing RTP packets may cause small audio glitches.

Jitter:
Variation in packet arrival timing.
Handled using a jitter buffer on the receiver side.

---

## Relationship Between SIP and RTP

SIP negotiates the session parameters (often using SDP).

After session establishment:
RTP flows directly between endpoints.

SIP handles signaling.
RTP handles media.
