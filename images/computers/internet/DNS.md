---
subjects:
  - Internet
  - Computers
status: done
---
DNS is a protocol/system that resolves human-readable addresses (domain names) into [[IP]] addresses that computers actually use.

This is the reason why you don't have to type in `142.251.12.113` every time you want to go to google. DNS resolves the domain name `google.com` automatically into that IP.

That's basically how it works foundationally.
## DNS Servers and Records

DNS servers are servers that contain DNS records.

There are multiple types of DNS records, and each type contains different types of information, here is a list of the most common ones:

- **A**: Record that maps the IPv4 address of a domain.
- **AAAA**: Record that maps the IPv6 address of a domain.
- **CNAME**: Maps one domain/subdomain into another domain, does not contain an IP address.
- **MX**: Directs mail to an email server.

## DNS Resolvers

DNS Resolvers are a service that resolves DNS addresses on your behalf. They usually contain multiple DNS servers for more efficiency, security, and resilience against failures.

Each DNS resolver has an address that clients can use to access the resolver service. An example is `1.1.1.1`, which is the IP address of Cloudflare's DNS provider that your computer can access to resolve DNS queries there.

Some examples of DNS resolvers include:

- Cloudflare (1.1.1.1)
- Google (8.8.8.8)
- Quad9 (9.9.9.9)
- OpenDNS (208.67.222.222)