# Rozdział 9: Powiązane Dokumenty i Mapa Standardów

> **Status:** 🔄 Szkielet — wymaga uzupełnienia o linki do dokumentów organizacyjnych  
> **Priorytet uzupełnienia:** Średni

---

## 9.1 Mapa Dokumentów

Ten przewodnik jest dokumentem poziomu 1 (guide/framework). Poniżej mapa powiązanych dokumentów.

```
┌────────────────────────────────────────────────────────────────┐
│ POZIOM 0: POLITYKI                                             │
│ • Polityka Model Risk Management                               │
│ • Polityka zarządzania danymi                                  │
│ • Polityka zgodności regulacyjnej                             │
└────────────────────────────────────────────────────────────────┘
                              ↑ nadrzędne
┌────────────────────────────────────────────────────────────────┐
│ POZIOM 1: TEN DOKUMENT                                         │
│ • Model Lifecycle Guide                                        │
└────────────────────────────────────────────────────────────────┘
                              ↓ szczegółowe
┌────────────────────────────────────────────────────────────────┐
│ POZIOM 2: STANDARDY (01_supporting_standards/)                 │
│ • STD-001: Rozwój Modeli                                      │
│ • STD-002: Dokumentacja                                        │
│ • STD-003: Walidacja                                           │
│ • STD-004: Monitoring                                          │
│ • STD-005: Inwentarz Modeli                                   │
│ • STD-006: Zarządzanie Zmianą                                 │
│ • STD-007: Explainability                                      │
│ • STD-008: Wdrożenie                                           │
└────────────────────────────────────────────────────────────────┘
                              ↓ operacyjne
┌────────────────────────────────────────────────────────────────┐
│ POZIOM 3: PROCEDURY (02_procedures/)                           │
│ • PROC-001: Inicjacja modelu                                   │
│ • PROC-002: Dane i ocena                                       │
│ • PROC-003: Walidacja                                          │
│ • PROC-004: Wdrożenie                                          │
│ • PROC-005: Monitoring i przegląd                             │
│ • PROC-006: Wycofanie                                          │
└────────────────────────────────────────────────────────────────┘
                              ↓ narzędzia
┌────────────────────────────────────────────────────────────────┐
│ POZIOM 4: SZABLONY (03_templates/)                             │
│ • TMPL-001: Dokument koncepcji                                 │
│ • TMPL-002: Model Development Document                        │
│ • TMPL-003: Raport walidacji                                   │
│ • TMPL-004: Plan monitoringu                                   │
│ • TMPL-005: Wniosek o zmianę                                   │
│ • TMPL-006: Formularz wycofania                                │
└────────────────────────────────────────────────────────────────┘
```

---

## 9.2 Tabela Powiązanych Standardów

| Dokument | Typ | Co opisuje | Link |
|---|---|---|---|
| STD-001: Rozwój Modeli | Standard | Szczegółowe wymagania development (kod, dane, testy) | [→](../01_supporting_standards/STD-001_rozwoj_modeli.md) |
| STD-002: Dokumentacja | Standard | Minimalna treść MDD, szablony dokumentacji | [→](../01_supporting_standards/STD-002_dokumentacja.md) |
| STD-003: Walidacja | Standard | Zakres, metodologia i wymagania walidacji | [→](../01_supporting_standards/STD-003_walidacja.md) |
| STD-004: Monitoring | Standard | Metryki, triggery, częstotliwość monitoringu | [→](../01_supporting_standards/STD-004_monitoring.md) |
| STD-005: Inwentarz | Standard | Rejestracja i utrzymanie inwentarza modeli | [→](../01_supporting_standards/STD-005_inwentarz.md) |
| STD-006: Zmiana | Standard | Klasyfikacja zmian, ścieżki zatwierdzania | [→](../01_supporting_standards/STD-006_zarzadzanie_zmiana.md) |
| STD-007: Explainability | Standard | Wymagania interpretowalności modeli | [→](../01_supporting_standards/STD-007_explainability.md) |
| STD-008: Wdrożenie | Standard | Wymagania techniczne wdrożenia i MLOps | [→](../01_supporting_standards/STD-008_wdrozenie.md) |

---

## 9.3 Tabela Powiązanych Procedur

| Dokument | Typ | Co opisuje | Link |
|---|---|---|---|
| PROC-001: Inicjacja | Procedura | Krok po kroku: inicjacja projektu modelarskiego | [→](../02_procedures/PROC-001_inicjacja.md) |
| PROC-002: Dane | Procedura | Krok po kroku: assessment i przygotowanie danych | [→](../02_procedures/PROC-002_dane_i_ocena.md) |
| PROC-003: Walidacja | Procedura | Krok po kroku: przygotowanie do i przebieg walidacji | [→](../02_procedures/PROC-003_walidacja.md) |
| PROC-004: Wdrożenie | Procedura | Krok po kroku: UAT, deployment, go-live | [→](../02_procedures/PROC-004_wdrozenie.md) |
| PROC-005: Monitoring | Procedura | Krok po kroku: monitoring ciągły i review | [→](../02_procedures/PROC-005_monitoring.md) |
| PROC-006: Wycofanie | Procedura | Krok po kroku: decyzja, archiwizacja, retirement | [→](../02_procedures/PROC-006_wycofanie.md) |

---

## 9.4 Tabela Szablonów

| Szablon | Zastosowanie | Link |
|---|---|---|
| TMPL-001 | Dokument koncepcji modelu (Business Case) | [→](../03_templates/TMPL-001_dokument_koncepcji.md) |
| TMPL-002 | Model Development Document (MDD) | [→](../03_templates/TMPL-002_dokumentacja_modelu.md) |
| TMPL-003 | Raport walidacji | [→](../03_templates/TMPL-003_raport_walidacji.md) |
| TMPL-004 | Plan monitoringu | [→](../03_templates/TMPL-004_plan_monitoringu.md) |
| TMPL-005 | Wniosek o zmianę modelu | [→](../03_templates/TMPL-005_wniosek_o_zmiane.md) |
| TMPL-006 | Formularz wycofania modelu | [→](../03_templates/TMPL-006_wycofanie_modelu.md) |

---

## 9.5 Zewnętrzne Regulacje i Standardy

Szczegółowe opisy i linki: [04_references/](../04_references/)

| Dokument | Typ | Zastosowanie |
|---|---|---|
| SR 11-7 (Fed Reserve) | Regulacyjny | Fundament model risk management |
| EBA/GL/2017/16 | Regulacyjny | PD/LGD/EAD dla IRB |
| EBA Model Risk Management Guidelines | Regulacyjny | Szeroki zakres model governance |
| ECB Guide to Internal Models (TRIM) | Regulacyjny | Szczegółowe wymogi wewnętrznych modeli |
| Rekomendacje KNF | Regulacyjny | Polskie wymogi nadzorcze |
| IFRS 9 | Regulacyjny | Modele oczekiwanych strat kredytowych |
| ISO/IEC TR 24028:2020 | Standard | AI trustworthiness |

---

*Poprzedni: [08 — Kontrole](./08_kontrole_wyjatki.md) | Następny: [10 — Przegląd Przewodnika](./10_przeglad_przewodnika.md)*
