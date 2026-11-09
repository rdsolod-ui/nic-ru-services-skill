# Account, domains and DNS

## Choose the right account and operation

- Open the [account](https://www.nic.ru/my-account), then check the selected contract and its active services. Compare the exact domain or service ID. The contract selector can show a different account from the one in the current request.
- Account sign-in, hosting control and webmail have separate entry points. Use the relevant one and prefer the existing authenticated session. If a login attempt fails, distinguish timeout, rejected credentials and an interactive challenge before deciding whether another attempt is justified.
- For registration and renewal, verify the exact domain, extension, term, price, expiration and any auto-renewal state. An order, payment and active renewal are separate states.
- Separate changing registrar, moving between contracts and changing the domain administrator. Verify the extension-specific procedure, transfer restrictions and exact recipient. Preserve the existing NS and mail configuration where the operation permits it. Handle transfer codes as credentials.

Official sources: [Account](https://www.nic.ru/my-account), [Account security](https://www.nic.ru/info/increased-security/), [Transfer to Руцентр](https://www.nic.ru/info/services/domain-transfer/to-ru-center/), [Move between contracts](https://www.nic.ru/info/services/domain-transfer/to-other-account/), [Domain monitoring](https://www.nic.ru/help/monitoring-domenov_4451.html).

## Separate delegation and records

- For NS changes, identify the current parent delegation and confirm the replacement DNS provider has a complete zone. Check DNSSEC and DS coordination, and glue when applicable. Capture old NS/DS values for recovery.
- For record changes, discover the delegated nameservers and edit at the authoritative provider. If the zone is on NIC.RU DNS hosting, verify the zone and service in the account before opening the record editor. A purchased DNS service can exist before delegation points to it.
- Capture the affected RRsets, TTLs and priorities. Resolve UI conventions for apex, relative labels and trailing dots before saving. Preserve unrelated values. Check CNAME conflicts, avoid duplicate SPF policies and use the mail provider's exact DKIM selector and value.
- Query each authoritative server for the changed RRset, then use a recursive resolver to assess cache behavior. A stale recursive answer during TTL expiry and a wrong authoritative answer need different fixes.

Example with reserved domain names:

```sh
dig +trace example.com NS
dig @ns1.example.net example.com SOA +norecurse
dig @ns1.example.net www.example.com A +norecurse
dig @ns1.example.net example.com MX +norecurse
```

On Windows, use `Resolve-DnsName -Name example.com -Type NS -DnsOnly` and `Resolve-DnsName -Name www.example.com -Type A -Server ns1.example.net -DnsOnly -NoRecursion` where available.

Official sources: [DNS hosting](https://www.nic.ru/catalog/for-domain-use/dns-hosting/), [DNS Secondary](https://www.nic.ru/catalog/for-domain-use/dns-secondary/), [DNS FAQ](https://www.nic.ru/help/chasto-zadavaemye-voprosy-o-dns_7967.html).
