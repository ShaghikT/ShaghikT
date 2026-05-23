# Shaghik Torosian

Junior software developer based in Yerevan. Building real products in .NET while learning the craft.

---

## 🚀 Current project — Frameet

**Live:** [frameet-hkdbhffnckf0cdgq.westeurope-01.azurewebsites.net](https://frameet-hkdbhffnckf0cdgq.westeurope-01.azurewebsites.net)

A photographer marketplace for Armenia. Three user types, real bookings, payment integration in progress, deployed to Azure with auto-migrations on startup.

I built Frameet because I've lived the problem — finding the right photographer in Armenia is unreasonably hard, and so is being a photographer trying to get found. It started as the platform I wished existed, and turned into my main learning project: one ~2-hour session per day, manual coding with explained rationale.

**Stack:** ASP.NET Core 10 · Razor Pages · Entity Framework Core 10 · SQL Server (Azure SQL serverless prod / LocalDB dev) · ASP.NET Core Identity · Cloudinary · SendGrid · Stripe (in progress) · Tailwind CSS v4 · GitHub Actions CI/CD · Azure App Service

**Shipped, and continuing to ship:**

- 🔐 Auth for 3 user types (Client / Photographer / Studio) with custom claims factory
- 👤 Photographer profiles with slug-based public URLs, M:M taxonomy tagging, portfolio + albums via Cloudinary
- 🏢 Studio B2B profiles with space + equipment listings
- ⭐ Bidirectional reviews (client→photographer, photographer→studio), aggregate ratings, check constraints
- 📅 Availability calendar, favorites, booking + studio rental flows with status state machines
- 💬 In-app messaging with conversation anchoring (XOR-constrained to booking OR rental OR general)
- 📧 SendGrid transactional emails, `BackgroundService` sweeper for auto-completion
- 🎫 Admin event management with cover photo upload + custom modal-confirmed delete
- 🎨 SEO-ready: JSON-LD structured data (Person, AggregateRating, LocalBusiness, Organization), OG/Twitter cards
- 🚀 Auto-migration on Azure startup, GitHub Actions CI/CD, environment-separated config

**Repo is private** to protect launch positioning and avoid exposing API credentials in commit history. Happy to walk through the codebase during interviews.

---

## 🧠 Things I've learned the hard way (and now do right)

- EF Core M:M needs `ICollection<>` on both sides OR explicit `HasMany().WithMany()` — silently generates a 1:M shadow FK otherwise
- SQL Server rejects multiple cascade paths — solved with `DeleteBehavior.NoAction` + manual app-code nulling
- `[Flags]` enums can't bind via ASP.NET Core model binding natively — use `List<T>` + server-side OR-aggregate
- Identity claims live in the auth cookie; updating user data requires sign-out/in or `RefreshSignInAsync`
- Azure SQL serverless needs `EnableRetryOnFailure(5, 30s)` + 60s connection timeout for cold starts
- Singleton Cloudinary client + Scoped service wrapper avoids the captive dependency rule
- One commit per session, reviewed migration output before every `database update`

---

## 📚 Currently learning

- **Python + Machine Learning** — TUMO Labs GSL program. Expanding beyond the .NET stack into the ML ecosystem that powers Frameet's planned Shot Suggester (auto-tagging portfolios by style, matching clients to photographers by visual preference).
- Going deeper on EF Core query optimization, async patterns, and clean architecture as Frameet grows.

---

## 🛠 Working with

C# 13 · LINQ · async/await · Razor Pages tag helpers · Fluent API · ASP.NET Identity · Tailwind utility-first · vanilla JS (no framework) · Cloudinary SDK · Stripe.net · SendGrid · GitHub Actions · Azure App Service · Azure SQL · VS Code + Visual Studio 2022

---

## 📫 Contact

- Email: [shaghiktorosian@gmail.com](mailto:shaghiktorosian@gmail.com)
- Location: Yerevan, Armenia
- Open to: junior .NET roles, remote or hybrid

---

*Frameet is my full-time learning project. Real product, real users coming, real software development experience. Focused on shipping over stacking tutorial projects.*
