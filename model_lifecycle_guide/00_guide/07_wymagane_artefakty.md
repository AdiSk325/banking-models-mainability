# Rozdział 7: Wymagane Artefakty i Minimalna Dokumentacja

> **Status:** 🔄 Szkielet — wymaga uzupełnienia macierzy artefaktów per tier  
> **Priorytet uzupełnienia:** Wysoki

---

## 7.1 Zasada

Artefakty są dowodem wykonanej pracy i podstawą do niezależnej oceny i audytu modelu. Każdy model — niezależnie od tieru — musi wytworzyć zestaw minimalnych artefaktów.

> 🔴 **OBOWIĄZKOWE** — Brak wymaganych artefaktów blokuje przejście przez bramkę walidacji i wdrożenia.

---

## 7.2 Lista Artefaktów per Etap

### Faza Inicjacji

| Artefakt | Szablon | Tier 1 | Tier 2 | Tier 3 | Uwagi |
|---|---|---|---|---|---|
| Business Case / Model Concept Note | TMPL-001 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany | |
| Karta klasyfikacji tieru | TMPL-001 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🔴 Obowiązkowy | |
| Wpis w inwentarzu modeli | — | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🔴 Obowiązkowy | |
| Plan developmentu | — | 🔴 Obowiązkowy | 🟡 Zalecany | 🟢 Opcjonalny | |

### Faza Development

| Artefakt | Szablon | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|---|
| Data Assessment Report | — | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Data Dictionary | STD-002 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Design Document / Methodology Note | — | 🔴 Obowiązkowy | 🟡 Zalecany | 🟢 Opcjonalny |
| Assumptions Register | STD-002 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Kod modelu (wersjonowany w Git) | — | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🔴 Obowiązkowy |
| Model Development Document (MDD) | TMPL-002 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Uproszczony |
| Test Results Report | — | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |

### Faza Zatwierdzenia

| Artefakt | Szablon | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|---|
| Raport Walidacji | TMPL-003 | 🔴 Pełny | 🔴 Pełny | 🟡 Uproszczony |
| Approval Record | — | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Lista findings z planem adresowania | — | 🔴 Obowiązkowy | 🟡 Zalecany | 🟢 Opcjonalny |

### Faza Produkcji

| Artefakt | Szablon | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|---|
| Deployment Evidence / Go-live checklist | PROC-004 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| UAT Sign-off | — | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Plan Monitoringu | TMPL-004 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Raporty monitoringowe (cykliczne) | — | 🔴 Miesięczne | 🔴 Kwartalne | 🟡 Półroczne |
| Change Log | STD-006 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🔴 Obowiązkowy |
| Annual Review Report | — | 🔴 Roczny | 🔴 Roczny | 🟢 Opcjonalny |

### Faza Zakończenia

| Artefakt | Szablon | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|---|
| Retirement Decision Document | TMPL-006 | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Archiwum dokumentacji | — | 🔴 Obowiązkowy | 🔴 Obowiązkowy | 🟡 Zalecany |
| Lessons Learned | — | 🟡 Zalecany | 🟢 Opcjonalny | 🟢 Opcjonalny |

---

## 7.3 Minimalna Zawartość Model Development Document (MDD)

MDD jest kluczowym artefaktem każdego modelu. Minimalna struktura:

1. **Executive Summary** — cel modelu, metodologia, wyniki kluczowe
2. **Kontekst biznesowy** — problem, zastosowanie, populacja docelowa
3. **Opis danych** — źródła, zakres, jakość, lineage
4. **Metodologia** — wybrane podejście i uzasadnienie
5. **Feature Engineering** — opis zmiennych, transformacje
6. **Trening i selekcja modelu** — procedura, wyniki
7. **Wyniki performance** — metryki, backtesting, porównanie benchmarkowe
8. **Założenia i ograniczenia** — kompletna lista
9. **Explainability** — interpretacja wyników (SHAP lub inne)
10. **Plan monitoringu** — metryki, triggery, częstotliwość
11. **Historia zmian** — wersje, daty, autorzy

---

## 7.4 Specyficzne Artefakty per Typ Modelu

> ⚠️ **[REGULACYJNE]** Modele regulacyjne wymagają dodatkowo:
> - Dokumentację zgodności z regulacją (mapping wymagań EBA/KNF)
> - Use Test documentation (dowód, że model jest faktycznie używany w zarządzaniu ryzykiem)
> - Stress testing documentation
> - Approval Record ze wskazaniem trybu notyfikacji nadzorcy (jeśli dotyczy)

> 📋 **[SUPERVISED]** Modele supervised — zalecane dodatkowe artefakty:
> - Label definition document (definicja target variable z uzasadnieniem)
> - Data leakage assessment (ocena ryzyka leakage)
> - Model card (skrócona karta modelu dla użytkowników biznesowych)
> - Fairness/bias assessment (jeśli model podejmuje decyzje wobec klientów)

> 🔬 **[UNSUPERVISED]** Modele unsupervised — zalecane dodatkowe artefakty:
> - Cluster interpretation document (opis każdego segmentu z perspektywy biznesowej)
> - Stability assessment report (wyniki testów stabilności klasteryzacji)
> - Business validation sign-off (potwierdzenie sensowności biznesowej przez ekspertów)

---

## 7.5 Wymagania Archiwizacji

> ✍️ **[DO UZUPEŁNIENIA]** Uzupełnić o okresy retencji per typ dokumentu, zgodnie z wewnętrzną polityką archiwizacyjną.

| Typ artefaktu | Okres retencji | Lokalizacja archiwum |
|---|---|---|
| MDD | min. [X] lat od wycofania | [do uzupełnienia] |
| Raporty walidacji | min. [X] lat | [do uzupełnienia] |
| Kod modelu | min. [X] lat | Git / archiwum |
| Dane treningowe | per polityka danych | [do uzupełnienia] |
| Approval Records | min. [X] lat | [do uzupełnienia] |

---

## 7.6 Powiązane Dokumenty

- [STD-002: Standard Dokumentacji](../01_supporting_standards/STD-002_dokumentacja.md) — szczegółowe wymagania treści dokumentacji
- [03_templates/](../03_templates/) — szablony do wypełnienia
- [Rozdział 5: Etapy](./05_etapy_cyklu_zycia.md) — kiedy wytwarzać każdy artefakt

---

*Poprzedni: [06 — Role](./06_role_i_odpowiedzialnosci.md) | Następny: [08 — Kontrole i Wyjątki](./08_kontrole_wyjatki.md)*
