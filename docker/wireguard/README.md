#### Docker Compose file contains:
- adguard - https://hub.docker.com/r/adguard/adguardhome
- unbound - https://hub.docker.com/r/mvance/unbound
- wireguard vpn - https://hub.docker.com/r/linuxserver/wireguard


#### Modifying the upstream DNS provider for Unbound
If you choose to not use Cloudflare,then modify the upstream DNS provider in `unbound.conf`.

Search for `forward-zone` and modify the IP addresses for your chosen DNS [provider](https://docs.pi-hole.net/guides/dns/upstream-dns-providers/).
```yaml
forward-zone:
        name: "."
        forward-addr: 1.1.1.1@853#cloudflare-dns.com
        forward-addr: 1.0.0.1@853#cloudflare-dns.com
        forward-addr: 2606:4700:4700::1111@853#cloudflare-dns.com
        forward-addr: 2606:4700:4700::1001@853#cloudflare-dns.com
        forward-tls-upstream: yes
```

#### Unbound static DNS entries (Optional) 
The unbound/a-records.conf defines static DNS entries for your local network using local-data (A records) and local-data-ptr (PTR record).
Location for `unbound/a-records.conf` 
```yaml
# A Record
     local-data: "raspberry.lan.  A 192.168.55.200"

# PTR Record
     local-data-ptr: "192.168.55.200 raspberry.lan."
```

#### Access Adguard 
While connected to WireGuard, navigate to http://10.2.0.100:3000 first to setup AdGuard Home before DNS query and adblocking to work.

#### Recommended configuration / Split tunnel:
Modify your wireguard client `AllowedIps` to `10.2.0.0/24` to only tunnel the web panel and DNS traffic.

### Browse the Internet without adds connected to the VPS
Android App: Wireguard for smartphone protection
