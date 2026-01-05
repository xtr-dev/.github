**xtr.dev** is building essential plugins for PayloadCMS and tools for peer-to-peer connectivity.
We create open-source packages that solve real development needs.

## 🔌 PayloadCMS Plugins

A comprehensive suite of PayloadCMS plugins for building production applications:

### 🔧 Core Plugins
- **[@xtr-dev/payload-automation](https://github.com/xtr-dev/payload-automation)** - Visual workflow builder with collection triggers and JSONata expressions
- **[@xtr-dev/payload-feature-flags](https://github.com/xtr-dev/payload-feature-flags)** - Feature toggles and A/B testing
- **[@xtr-dev/payload-notifications](https://github.com/xtr-dev/payload-notifications)** - Complete notification system with web push support

### 💰 Business Plugins
- **[@xtr-dev/payload-billing](https://github.com/xtr-dev/payload-billing)** - Payment provider integrations (Mollie, Stripe) with test mode
- **[@xtr-dev/payload-mailing](https://github.com/xtr-dev/payload-mailing)** - Template-based email system with scheduling

### 🛒 E-commerce Suite
- **[@xtr-dev/payload-ecommerce](https://github.com/xtr-dev/payload-ecommerce)** - Products, orders, and carts for e-commerce
- **[@xtr-dev/payload-ecommerce-plus](https://github.com/xtr-dev/payload-ecommerce-plus)** - Premium features with subscriptions and booking

## 🤝 Rondevu: WebRTC Signaling & Peer Discovery

Tags-based WebRTC signaling with HMAC authentication and durable connections.

- 🏷️ **Tags-based discovery** - Find peers by topic (e.g., `["chat", "video"]`)
- 🔐 **HMAC-SHA256 authentication** - Secure credential-based API calls
- 🔄 **Automatic reconnection** - Built-in exponential backoff and message buffering
- 💾 **Multiple backends** - Memory, SQLite, MySQL, PostgreSQL, Cloudflare Workers

### 📦 Rondevu Packages
- **[rondevu-server](https://github.com/xtr-dev/rondevu-server)** - HTTP signaling server with JSON-RPC interface
- **[rondevu-client](https://github.com/xtr-dev/rondevu-client)** - TypeScript client with durable peer connections
- **[rondevu-demo](https://github.com/xtr-dev/rondevu-demo)** - Interactive demo → [ronde.vu](https://ronde.vu)
- **[rondevu-webtorrent](https://github.com/xtr-dev/rondevu-webtorrent)** - WebTorrent peer discovery plugin using Rondevu signaling
