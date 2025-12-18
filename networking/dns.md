# Domain Name System

DNS (Domain Name System) is the system that translates human readable domain names into IP addresses so that computers understand where they're routing to. Without DNS, users would need to remember IP addresses for each site. As it is so tightly wrapped around IP, it remains a critical taregt in recon and phishing attacks.

---

## What DNS Does

Let's have a link like google.com. DNS would map that to 10.10.10.10. Browsers now know where to locate, and the computer now knows where data is being sent. DNS itself doesn't transfer data, it just locates.

## DNS Hierarchy
Resolution flows through multiple layers:
1. **Local Cache**: Your computer checks if it already knows the location.
2. **Recursive Resolver**: Provided by your ISP usually. Leads to following layers.
3. **Root DNS Servers**: Direct queries to the corresponding TLD (.com, .org).
4. **TLD Servers**: These handle the queries from the root DNS server.
5. **Authorative DNS Server**: Stores the actual DNS records for the domain.

## Common DNS Record Types

DNS records define how traffic should be handled.

- **A Record**: Resolves a domain into an IPv4 address.
- **AAAA Record**: Resolves into an IPv6 address.
- **CNAME Record**: Maps one domain to another domain.
- **MX Record**: Defines which mail servers receive mail for a domain.
- **TXT Record**: Stores text-based information. Domain verification, ownership proof, etc.

## DNS Caching and TTL

DNS reponses are cached locally to stop the need of recursion everytime. Each response has a **TTL (Time-To-Live)**, which is how long a response can be reused. Higher
- Lower TTL = faster changes
- Higher TTL = High performance, slower updates