# Kolekcja Referencji — Model Lifecycle Guide

> **Cel:** Centralne repozytorium źródeł i referencji dla Model Lifecycle Guide  
> **Powiązany dokument:** [../guide/MODEL_LIFECYCLE_GUIDE.md](../guide/MODEL_LIFECYCLE_GUIDE.md)  
> **Ostatnia aktualizacja:** 2026-05-09

---

## Struktura Kolekcji

```
references/
├── README.md                    (ten plik — centralny indeks)
├── regulatory/                  (dokumenty regulacyjne i nadzorcze)
│   ├── README.md
│   ├── SR_11-7_summary.md      (SR 11-7 — kluczowe wymagania)
│   ├── EBA_guidelines.md       (EBA Guidelines on MRM)
│   ├── ECB_TRIM_summary.md     (ECB TRIM Guide)
│   └── KNF_requirements.md     (Wymagania KNF)
├── academic/                    (artykuły i publikacje akademickie)
│   └── README.md
└── industry/                    (whitepapers i best practices branżowe)
    └── README.md
```

---

## Szybki Dostęp — Kluczowe Referencje

### 🏛️ Dokumenty Regulacyjne (Obligatoryjne)

| Dokument | Organizacja | Rok | Kluczowe sekcje | Link |
|----------|-------------|-----|-----------------|------|
| **SR 11-7** Guidance on Model Risk Management | US Federal Reserve | 2011 | Defn. modelu, walidacja, governance | [federalreserve.gov](https://www.federalreserve.gov/supervisionreg/srletters/sr1107.htm) |
| **OCC Bulletin 2011-12** | OCC | 2011 | Uzupełnienie SR 11-7 | [occ.gov](https://www.occ.gov/news-issuances/bulletins/2011/bulletin-2011-12a.pdf) |
| **EBA/GL/2023** Guidelines on Model Risk Management | EBA | 2023 | Wiążące dla banków UE | [eba.europa.eu](https://www.eba.europa.eu) |
| **ECB Guide to Internal Models (TRIM)** | ECB | 2018 | Modele IRB, walidacja | [bankingsupervision.europa.eu](https://www.bankingsupervision.europa.eu) |
| **SS1/23** Model Risk Management Principles | PRA/BoE | 2023 | Dobra praktyka UK | [bankofengland.co.uk](https://www.bankofengland.co.uk) |
| **EBA/GL/2017/16** PD, LGD, CCF Estimation | EBA | 2017 | Modele IRB szczegółowe | [eba.europa.eu](https://www.eba.europa.eu) |

### 📚 Kluczowe Publikacje Akademickie

| Tytuł | Autorzy | Rok | Dlaczego ważne |
|-------|---------|-----|----------------|
| Model Risk Management | Morini & Baviera | 2019 | Przegląd framework MRM |
| "Model Cards for Model Reporting" | Mitchell et al. | 2019 | Standard Model Card — ML |
| "A Unified Approach to Model Predictions (SHAP)" | Lundberg & Lee | 2017 | Podstawy SHAP |
| "Why Should I Trust You? (LIME)" | Ribeiro et al. | 2016 | Podstawy LIME |
| "Hidden Technical Debt in ML Systems" | Sculley et al. (Google) | 2015 | MLOps — kluczowe |

### 🏢 Whitepapers i Best Practices

| Dokument | Organizacja | Rok | Temat |
|----------|-------------|-----|-------|
| Model Risk Management in Banks | Deloitte / EY / KPMG | różne | Praktyki branżowe |
| MLOps: Continuous Delivery for ML | Google | 2020 | MLOps praktyki |
| Principles for AI | FSB / BIS | 2021+ | Governance AI |

---

## Mapa Referencji do Rozdziałów Guide

| Rozdział Guide | Kluczowe referencje |
|----------------|---------------------|
| Rozdz. 1 — Definicja modelu | SR 11-7 Sekcja I; EBA GL 2023 |
| Rozdz. 2 — Zasady | SR 11-7 Sekcja II; EBA GL |
| Rozdz. 3 — Klasyfikacja | SR 11-7; EBA GL Annex |
| Rozdz. 5.5 — Walidacja | SR 11-7 Sekcja IV; EBA GL; ECB TRIM |
| Rozdz. 5.8 — Monitoring | SR 11-7 Sekcja V; EBA GL |
| Rozdz. 5.9 — Zmiana | SR 11-7 Sekcja VI |
| Kategoria C — Explainability | SHAP (Lundberg), LIME (Ribeiro), EBA AI |
| Kategoria C/D — Bias | IEEE P7003; EU AI Act; RODO Art. 22 |
| Modele IRB | EBA/GL/2017/16; ECB TRIM; CRR |
| Modele IFRS9 | IFRS 9; EBA IFRS9 Guidelines |

---

## Wskazówki dla Kontrybutorów

Dodając nową referencję do kolekcji:
1. Wybierz właściwy podfolder (regulatory / academic / industry)
2. Dodaj wpis do tabeli w odpowiednim pliku README
3. Jeśli tworzysz summary dokumentu — użyj szablonu poniżej
4. Zaktualizuj plik README (ten) o nową pozycję

### Szablon Summary Dokumentu

```markdown
# [Tytuł Dokumentu]

**Organizacja / Autorzy:** ...
**Rok:** ...
**Link:** ...
**Typ:** Regulacja / Artykuł / Whitepaper

## Streszczenie

[2-3 akapity streszczenia]

## Kluczowe Wymagania dla Model Lifecycle

[Bullet points z wymaganiami istotnymi dla guide]

## Cytowania w Guide

[Które rozdziały Guide odwołują się do tego dokumentu]
```

---

## Dodatkowe Zasoby Online

| Zasób | URL | Zakres |
|-------|-----|--------|
| Risk.net | risk.net | Artykuły i analizy finansowe |
| SSRN | ssrn.com | Pre-prints akademickie |
| arXiv (cs.LG, stat.ML) | arxiv.org | ML research |
| BIS Research | bis.org | Regulacje bankowe |
| EBA Publications | eba.europa.eu | EU banking regulation |
| KNF Wytyczne | knf.gov.pl | Polskie wymogi nadzorcze |
| NBP Raporty | nbp.pl | Kontekst polskiego rynku |
