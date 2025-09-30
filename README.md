# Pi-hole Whitelist

A curated whitelist of domains for Pi-hole that are commonly blocked by aggressive blocklists but are needed for legitimate functionality.

## 📋 What's Included

This whitelist contains domains for:
- **Microsoft Services & Windows** - Windows Update, Office 365, Microsoft Store
- **Apple Services** - iCloud, App Store, iTunes
- **Google Services** - Android, Play Store, Google APIs
- **Marketing Services** - Fixes email links not working anymore


## 🚀 Quick Start

### Method 1: Import via URL (Recommended)

1. Copy the raw URL of the whitelist:
   ```
   https://raw.githubusercontent.com/duncanplatt/dnsblock-whitelist/main/whitelist.txt
   ```

2. In Pi-hole admin interface:
   - Go to **Group Management** → **Adlists**
   - Or use the command line (see below)

### Method 2: Command Line Import

SSH into your Pi-hole and run:

```bash
# Download the whitelist
wget https://raw.githubusercontent.com/duncanplatt/dnsblock-whitelist/main/whitelist.txt

# Add all domains to whitelist (removes comments and blank lines)
grep -v '^#' whitelist.txt | grep -v '^$' | while read domain; do
    pihole -w $domain
done
```

### Method 3: Manual Addition

1. Go to Pi-hole Admin Console
2. Navigate to **Whitelist**
3. Add domains one by one from `whitelist.txt`

## 📝 Customization

Feel free to:
- Fork this repository
- Remove domains you don't need
- Add your own commonly blocked domains
- Submit pull requests for domains that should be included

## ⚠️ Important Notes

- This whitelist is designed to work with **aggressive blocklists**
- Not all domains may be necessary for your setup
- Review the list and remove services you don't use
- Whitelisting reduces privacy protection - use judiciously

## 🔄 Updates

This list is maintained and updated regularly. Star/watch this repo to get notified of updates.

## 🤝 Contributing

Found a domain that's commonly blocked but needed? Submit a PR or open an issue!

Please include:
- The domain name
- Why it's needed (what breaks without it)
- Category it belongs to

## 📜 License

MIT License - See [LICENSE.md](LICENSE.md) for details