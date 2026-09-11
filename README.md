# OptixMod OTA feeds

One file per app: `updates/<package>.json` (e.g. `com.example.application2.json`).
The app builds this URL from its own package id and ignores any file whose
`package` field doesn't match — safe to drop the dialog class into any app.
`app.json` is a legacy alias, keep it in sync or delete once no old builds remain.

Schema:

```json
{
  "package": "com.example.application2",
  "versionCode": 2,
  "versionName": "1.1",
  "changelog": "- stuff",
  "apkUrl": "https://t.me/OptixMod",
  "forceUpdate": false
}
```

To ship an update: bump `versionCode` above the installed app and the dialog
pops on next launch (welcome flow re-checks 30s after first-run dismiss).
Set `forceUpdate: true` to block "Later".
