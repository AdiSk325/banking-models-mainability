# Cykl Życia Modelu i Model Governance

## Opis

Ten katalog zawiera kompletny framework zarządzania cyklem życia modeli w bankowości — od inicjacji przez wdrożenie, monitoring, zarządzanie zmianą, aż po wycofanie.

## 🏛️ Główny Dokument: Model Lifecycle Guide

**→ [guide/MODEL_LIFECYCLE_GUIDE.md](./guide/MODEL_LIFECYCLE_GUIDE.md)**

Model Lifecycle Guide to **"konstytucja pracy z modelami"** — nadrzędny przewodnik definiujący zasady, etapy, role, artefakty i punkty kontrolne dla wszystkich modeli w organizacji.

---

## 📁 Struktura Katalogu

```
05_model_lifecycle/
├── guide/                          ← GŁÓWNY PRZEWODNIK (Poziom 2)
│   ├── MODEL_LIFECYCLE_GUIDE.md    ← Główny dokument — zacznij tutaj
│   ├── 01_cel_zakres_odbiorcy.md
│   ├── 02_zasady_nadrzedne.md
│   ├── 03_klasyfikacja_modeli.md   ← Regulatory / Scorecard / Supervised / Unsupervised
│   ├── 04_przeglad_cyklu_zycia.md
│   ├── 05_etapy/                   ← 10 szczegółowych etapów lifecycle
│   │   ├── 01_inicjacja.md
│   │   ├── 02_pozyskanie_danych.md
│   │   ├── 03_projektowanie_rozwoj.md
│   │   ├── 04_testowanie_dokumentacja.md
│   │   ├── 05_walidacja_niezalezna.md
│   │   ├── 06_akceptacja_governance.md
│   │   ├── 07_wdrozenie.md
│   │   ├── 08_monitoring_przeglad.md
│   │   ├── 09_zarzadzanie_zmiana.md
│   │   └── 10_wycofanie_archiwizacja.md
│   ├── 06_role_odpowiedzialnosci.md
│   ├── 07_wymagane_artefakty.md
│   ├── 08_kontrole_wyjatki.md
│   └── 09_powiazane_dokumenty.md
│
├── standards/                      ← STANDARDY SZCZEGÓŁOWE (Poziom 3)
│   ├── README.md
│   ├── development_standard.md
│   ├── documentation_standard.md
│   ├── validation_standard.md
│   ├── monitoring_standard.md
│   └── change_management_standard.md
│
├── procedures/                     ← PROCEDURY (Poziom 4)
│   └── README.md
│
├── templates/                      ← SZABLONY I NARZĘDZIA (Poziom 5)
│   └── README.md
│
├── references/                     ← KOLEKCJA REFERENCJI
│   ├── README.md                   ← Centralny indeks referencji
│   ├── regulatory/                 ← SR 11-7, EBA GL, ECB TRIM, KNF
│   ├── academic/                   ← Artykuły naukowe
│   └── industry/                   ← Whitepapers, best practices
│
├── research_papers/                ← Istniejące zasoby badawcze
└── specialized_knowledge/          ← Istniejąca wiedza specjalistyczna
```

---

## 🎯 Hierarchia Dokumentów

```
Poziom 1:  Polityka zarządzania ryzykiem modelowym (Model Risk Policy)
                              ↓
Poziom 2:  Model Lifecycle Guide  ← [guide/MODEL_LIFECYCLE_GUIDE.md]
                              ↓
Poziom 3:  Standardy (Standards)  ← [standards/]
                              ↓
Poziom 4:  Procedury (Procedures) ← [procedures/]
                              ↓
Poziom 5:  Szablony (Templates)   ← [templates/]
```

---

## 🔑 Zakres Modeli

Przewodnik obejmuje **cztery kategorie modeli**:

| Kategoria | Przykłady | Tier |
|-----------|-----------|------|
| **A — Regulacyjne** | PD/LGD/EAD (IRB), IFRS9 ECL | Tier 1 |
| **B — Scorecard/Statystyczne** | Scoring aplikacyjny, behawioralny, kolekcyjny | Tier 1-2 |
| **C — Supervised ML** | XGBoost, Random Forest, Neural Networks | Tier 2 |
| **D — Unsupervised ML** | Clustering, Anomaly Detection, PCA | Tier 2-3 |

---

## 📖 Referencje Regulacyjne

- SR 11-7 (Federal Reserve, 2011) — globalny standard MRM
- EBA Guidelines on Model Risk Management (2023)
- ECB Guide to Internal Models / TRIM (2018)
- SS1/23 (PRA/BoE, 2023)
- Rekomendacje KNF

Pełna kolekcja: **[references/README.md](./references/README.md)**
