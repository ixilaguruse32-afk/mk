# Aurora v4 — Institutional Order Flow Engine

**Pine Script v6 | TradingView Strategy**

---

## معرفی

Aurora v4 یک استراتژی سازمانی (Institutional Grade) برای TradingView است که بر پایه Order Flow، Footprint Data و Multi-Timeframe Confluence ساخته شده است.

## تغییرات نسبت به v3

| کد | تغییر |
|----|-------|
| V4-1 | تبدیل از `indicator()` به `strategy()` — گزارش رسمی TradingView |
| V4-2 | سیستم ورود 5-لایه Confluence با امتیاز 0-100 |
| V4-3 | Session Filter — London/NY/Crypto |
| V4-4 | ADX Trend Quality Gate — بدون ترند = بدون معامله |
| V4-5 | SL داینامیک — Shelf-Anchored + حداقل 1.5×ATR |
| V4-6 | Partial TP — 50% در 1R، بقیه در 2.5R |
| V4-7 | Break-Even بعد از TP1 + Trailing Stop |
| V4-8 | P/D Zone از timeframe بالاتر (4H) |
| V4-9 | Fresh Shelf Detection — حداکثر 2 touch |
| V4-10 | windowDelta بدون current bar (no self-reference) |
| V4-11 | Volatility Gate — بازار خواب = بدون ورود |
| V4-12 | HTF Neutral = NO TRADE |
| V4-13 | Volume Spike Confirmation |
| V4-14 | Commission 0.04% + Slippage در backtest |
| V4-15 | Dashboard کامل: SQN، Expectancy، Avg R:R |

## نیازمندی‌ها

- **TradingView Premium یا Ultimate** (برای `request.footprint()`)
- Pine Script v6

## تنظیمات پیشنهادی

| پارامتر | مقدار | توضیح |
|---------|-------|-------|
| HTF | 60m | ترند اصلی |
| MTF | 15m | تأیید |
| P/D TF | 240 (4H) | ناحیه HTF |
| ADX Min | 22 | فیلتر Chop |
| SL | 1.5×ATR | مناسب 15m |
| TP1 | 1R — 50% | لاک سود |
| TP2 | 2.5R — 100% | هدف اصلی |
| Absorption Only | ON | کیفیت بالا |
| Min Score | 55 | شلف‌های قوی |
| Max Touches | 2 | تازگی shelf |

## نصب

1. TradingView → Pine Script Editor را باز کنید
2. محتوای `aurora_v4_institutional.pine` را کپی کنید
3. **Add to Chart** بزنید
4. برای backtest: تب **Strategy Tester** را باز کنید

---

*Built by Aurora Trading Research Lab 2026*
