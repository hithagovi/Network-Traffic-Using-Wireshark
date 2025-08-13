
# Task 5 – Capture and Analyze Network Traffic Using Wireshark

## Objective
Capture live network packets and identify basic protocols and traffic types using Wireshark.

## Tools Used
- **Wireshark** (Linux, interface: `eth0` in promiscuous mode)

## Steps Taken
1. Launched Wireshark and selected the `eth0` interface in promiscuous mode.
2. Started capture and generated traffic by visiting websites.
3. Stopped capture after ~1 minute.
4. Applied protocol filters (`dns`, `tcp`, `http`) to analyze specific traffic types.
5. Saved the capture as **capture_wireshark.pcap**.

## Protocols Identified

| Protocol | Purpose | Example Packet Info | Source → Destination |
|----------|---------|---------------------|----------------------|
| **DNS**  | Resolves domain names to IP addresses | Standard query A `google.com` | `10.0.2.15 → 10.0.2.3` |
| **TCP**  | Reliable transport protocol | SYN to port 80 | `fd17:625c:... → 2600:1408:...` |
| **HTTP** | Web content transfer | `GET / HTTP/1.1` and `200 OK` | `10.0.2.15 → 23.215.0.136` |

## Findings
- Multiple DNS queries and responses for domains like `google.com` and `example.com` were captured.
- TCP handshake attempts (SYN, ACK) and resets (RST) were observed, indicating both successful and failed connection attempts.
- HTTP GET requests and 200 OK responses confirmed successful webpage retrieval.

## Packet Count
- **Total captured packets:** 105

## File Delivered
- **capture_wireshark.pcap** — contains the full packet data for analysis.
