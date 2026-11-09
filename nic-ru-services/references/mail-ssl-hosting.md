# Mail, SSL and hosting

## Corporate mail

Check the exact mail service and domain in the hosting panel. A link labeled «Панель управления хостингом» can open the corporate mail panel if that is the active product. Use the product's current settings for MX, SPF, DKIM, DMARC and client endpoints. Verify DNS independently. Separate mailbox creation, webmail login, SMTP submission and actual delivery. Send a test message only within the user's authorized scope.

Official sources: [Corporate mail](https://www.nic.ru/catalog/mail/on-domain/), [Webmail](https://mail.nic.ru/?page_id=2).

## SSL and HTTPS

Identify where TLS terminates, such as shared hosting, a VPS reverse proxy or a CDN. Confirm the SANs, wildcard coverage, validation method and renewal responsibility. Keep private keys in the target's protected store and verify that the key matches the certificate before installation. Use the correct intermediate chain. After installation verify the public hostname with SNI, trust, expiry and redirects. A purchased or issued certificate alone does not establish that HTTPS serves it.

Official sources: [SSL help](https://www.nic.ru/help/ssl-sertifikaty-509/).

## Shared hosting and VPS/VDS

- Shared hosting: bind the selected hosting service and website, confirm plan features and provisioned access in its panel. FTP/SFTP/SSH availability depends on the product. Use backups and test the site before switching DNS in a migration.
- VPS/VDS: find the provisioned server with the exact IP or service ID and use its designated control panel. Look for console access in that specific service. If the account shows only domains, DNS or mail, record that the VPS was not found in the inspected scope. Check another contract or provider only when there is evidence linking it to the server. IP registry data can help identify the network operator but does not identify the billing account.
- SSH: check the saved alias, port and expected host key. If TCP connects and closes before the SSH greeting or key exchange, report a pre-authentication failure. Use the verified server console for read-only checks of the listener, sshd logs and relevant firewall or provider rules. An account/password test has not occurred at that stage. Do not guess alternate ports, repeatedly retry authentication or weaken host key checking.
- For a requested new account, inspect any existing account with that name first. Prefer the recipient's public key and ordinary privileges unless elevated access is authorized. Verify a fresh session identifies the requested user and read back the effective privilege groups. An account created through the console is not proof that remote SSH works.

Official sources: [Shared hosting](https://www.nic.ru/catalog/hosting/shared/), [VPS/VDS catalog](https://www.nic.ru/catalog/hosting/vds-vps/), [Linux VPS](https://www.nic.ru/catalog/hosting/linux-vps/), [Official support](https://www.nic.ru/support/).
