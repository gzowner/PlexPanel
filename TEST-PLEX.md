# PlexPanel v0.1.0 Runtime Test

Use a staging Plex account and test server before production deployment.

## 1. Installation

```bash
sudo bash install.sh
sudo /opt/plexpanel/scripts/manage.sh health
```

Expected API result:

```json
{"status":"ok","version":"0.1.0","schema":1,"database":true,"redis":true}
```

## 2. Register the server

Open **Servers → Add server** and enter:

- `http://PLEX_SERVER_IP:32400`
- An owner-account token
- TLS verification as appropriate

Confirm the test reports online and the machine identifier, Plex version, and platform appear.

## 3. Library inventory

Select **Sync libraries** and confirm all expected libraries appear. Test a normal scan first, then test metadata refresh only on a small library.

## 4. Existing shares

Select **Import shares** and confirm accepted accounts and pending invitations are imported once with the expected library keys.

## 5. New invitation

Create a test customer using a separate Plex account. Confirm the invitation arrives, selected libraries appear after acceptance, and synchronizing again updates rather than duplicates access.

## 6. Suspension and renewal

Suspend the customer and confirm library access is removed without deleting the Plex account. Renew and synchronize to restore the assigned libraries.

## 7. Sessions and history

Start playback with the test account. Confirm Stream Operations displays the session and stopping it affects only the selected playback. Pull History and confirm recent records are not duplicated.

## 8. Enforcement

Keep enforcement disabled until Plex session usernames match customer records. Then test a one-stream package with two sessions and confirm only the excess session is stopped.

## 9. Backup

```bash
sudo /opt/plexpanel/scripts/manage.sh backup
ls -lh /opt/plexpanel/backups
```
