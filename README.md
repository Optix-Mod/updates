# OptixMod OTA feeds

JSON files polled by our apps for update dialogs.

- `app.json` — dialog test app (`com.example.application2`)
- Add one file per app: `<package-or-slug>.json`

Schema:

```json
{
  "versionCode": 2,
  "versionName": "1.1",
  "changelog": "- stuff",
  "apkUrl": "https://t.me/OptixMod",
  "forceUpdate": false
}
```

Bump `versionCode` above the installed app and the dialog pops on next launch.
Set `forceUpdate: true` to block "Later".
