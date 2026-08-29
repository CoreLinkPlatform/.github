<div align="center">

# CoreLink Platform

### زیرساخت اتصال و یکپارچه‌سازی محصولات هوشمند

CoreLink یک محصول واحد با چند مرز پیاده‌سازی و انتشار است: runtime، Console، Control، قراردادهای عمومی، SDKها، مستندات و ابزارها با یک مدل maturity مشترک تکامل پیدا می‌کنند.

[Developer Documentation](https://github.com/CoreLinkPlatform/developer-docs)
· [API Contracts](https://github.com/CoreLinkPlatform/api-contracts)
· [CoreLink Console](https://github.com/CoreLinkPlatform/Console)
· [Product Website](https://corelinkplatform.ir)
· [Repository Maturity](../REPOSITORY_MATURITY.md)

</div>

---

## وضعیت فعلی محصول

CoreLink هنوز Stable v1 نیست.

- **Runtime:** Alpha / implemented foundation؛ hosted-alpha و acceptance evidence در حال تکمیل است.
- **Console:** Alpha؛ سطح tenant/customer/partner/reseller با OIDC/BFF و جریان‌های عملیاتی CoreLink-owned.
- **Control:** Alpha و Private؛ control-plane داخلی برای platform operators، tenants/devices/connections/diagnostics و خارج از قرارداد tenant-facing.
- **API Contracts:** Alpha، baseline عمومی فعلی `1.0.0-draft`.
- **TypeScript / Python SDKs:** Prerelease Alpha.
- **Java SDK / CLI / Mock Server / MCP Server:** Scaffold · Planned.

[موجودی کامل maturity](../REPOSITORY_MATURITY.md) مرجع این خلاصه است.

## CoreLink چه مسئله‌ای را حل می‌کند؟

CoreLink برای ساخت و بهره‌برداری محصولات متصل طراحی شده است. دستگاه‌ها و providerها در مرز زیرساخت جذب می‌شوند و applicationها با شناسه‌ها، قراردادها و رفتارهای CoreLink-owned کار می‌کنند.

جهت محصول شامل device lifecycle، commands، telemetry/location/state، events/webhooks، integrations، commercial controls و تجربه‌های white-label است؛ اما هر مورد فقط وقتی «پشتیبانی‌شده» محسوب می‌شود که contract، runtime، documentation و release/acceptance evidence همان maturity را تأیید کنند.

## سطوح محصول

- **Console** سطح محصول برای tenantها، مشتریان، partnerها و resellerها است و نباید provider credentials/IDs یا جزئیات زیرساخت را به قرارداد عمومی تبدیل کند.
- **Control** سطح خصوصی و privileged برای تیم CoreLink است. دسترسی tenant به‌تنهایی هیچ مجوزی برای Control ایجاد نمی‌کند.
- **Developer Platform** از `api-contracts`، مستندات نسخه‌دار، SDKها و ابزارهای پذیرفته‌شده تشکیل می‌شود.

## از کجا شروع کنیم؟

| منبع | وضعیت | کاربرد فعلی |
| --- | --- | --- |
| [Developer docs](https://github.com/CoreLinkPlatform/developer-docs) | Alpha | مستندات نسخه‌دار، quickstart و راهنماهای توسعه‌دهنده |
| [API contracts](https://github.com/CoreLinkPlatform/api-contracts) | Alpha · `1.0.0-draft` | مرز machine-readable عمومی/admin/internal و event schemas |
| [Console](https://github.com/CoreLinkPlatform/Console) | Alpha | تجربه hosted SaaS برای tenant/assets/telemetry/alerts/usage/integrations |
| [TypeScript SDK](https://github.com/CoreLinkPlatform/sdk-typescript) | Prerelease Alpha | generated client؛ هنوز Stable package نیست |
| [Python SDK](https://github.com/CoreLinkPlatform/sdk-python) | Prerelease Alpha | generated client؛ هنوز Stable package نیست |
| [Java SDK](https://github.com/CoreLinkPlatform/sdk-java) | Scaffold · Planned | package پشتیبانی‌شده ندارد |
| [CLI](https://github.com/CoreLinkPlatform/cli) | Scaffold · Planned | installable release ندارد |
| [Mock Server](https://github.com/CoreLinkPlatform/mock-server) | Scaffold · Planned | contract-driven simulation در backlog |
| [MCP Server](https://github.com/CoreLinkPlatform/mcp-server) | Scaffold · Planned | سطح MCP امن و tenant-scoped در backlog |

`Control` عمداً private است و developer/customer entry point عمومی محسوب نمی‌شود.

## قرارداد عمومی امروز

برای integration جدید، قرارداد عمومی منبع حقیقت است؛ نه ساختار provider یا جزئیات داخلی runtime.

- شناسه عمومی دستگاه: `corelink_device_id`;
- tenant scope در مسیرهای عمومی صریح است;
- authentication قرارداد عمومی: Bearer JWT;
- Command create نیازمند `Idempotency-Key` است;
- provider/connector identifiers جزئیات پیاده‌سازی‌اند.

Quickstart و referenceهای نسخه‌دار در [`developer-docs`](https://github.com/CoreLinkPlatform/developer-docs) قرار دارند.

## یک محصول، چند repository

Product hierarchy، milestone gates و تصمیم‌های cross-repository در [`product-planning`](https://github.com/CoreLinkPlatform/product-planning) مدیریت می‌شوند. هر repository implementation/evidence مرز خودش را نگه می‌دارد.

واژگان maturity مشترک: **Scaffold, Experimental, Alpha, Beta, Stable, Deprecated, Planned**.

## اعتماد، امنیت و مشارکت

- [Security Policy](../SECURITY.md)
- [Support Policy](../SUPPORT.md)
- [Contribution Guide](../CONTRIBUTING.md)
- [Release Policy](../RELEASE_POLICY.md)
- [Repository Maturity](../REPOSITORY_MATURITY.md)

---

CoreLink Platform · one product, explicit maturity, evidence before claims.
