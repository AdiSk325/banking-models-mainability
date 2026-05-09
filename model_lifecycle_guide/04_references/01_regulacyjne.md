# Dokumenty Regulacyjne — Źródła dla Model Lifecycle Guide

> Dokumenty regulacyjne stanowią fundamentalne wymagania dla governance modeli w bankowości.  
> Data Scientist powinien je znać — przynajmniej w zakresie swoich typów modeli.

---

## 🇺🇸 Stany Zjednoczone

### SR 11-7: Guidance on Model Risk Management
- **Wydawca:** Federal Reserve / OCC
- **Data:** 2011
- **Dostęp:** https://www.federalreserve.gov/supervisionreg/srletters/sr1107.htm
- **Znaczenie:** Fundament model risk management — definicja modelu, framework governance, walidacja, dokumentacja
- **Zastosowanie w tym przewodniku:** Rozdział 1 (definicja modelu), Rozdział 2 (zasady), Etap 7 (walidacja)

### OCC 2011-12
- **Wydawca:** Office of the Comptroller of the Currency
- **Data:** 2011
- **Dostęp:** https://www.occ.gov/news-issuances/bulletins/2011/bulletin-2011-12a.pdf
- **Znaczenie:** Komplementarny do SR 11-7, z perspektywy OCC

---

## 🇪🇺 Unia Europejska

### EBA Guidelines on Internal Ratings-Based Approach (EBA/GL/2017/16)
- **Wydawca:** European Banking Authority
- **Data:** 2017 (aktualizacje 2019–2023)
- **Dostęp:** https://www.eba.europa.eu/regulation-and-policy/credit-risk
- **Znaczenie:** Szczegółowe wymagania dla modeli PD, LGD, EAD w podejściu IRB
- **Zastosowanie:** Zakres (modele regulacyjne), Etap 7 (walidacja IRB), Etap 12 (change management)
- **Kluczowe dla:** Modeli regulacyjnych Tier 1 (PD/LGD/EAD)

### EBA Guidelines on Model Risk Management (EBA/GL/2023/01 lub nowsze)
- **Wydawca:** European Banking Authority
- **Data:** 2023
- **Dostęp:** https://www.eba.europa.eu
- **Znaczenie:** Najnowsze wytyczne obejmujące model risk management dla wszystkich banków europejskich
- **Zastosowanie:** Cały framework, szczególnie Rozdział 2 (zasady), Rozdział 3 (klasyfikacja), Etap 7

### ECB Guide to Internal Models (TRIM Guide)
- **Wydawca:** European Central Bank
- **Data:** 2018 (aktualizacje)
- **Dostęp:** https://www.bankingsupervision.europa.eu
- **Znaczenie:** Szczegółowe oczekiwania ECB wobec banków SSM — modele IRB, ryzyko rynkowe, CCR
- **Zastosowanie:** Etap 7 (walidacja), Etap 8 (governance dla SSM banków)

---

## 🇵🇱 Polska

### Rekomendacje KNF (aktualne)
- **Wydawca:** Komisja Nadzoru Finansowego
- **Dostęp:** https://www.knf.gov.pl
- **Kluczowe rekomendacje:** R, S, T, U, W (w zależności od obszaru modelowego)
- **Znaczenie:** Polskie wymogi nadzorcze nadrzędne dla banków krajowych
- **Zastosowanie:** Zakres, Etap 8 (governance)

> ✍️ **[DO UZUPEŁNIENIA]** Uzupełnić o konkretne Rekomendacje KNF istotne dla danej organizacji.

---

## 🌍 Bazylea / BCBS

### Basel III / CRR — wymagania dotyczące modeli wewnętrznych
- **Wydawca:** Basel Committee on Banking Supervision / Europejska implementacja (CRR)
- **Zastosowanie:** Modele kapitałowe (Tier 1 regulacyjne)

### IFRS 9 (MSR 9 — Instrumenty Finansowe)
- **Wydawca:** IASB / adaptacja europejska
- **Znaczenie:** Wymagania dla modeli ECL (Expected Credit Loss) — staging, forward-looking
- **Zastosowanie:** Modele IFRS 9, lifecycle i dokumentacja

---

## Jak używać tych źródeł

| Typ pracy | Zalecanae źródła |
|---|---|
| Budowa frameworku governance | SR 11-7, EBA Guidelines MRM |
| Dokumentacja modelu IRB | EBA/GL/2017/16, ECB TRIM |
| Dokumentacja IFRS 9 | IFRS 9, EBA IFRS 9 Guidelines |
| Walidacja niezależna | SR 11-7 Section 4, EBA Guidelines MRM |
| Change management | SR 11-7, EBA Guidelines MRM |
| Wymagania polskie | Rekomendacje KNF |
