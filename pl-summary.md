# GMT QuoteAgent — P&L Summary
# Evidence of business financial activity
# Hackathon Period: June 22 – August 17, 2026

## Financial Summary

| Item | Jun 2026 | Jul 2026 (proj.) | Aug 2026 (proj.) | TOTAL |
|------|----------|-----------------|-----------------|-------|
| **REVENUE** | | | | |
| Setup Fee — Client 1 | $0 | $400 | $0 | $400 |
| Setup Fee — Client 2 | $0 | $400 | $0 | $400 |
| Subscription — Client 1 | $0 | $0 | $100 | $100 |
| Subscription — Client 2 | $0 | $0 | $100 | $100 |
| **TOTAL REVENUE** | **$0** | **$800** | **$200** | **$1,000** |
| | | | | |
| **COGS** | | | | |
| Gemini API (Google Cloud) | $5 | $15 | $20 | $40 |
| Claude API (Anthropic) | $3 | $8 | $10 | $21 |
| Twilio WhatsApp API | $0 | $5 | $8 | $13 |
| **TOTAL COGS** | **$8** | **$28** | **$38** | **$74** |
| | | | | |
| **GROSS PROFIT** | **-$8** | **$772** | **$162** | **$926** |
| Gross Margin % | N/A | 96.5% | 81.0% | 92.6% |
| | | | | |
| **OPEX** | | | | |
| Hosting (own hardware) | $0 | $0 | $0 | $0 |
| N8N + NocoDB (open source) | $0 | $0 | $0 | $0 |
| Domain & SSL | $0 | $12 | $0 | $12 |
| Marketing | $0 | $0 | $0 | $0 |
| **TOTAL OPEX** | **$0** | **$12** | **$0** | **$12** |
| | | | | |
| **NET PROFIT / (LOSS)** | **-$8** | **$760** | **$162** | **$914** |

---

## Key Metrics

| Metric | Jun | Jul | Aug |
|--------|-----|-----|-----|
| Paying clients | 0 | 1 | 2 |
| AI quotations generated | 3 | 25 | 60 |
| Avg. time per quotation | 60 min (manual) | 5 min (AI) | 5 min (AI) |
| API cost per client/month | — | ~$15 | ~$19 |

---

## Notes

- **Jun 2026:** $0 revenue. Project launched June 22, 2026. Development and pilot setup phase.
- **Jul 2026:** $800 projected from 2 setup fees. Clients sourced from GMT's existing network of 200+ technology integrators. Arms-length transactions.
- Infrastructure runs on founder's own hardware. N8N and NocoDB are open source. Hosting cost = $0.
- Related-party: GMT Telecomunicaciones is a production user during pilot phase but not billed.
- Full P&L spreadsheet available as uploaded file in Devpost submission.

---

## Break-even Analysis

- Monthly fixed costs: ~$12 (domain)
- Variable cost per client: ~$15/month (API usage)
- Revenue per client: $100/month subscription
- **Contribution margin per client: $85/month**
- **Break-even: 1 client covers all current fixed costs**
- **Path to $1,000 MRR: 12 paying clients**

*All figures in USD. Argentine operations billed in ARS at official exchange rate.*
*Repository: https://github.com/gmtfedex/gmt-quoteagent*
