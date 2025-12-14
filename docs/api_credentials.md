## API Credentials for MyTelegram

### Default Credentials (Automatic)

**For MyTelegram branded builds**, test API credentials are **automatically used by default**. You don't need to obtain your own API credentials if you're just rebranding for personal use or testing.

The following test credentials are used automatically:
- **api_id**: 17349
- **api_hash**: 344583e45741c457fe1862106095a5eb

**Important**: These test credentials are limited by the Telegram API server and are intended for testing only. Your users may experience issues or internal server errors if you deploy an app using these credentials.

### Custom Credentials (Optional)

If you're building for deployment or production use, you should obtain your own **api_id** and **api_hash** for the Telegram API access.

How to obtain your **api_id** and **api_hash** is described here: [https://core.telegram.org/api/obtaining_api_id](https://core.telegram.org/api/obtaining_api_id)

To use your own credentials, provide them during the configure step:
```
configure.bat -D TDESKTOP_API_ID=YOUR_API_ID -D TDESKTOP_API_HASH=YOUR_API_HASH
```

### Disabling Test Credentials

If you want to disable the automatic test credentials and require explicit API credentials, set `TDESKTOP_API_TEST=OFF`:
```
configure.bat -D TDESKTOP_API_TEST=OFF -D TDESKTOP_API_ID=YOUR_API_ID -D TDESKTOP_API_HASH=YOUR_API_HASH
```

