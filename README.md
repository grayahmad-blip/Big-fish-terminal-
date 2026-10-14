# Big Fish Trading Terminal — paper-only MVP

## What is implemented
- iPhone-responsive trading-city view with touch rotation and symbol selection
- Synthetic demo market series, manual demo ticks, and CSV historical-price import
- Paper share orders, portfolio accounting, local persistence, and CSV export
- Moving-average strategy backtest with configurable fees and slippage, next-bar execution approximation
- Manual-tick-only paper bot with a long-only crossover strategy
- Basic progressive web app manifest and offline fallback service worker

## Run locally
From this directory, run `python3 -m http.server 8000`, then visit http://localhost:8000. On an iPhone, deploy the folder to an HTTPS static host, open its HTTPS URL in Safari, and choose Share > Add to Home Screen. The service worker requires HTTPS or localhost.

## Historical CSV
Header: `symbol,date,close`; supported symbols: QQQ, SPY, NVDA, AAPL, TSLA. At least two rows per imported symbol. The application treats imported prices as user-provided and unverified. For a meaningful backtest, provide 100+ trading-day observations and independently verify adjustment methodology and rights.

## Critical limitations
This is a prototype, **not** a live brokerage, options engine, secure customer service, or production subscription platform. No live quotes, no API keys, no payment processor, no customer accounts, no server, and no scheduled execution. All user data stays in local browser storage, which can be erased. The demo prices are fabricated. Historical backtesting is simplified and can have modeling bias. There are no automated real trades. No guaranteed earnings.

## Production roadmap
1. Secure server and database with per-user authentication, rate limiting, monitoring, and backups.
2. Licensed historical and live data provider, appropriate exchange redistribution agreements, timestamps, and corporate-action adjustments.
3. Deterministic test suite and independently reviewed backtest engine with realistic order/fill model and out-of-sample walk-forward tests.
4. Server-side paper execution engine and risk controls (max loss, max position, kill switch).
5. Subscription billing and entitlement enforcement only after legal review, privacy terms, customer support, and data licensing.
6. Security assessment, beta test, and then deployment. Consult a qualified securities lawyer regarding adviser, signals, marketing, and other regulatory requirements.

Do not put provider API secrets in frontend code.
