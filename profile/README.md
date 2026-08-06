<div align="center">

# CoreLink Platform

### زیرساخت اتصال و یکپارچه‌سازی محصولات هوشمند

CoreLink یک محصول واحد با چند مرز پیاده‌سازی است: قراردادهای عمومی، runtime،
SDKها، مستندات و ابزارها با یک مدل maturity مشترک تکامل پیدا می‌کنند.

[Developer Documentation](https://github.com/CoreLinkPlatform/developer-docs)
·
[API Contracts](https://github.com/CoreLinkPlatform/api-contracts)
·
[Product Website](https://corelinkplatform.ir)
·
[Repository Maturity](../REPOSITORY_MATURITY.md)

</div>

---

## وضعیت فعلی محصول

CoreLink هنوز یک انتشار Stable v1 نیست. مرز عمومی فعلی به‌صورت شفاف محدود است:

- **API Contracts:** Alpha، با baseline فعلی `1.0.0-draft` برای Device و
  Command و canonical event envelope.
- **TypeScript SDK:** Prerelease Alpha.
- **Python SDK:** Prerelease Alpha.
- **Java SDK / CLI / Mock Server / MCP Server:** Scaffold · Planned.
- **Core runtime:** foundation پیاده‌سازی‌شده دارد، اما تکمیل engineering
  foundation به‌تنهایی معادل پذیرش محصول یا انتشار Stable نیست.

[موجودی کامل maturity ریپوها](../REPOSITORY_MATURITY.md) مرجع این خلاصه است.

## CoreLink چه مسئله‌ای را حل می‌کند؟

CoreLink برای ساخت محصولات متصل طراحی شده است: دستگاه و integration در مرز
زیرساخت جذب می‌شوند و applicationها با شناسه‌ها، قراردادها و رفتارهای
CoreLink-owned کار می‌کنند.

جهت محصول شامل device lifecycle، commands، telemetry/state، events،
integrations و تجربه‌های white-label است؛ اما هر مورد فقط وقتی «قابلیت پشتیبانی
شده» محسوب می‌شود که contract، runtime، مستندات و release evidence همان maturity
را تأیید کنند.

## از کجا شروع کنیم؟

| منبع | وضعیت | کاربرد فعلی |
| --- | --- | --- |
| [Developer docs](https://github.com/CoreLinkPlatform/developer-docs) | Alpha | مستندات نسخه‌دار و quickstart مبتنی بر contract |
| [API contracts](https://github.com/CoreLinkPlatform/api-contracts) | Alpha · `1.0.0-draft` | مرز عمومی Device + Command و event envelope |
| [TypeScript SDK](https://github.com/CoreLinkPlatform/sdk-typescript) | Prerelease Alpha | کلاینت generated؛ هنوز release پایدار نیست |
| [Python SDK](https://github.com/CoreLinkPlatform/sdk-python) | Prerelease Alpha | کلاینت generated؛ هنوز release پایدار نیست |
| [Java SDK](https://github.com/CoreLinkPlatform/sdk-java) | Scaffold · Planned | مسیر توسعه آینده؛ package پشتیبانی‌شده ندارد |
| [CLI](https://github.com/CoreLinkPlatform/cli) | Scaffold · Planned | ابزار برنامه‌ریزی‌شده؛ installable release ندارد |
| [Mock Server](https://github.com/CoreLinkPlatform/mock-server) | Scaffold · Planned | شبیه‌ساز برنامه‌ریزی‌شده |
| [MCP Server](https://github.com/CoreLinkPlatform/mcp-server) | Scaffold · Planned | سطح agent/MCP برنامه‌ریزی‌شده |

## قرارداد عمومی امروز

برای integration جدید، قرارداد عمومی منبع حقیقت است؛ نه ساختار provider یا
جزئیات داخلی runtime.

- شناسه عمومی دستگاه: `corelink_device_id`;
- tenant scope در مسیرهای عمومی صریح است;
- authentication فعلی قرارداد عمومی: Bearer JWT;
- Command create نیازمند `Idempotency-Key` است;
- provider/connector identifiers جزئیات پیاده‌سازی‌اند.

Quickstart و referenceهای نسخه‌دار در
[`developer-docs`](https://github.com/CoreLinkPlatform/developer-docs) قرار
دارند.

## یک محصول، چند repository

Product hierarchy، milestone gates و تصمیم‌های cross-repository در
[`product-planning`](https://github.com/CoreLinkPlatform/product-planning)
مدیریت می‌شوند. هر repository فقط implementation/evidence مرز خودش را نگه
می‌دارد.

وضعیت یک repository را از public بودن، تعداد فایل‌ها یا وجود یک scaffold نتیجه
نمی‌گیریم. واژگان مشترک maturity عبارت‌اند از **Scaffold, Experimental, Alpha,
Beta, Stable, Deprecated, Planned**.

## اعتماد، امنیت و مشارکت

- آسیب‌پذیری امنیتی را طبق [Security Policy](../SECURITY.md) گزارش کنید.
- تغییرات کد و مستندات باید [Contribution Guide](../CONTRIBUTING.md) را رعایت کنند.
- Issueهای اجرایی از [organization Issue forms](../ISSUE_TEMPLATE/) استفاده
  می‌کنند و به Product Epic مربوط لینک می‌شوند.
- وضعیت محصول یا package را قبل از استفاده production از repository مالک و
  [maturity inventory](../REPOSITORY_MATURITY.md) بررسی کنید.

---

CoreLink Platform · one product, explicit maturity, evidence before claims.
