# STD-004: Standard Monitoringu Modeli

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet  
> **Powiązany rozdział przewodnika:** Etapy 10, 11

---

## Cel standardu

Standard określa minimalne wymagania dla monitoringu modeli produkcyjnych, w tym metryki, progi, częstotliwość, raportowanie i procedury reakcji na przekroczenie progów.

---

## 1. Zasada — Monitoring by Design

> 🔴 **OBOWIĄZKOWE** — Plan monitoringu musi być przygotowany **przed wdrożeniem** modelu, nie po.  
> Monitoring jest obowiązkiem Data Scientista i Model Ownera — nie jest działaniem incydentalnym.

---

## 2. Obowiązkowe Metryki Monitoringowe

### Metryki wspólne dla wszystkich typów modeli

| Metryka | Opis | Próg ostrzeżenia | Próg krytyczny |
|---|---|---|---|
| Data quality | Wskaźnik brakujących wartości na zmiennych wejściowych | > 5% | > 10% |
| Population stability (PSI) | Stabilność rozkładu danych wejściowych | PSI > 0.1 | PSI > 0.25 |
| System availability | Dostępność modelu / SLA | < 99% | < 95% |

### Metryki specyficzne per typ modelu

> 📋 **[SUPERVISED]** Dodatkowe metryki:
> - **Discriminatory power** — GINI/AUC/KS (porównanie z baseline development)
> - **Calibration** — porównanie predicted vs. actual rates
> - **Bad rate stability** — zmiana stopy rzeczywistych defaultów/zdarzeń
> - **Override rate** — odsetek decyzji z override przez użytkownika
> - **CSI** (Characteristic Stability Index) — stabilność zmiennych wejściowych

> 🔬 **[UNSUPERVISED]** Dodatkowe metryki:
> - **Cluster stability** — Jaccard index lub podobne między periodami
> - **Cluster size distribution** — czy rozmiary segmentów są stabilne?
> - **Feature distribution per cluster** — monitoring driftu cech per segment

> ⚠️ **[REGULACYJNE]** Dodatkowe metryki:
> - **Backtesting p-value** — testy statystyczne poprawności prognoz
> - **Realizacja LGD/ECL** — porównanie prognozy z realizacją
> - **Regulatory benchmarks** — porównanie z zewnętrznymi benchmarkami (jeśli dostępne)

---

## 3. Częstotliwość Monitoringu

| Tier modelu | Częstotliwość podstawowa | Częstotliwość intensywna (po zdarzeniu) |
|---|---|---|
| Tier 1 | Miesięczna | Tygodniowa |
| Tier 2 | Kwartalna | Miesięczna |
| Tier 3 | Półroczna | Kwartalna |

---

## 4. Trigger Events

Zdarzenia wymagające natychmiastowej reakcji (niezależnie od harmonogramu cyklicznego):

| Zdarzenie | Wymagana reakcja | Czas reakcji |
|---|---|---|
| PSI > próg krytyczny | Analiza przyczyn + escalacja do MRM | 5 dni roboczych |
| Degradacja performance > X% | Analiza przyczyn, ewentualny review | 10 dni roboczych |
| Błąd systemu / awaria modelu | Incydent, rollback, RCA | Niezwłocznie |
| Zmiana zewnętrzna (regulacyjna, rynkowa) | Ocena wpływu | 20 dni roboczych |
| Roczny termin przeglądu | Annual Review | — |

---

## 5. Raportowanie

> ✍️ **[DO UZUPEŁNIENIA]** Opisać:
> - Format raportów monitoringowych
> - Do kogo raporty trafiają (Model Owner, MRM, MRC?)
> - Jak eskalowane są wyniki poniżej progów

---

## Powiązania

- [Rozdział 5: Etap 10 — Monitoring](../00_guide/05_etapy_cyklu_zycia.md#510-etap-10-monitoring)
- [TMPL-004: Plan Monitoringu](../03_templates/TMPL-004_plan_monitoringu.md)
- [PROC-005: Procedura Monitoringu](../02_procedures/PROC-005_monitoring.md)
