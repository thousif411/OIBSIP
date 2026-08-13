# Task 8 - Capture Network Traffic with Wireshark

## Objective

Capture and analyse live network traffic using Wireshark. The task focuses on HTTP, DNS, TCP traffic, TCP three-way handshakes, and identifying security risks from unencrypted HTTP communication.

## Tools Used

- Kali Linux
- Wireshark 4.6.6
- Local test network / VirtualBox network interface
- eth0

## Capture

A live traffic capture was performed on the `eth0` interface for at least two minutes.

The capture was saved as:

`wireshark_capture.pcap`

## HTTP Traffic Analysis

Display filter used:

`http`

The capture contained an HTTP GET request:

`GET / HTTP/1.1`

An HTTP response with status `200 OK` was also observed.

Because HTTP is unencrypted, information in the request can potentially be read by someone who can observe the network traffic.

## DNS Traffic Analysis

Display filter used:

`dns`

DNS packets were observed containing DNS queries and responses.

## TCP Three-Way Handshake

Display filter used:

`tcp`

A complete TCP connection establishment was observed:

1. SYN - The client requests a TCP connection.
2. SYN-ACK - The server acknowledges the request and sends its own synchronization information.
3. ACK - The client acknowledges the server.

This establishes the TCP connection before application data is exchanged.

## Unencrypted HTTP Data

The HTTP GET request was visible in the packet capture.

This demonstrates why plain HTTP is unsafe for sensitive communication. An observer who can capture the traffic may be able to read information transmitted through HTTP.

## Why HTTP Is Dangerous

HTTP sends application data without encryption. This means an attacker who can intercept network traffic may be able to read or modify the communication.

Sensitive information such as login credentials, session information, or other private data should not be transmitted over plain HTTP.

## How HTTPS Protects Traffic

HTTPS uses TLS encryption to protect HTTP communication.

TLS helps provide:

- Confidentiality - prevents others from simply reading the transmitted data.
- Integrity - helps detect unauthorized modification of data.
- Authentication - helps verify the identity of the server through digital certificates.

## Security Observations

- Plain HTTP traffic can expose application-layer information.
- DNS queries can reveal which domains a system is attempting to access.
- TCP handshakes provide useful information about network connections.
- Packet capture and analysis can help a SOC analyst investigate network activity.

## Glossary

### Packet

A packet is a small unit of data transmitted across a network.

### Protocol

A protocol is a set of rules that devices use to communicate with each other.

### Port

A port is a numbered communication endpoint used to identify a particular network service.

### Payload

A payload is the actual data carried inside a network packet, separate from the information used to deliver it.

### Handshake

A handshake is a sequence of messages used by two systems to establish communication. In TCP, the connection begins with SYN, SYN-ACK, and ACK.

## Evidence

Screenshots are stored in the `screenshots` directory:

- `http_filter.png`
- `dns_filter.png`
- `tcp_handshake.png`
- `http_unencrypted_data.png`

The complete packet capture is included as `wireshark_capture.pcap`.

## Ethics

This capture was performed only on a network/environment under my control and for educational purposes. Network traffic should not be captured on public, university, or other networks without explicit authorization.
