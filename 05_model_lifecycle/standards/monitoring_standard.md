# Standard Monitoringu Modeli

> **Poziom w hierarchii:** 2 — Standard  
> **Dokument nadrzędny:** [../guide/MODEL_LIFECYCLE_GUIDE.md](../guide/MODEL_LIFECYCLE_GUIDE.md)  
> **Wersja:** 0.1-draft  
> **Status:** Do opracowania

---

## Cel

Standard określa minimalne wymagania dotyczące monitoringu modeli produkcyjnych: metryki, progi, częstotliwość, raportowanie i trigger events.

---

## 1. Metryki Monitoringu — Definicje

### 1.1 Population Stability Index (PSI)

<!-- PROMPT DLA AUTORA:
Opisz dokładnie jak obliczany jest PSI w organizacji.
Jakie są progi alarmowe?
Jak PSI jest interpretowany w raportach?
-->

**Wzór:**
```
PSI = Σ (Actual% - Expected%) × ln(Actual% / Expected%)
```

**Progi interpretatywne (standard branżowy):**
- PSI < 0.1 — Niskie przesunięcie (dobra stabilność)
- PSI 0.1–0.2 — Umiarkowane przesunięcie (monitoring wymagany)
- PSI > 0.2 — Wysokie przesunięcie (eskalacja do MRM)
- PSI > 0.25 — Krytyczne (rozważenie wstrzymania modelu)

---

### 1.2 Characteristic Stability Index (CSI)

<!-- PROMPT DLA AUTORA:
Opisz CSI i jak jest obliczany per zmienna.
Jakie zmienne są monitorowane (wszystkie vs. kluczowe)?
-->

[Do uzupełnienia]

---

### 1.3 Metryki Performance — Monitoring

<!-- PROMPT DLA AUTORA:
Opisz jak metryki performance są śledzone w czasie.
Jaki jest baseline do porównań (OOT, deployment date)?
Jakie są progi degradacji wywołujące eskalację?
-->

| Metryka | Baseline | Próg alarmowy | Próg krytyczny |
|---------|---------|---------------|----------------|
| AUROC / Gini | Wartość w OOT walidacyjnym | Spadek > [PLACEHOLDER]% | Spadek > [PLACEHOLDER]% |
| KS Statistic | Wartość w OOT | | |
| Accuracy / Recall | [PLACEHOLDER] | | |

---

### 1.4 Data Quality Monitoring

<!-- PROMPT DLA AUTORA:
Opisz metryki jakości danych śledzone w monitoringu.
Jak różni się monitoring danych wejściowych vs. wyjściowych?
-->

Monitorowane metryki jakości danych:
- Missing rate per zmienna
- Out-of-range values
- Data freshness (aktualność danych)
- Spójność z historycznym profilem

---

### 1.5 Drift Monitoring (Kategoria C/D)

<!-- PROMPT DLA AUTORA:
Opisz metodologię detection driftu dla modeli ML.
Jakie biblioteki / narzędzia są używane (Evidently, custom)?
Jaka jest różnica między feature drift a concept drift?
-->

Dla modeli ML obowiązkowe jest monitorowanie:

**Feature drift:** Zmiana rozkładu zmiennych wejściowych
- Metoda: [PLACEHOLDER: np. PSI per feature, KS test, chi2 test]
- Próg: [PLACEHOLDER]

**Concept drift / Prediction drift:** Zmiana rozkładu wyników modelu
- Metoda: [PLACEHOLDER]
- Próg: [PLACEHOLDER]

---

## 2. Częstotliwość Monitoringu

<!-- PROMPT DLA AUTORA:
Uzupełnij wymaganą częstotliwość dla każdego Tiera.
Uwzględnij częstotliwość automatyczną vs. raportowaną do komitetu.
-->

| Tier | Monitoring automatyczny | Raport do MRM | Raport do Komitetu |
|------|------------------------|---------------|-------------------|
| Tier 1 | Dzienny / Tygodniowy | Miesięczny | Kwartalny |
| Tier 2 | Miesięczny | Kwartalny | Semi-roczny |
| Tier 3 | Kwartalny | Roczny | Roczny |

---

## 3. Monitoring Plan — Wymagana Zawartość

<!-- PROMPT DLA AUTORA:
Opisz obowiązkową zawartość Monitoring Plan wymaganego przed wdrożeniem.
Powiąż z szablonem Monitoring Plan.
-->

Monitoring Plan (wymagany przed Gate 7) musi zawierać:
1. Identyfikator modelu (Model ID)
2. Lista metryk z definicjami
3. Źródła danych dla monitoringu
4. Progi alarmowe i krytyczne per metryka
5. Częstotliwość monitoringu
6. Odpowiedzialny za monitoring
7. Trigger events i eskalacja
8. Schemat raportowania
9. Data startu monitoringu

---

## 4. Trigger Events i Eskalacja

<!-- PROMPT DLA AUTORA:
Opisz kompletną listę trigger events i wymagane działania.
-->

| Trigger | Klasa | Działanie | Termin |
|---------|-------|-----------|--------|
| PSI > 0.25 | Krytyczny | Wstrzymanie modelu + eskalacja MRM | Natychmiastowa |
| PSI 0.1–0.25 | Alarmowy | Pogłębiona analiza + MRM | 5 dni |
| Gini/AUC degradacja > [PLACEHOLDER]% | Krytyczny | Re-walidacja | 30 dni |
| Brak raportu w terminie | Procesowy | Eskalacja do Model Ownera | +5 dni |
| Missing rate > [PLACEHOLDER]% | Alarmowy | IT/Data investigation | 5 dni |

---

## 5. Annual Review

<!-- PROMPT DLA AUTORA:
Opisz zakres i wymagania Annual Review.
Czym różni się Annual Review od regular monitoring?
-->

Annual Review jest formalnym przeglądem stanu modelu, wykraczającym poza bieżące raporty.

Zakres: [Do uzupełnienia — patrz Guide Etap 5.8]

---

## Powiązane Dokumenty

- [Guide — Etap 5.8: Monitoring](../guide/05_etapy/08_monitoring_przeglad.md)
- [Monitoring Plan Template](../templates/)
- [Monitoring Report Template](../templates/)
- [Annual Review Template](../templates/)
