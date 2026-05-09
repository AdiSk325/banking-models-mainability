# Standard Walidacji Modeli

> **Poziom w hierarchii:** 2 — Standard  
> **Dokument nadrzędny:** [../guide/MODEL_LIFECYCLE_GUIDE.md](../guide/MODEL_LIFECYCLE_GUIDE.md)  
> **Wersja:** 0.1-draft  
> **Status:** Do opracowania — poniżej struktura i prompty dla autora

---

## Cel

Standard określa minimalne wymagania dotyczące niezależnej walidacji modeli, zakresu oceny, wymagań niezależności walidatora, klasyfikacji findings i procesu remediation.

---

## 1. Wymagania Niezależności

<!-- PROMPT DLA AUTORA:
Opisz szczegółowe wymagania niezależności walidatora.
Jak zorganizowany jest zespół walidacji w organizacji?
Jak rozwiązuje się sytuacje konfliktu interesów?
-->

[Do uzupełnienia]

---

## 2. Zakres Walidacji według Kategorii Modelu

<!-- PROMPT DLA AUTORA:
Dla każdej kategorii modelu (A, B, C, D) opisz obowiązkowy zakres walidacji.
Jakie elementy mogą być wyłączone ze scope i kiedy?
Co oznacza "limited scope validation" dla zmian niematerialnych?
-->

### Kategoria A — Regulacyjny

| Element | Obowiązkowy | Metodologia |
|---------|-------------|-------------|
| Conceptual soundness | ✅ | [PLACEHOLDER] |
| Outcomes analysis / Backtesting | ✅ | [PLACEHOLDER] |
| Regulatory compliance review | ✅ | Mapowanie do EBA/ECB TRIM/KNF |
| Benchmarking | ✅ | [PLACEHOLDER] |
| Sensitivity analysis | ✅ | [PLACEHOLDER] |
| Stress testing | ✅ | [PLACEHOLDER] |
| Documentation review | ✅ | Kompletność MDD |

### Kategoria B — Scorecard

| Element | Obowiązkowy | Metodologia |
|---------|-------------|-------------|
| Conceptual soundness | ✅ | |
| Outcomes analysis | ✅ | AUC, Gini, KS, PSI na OOT |
| WoE/IV review | ✅ | Weryfikacja binningów |
| Benchmarking | ✅ | vs. baseline model |
| Bias & Fairness review | ✅ | Disparate impact |
| Documentation review | ✅ | |

### Kategoria C — Supervised ML

| Element | Obowiązkowy | Metodologia |
|---------|-------------|-------------|
| Conceptual soundness | ✅ | |
| Outcomes analysis | ✅ | Testy na OOT |
| Explainability review | ✅ | SHAP consistency check |
| Bias & Fairness review | ✅ | |
| Feature analysis | ✅ | Sens biznesowy |
| Benchmarking | ✅ | vs. simpler model |
| Documentation review | ✅ | |

### Kategoria D — Unsupervised

| Element | Obowiązkowy | Metodologia |
|---------|-------------|-------------|
| Conceptual soundness | ✅ | Główny element |
| Business evaluation | ✅ | Sensowność segmentów |
| Stability testing | ✅ | Niezależna replikacja |
| Sensitivity analysis | ✅ | Wrażliwość na parametry |
| Documentation review | ✅ | |

---

## 3. Klasyfikacja Findings

<!-- PROMPT DLA AUTORA:
Zdefiniuj dokładne kryteria klasyfikacji findings (Critical/High/Medium/Low).
Podaj przykłady dla każdej klasy.
Opisz proces zamykania findings.
-->

| Klasa | Definicja | Przykłady | Termin remediation |
|-------|-----------|-----------|-------------------|
| **Critical** | [Do uzupełnienia] | Fałszywa dokumentacja, błąd logiczny w formule | Brak wdrożenia do zamknięcia |
| **High** | [Do uzupełnienia] | | [PLACEHOLDER] |
| **Medium** | [Do uzupełnienia] | | [PLACEHOLDER] |
| **Low** | [Do uzupełnienia] | | Opcjonalny |

---

## 4. Metryki i Progi Walidacyjne

<!-- PROMPT DLA AUTORA:
Uzupełnij progi akceptacji metryk dla każdego typu modelu.
Progi muszą odzwierciedlać standardy organizacji — nie przepisuj z regulacji.
-->

### Modele klasyfikacyjne

| Metryka | Minimalny próg akceptacji | Próg alarmowy |
|---------|--------------------------|---------------|
| AUROC / Gini | ≥ [PLACEHOLDER] | < [PLACEHOLDER] |
| KS Statistic | ≥ [PLACEHOLDER] | |
| PSI (vs baseline) | ≤ 0.20 | > 0.20 |
| Accuracy / Recall | Zależy od zastosowania | |

---

## 5. Validation Report — Wymagana Struktura

<!-- PROMPT DLA AUTORA:
Opisz obowiązkową strukturę Validation Report.
Powiąż z szablonem Validation Report.
-->

1. Executive Summary
2. Scope of Validation
3. Validation Methodology
4. Findings (per area)
5. Findings Register (tabela)
6. Conclusions and Recommendations
7. Validator Sign-off

---

## 6. Re-walidacja

<!-- PROMPT DLA AUTORA:
Opisz kiedy i jak przebiega re-walidacja.
Jaki jest zakres re-walidacji przy zmianie materialnej vs. przegląd roczny?
-->

[Do uzupełnienia]

---

## Powiązane Dokumenty

- [Guide — Etap 5.5: Niezależna Walidacja](../guide/05_etapy/05_walidacja_niezalezna.md)
- [Validation Report Template](../templates/)
- [Findings Register Template](../templates/)
