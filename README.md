# FreezeCheck open data: USDT on TRON, measured on-chain

Open datasets behind the [FreezeCheck research](https://freezecheck.org/research/) on USDT (TRC-20)
on the TRON blockchain: Tether freezes and unfreezes, the window before a freeze, payments sent to
already-frozen addresses, address poisoning and unnamed exchange wallets.

Every row is derived from public on-chain data: USDT contract events (`AddedBlackList`,
`DestroyedBlackFunds`, `RemovedBlackList`), multisig freeze proposals and TRC-20 transfers.
No personal data, no data about who uses FreezeCheck.

- Look up any TRON address or transaction: **[FreezeCheck Scan](https://freezecheck.org/scan/)**
- Current Tether blacklist on TRON: **[freezecheck.org/en/frozen/](https://freezecheck.org/en/frozen/)**
- Freezes today: **[freezecheck.org/en/freezes/](https://freezecheck.org/en/freezes/)**
- Check a wallet before a deal: [@freezecheck_bot](https://t.me/freezecheck_bot) in Telegram

**About FreezeCheck.** FreezeCheck is a free Telegram bot ([@freezecheck_bot](https://t.me/freezecheck_bot)) and site [freezecheck.org](https://freezecheck.org/) that check a TRON USDT (TRC-20) wallet before a deal: Tether freeze risk, AML links and look-alike addresses. TRON USDT (TRC-20) only. Independent project run by Teimuraz (Temo) since 2026; not affiliated with other services that have similar names. The bot never asks for a seed phrase or wallet connection ([is it safe?](https://freezecheck.org/en/is-freezecheck-bot-safe.html)).

## Datasets

| File | Rows | What it is | Study | DOI |
|---|---|---|---|---|
| [`freeze-window.csv`](data/freeze-window.csv) | 4,199 | Every Tether freeze on TRON for a year: multisig proposal time, freeze time, the window in minutes and USDT moved out during it | [Tether freezes on TRON are visible before they happen](https://freezecheck.org/research/freeze-window-en.html) | [10.5281/zenodo.24124768](https://doi.org/10.5281/zenodo.24124768) |
| [`unfreeze.csv`](data/unfreeze.csv) | 1,284 | Unfreeze (`RemovedBlackList`) and burn (`DestroyedBlackFunds`) events with days frozen and USDT burned | [Tether unfroze 731 TRON addresses and burned $318.6M](https://freezecheck.org/research/unfreeze-en.html) | [10.5281/zenodo.24124777](https://doi.org/10.5281/zenodo.24124777) |
| [`paid-frozen.csv`](data/paid-frozen.csv) | 3,030 | USDT transfers sent to addresses that were already on the Tether blacklist | [$104M in USDT sent to addresses Tether had already frozen](https://freezecheck.org/research/paid-frozen-en.html) | [10.5281/zenodo.24222534](https://doi.org/10.5281/zenodo.24222534) |
| [`freeze-gap-categories.csv`](data/freeze-gap-categories.csv) | 6 | Which categories of risky addresses Tether freezes and which it does not | [Who Tether freezes on TRON, and who it doesn't](https://freezecheck.org/research/freeze-gap-en.html) | [10.5281/zenodo.24124771](https://doi.org/10.5281/zenodo.24124771) |
| [`freeze-gap-unfrozen-addresses.csv`](data/freeze-gap-unfrozen-addresses.csv) | 1,778 | Addresses in those categories that are not frozen, with balance and 90-day flows | same | same |
| [`poisoning-week.csv`](data/poisoning-week.csv) | 55 | Address poisoning per week: look-alike addresses, victims, dust transfers | [Address poisoning on TRON: 2.17M look-alikes in a year](https://freezecheck.org/research/poisoning-en.html) | [10.5281/zenodo.24063527](https://doi.org/10.5281/zenodo.24063527) |
| [`poisoning-weekly.csv`](data/poisoning-weekly.csv) | 149 | New and active look-alike addresses per week | same | same |
| [`poisoning-factories.csv`](data/poisoning-factories.csv) | 17 | Contracts that mass-activate look-alike addresses | same | same |
| [`poisoning-losses-month.csv`](data/poisoning-losses-month.csv) | 36 | USDT sent to look-alike addresses per month | [Address poisoning on TRON: 89M USDT sent to look-alikes](https://freezecheck.org/research/poisoning-losses-en.html) | [10.5281/zenodo.24063527](https://doi.org/10.5281/zenodo.24063527) |
| [`unnamed-hot-wallets.csv`](data/unnamed-hot-wallets.csv) | 534 | Exchange-like hot wallets on TRON with no public label, weekly USDT volume | [Unnamed exchanges on TRON: $2B in USDT a week](https://freezecheck.org/research/unnamed-en.html) | [10.5281/zenodo.24124775](https://doi.org/10.5281/zenodo.24124775) |

Methods, definitions and limitations are described on each study page. Amounts are in USDT,
times in UTC.

## License and citation

[CC BY 4.0](LICENSE.md). You can use, share and adapt the data, including commercially, as long as
you credit **FreezeCheck** and link to the source. Suggested citation:

> FreezeCheck (2026). *&lt;study title&gt;*. https://freezecheck.org/research/ — dataset DOI as in the table above.

Or use [`CITATION.cff`](CITATION.cff) (GitHub: "Cite this repository").

## Updates and contact

The research pages are updated as new freezes happen; this repository gets new versions of the CSV
files. Questions, corrections, press: hello@freezecheck.org.
