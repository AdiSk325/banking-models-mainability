# TMPL-002: Model Development Document (MDD)

> **Kiedy używać:** Tworzony podczas developmentu, finalizowany przed walidacją (Etap 6)  
> **Kto wypełnia:** Data Scientist  
> **Cel:** Pełna dokumentacja metodyczna i techniczna modelu

---

## Instrukcja wypełnienia

Wypełnij każdą sekcję. Sekcje oznaczone `🔴` są obowiązkowe. Sekcje `🟡` są zalecane (mogą być pominięte z uzasadnieniem). Nie usuwaj struktury — pozostaw sekcję z adnotacją "N/A z uzasadnieniem" jeśli nie dotyczy.

---

# Model Development Document

**Tytuł modelu:** `[Pełna nazwa modelu]`  
**ID modelu:** `[ID z inwentarza]`  
**Wersja dokumentu:** `[x.x]`  
**Data dokumentu:** `[RRRR-MM-DD]`  
**Autor:** `[Imię i nazwisko DS]`  
**Model Owner:** `[Imię i nazwisko]`  
**Status:** `[Draft / Under Review / Final]`

---

## Historia zmian dokumentu

| Wersja | Data | Opis | Autor |
|---|---|---|---|
| 0.1 | | Inicjalny draft | |
| | | | |

---

## 1. 🔴 Streszczenie Wykonawcze

*Max 1 strona. Dla czytelnika biznesowego. Opisz cel, metodologię, wyniki kluczowe i ograniczenia.*

[Streszczenie — do wypełnienia]

---

## 2. 🔴 Kontekst Biznesowy i Regulacyjny

### 2.1 Problem biznesowy
[Opis problemu do rozwiązania]

### 2.2 Cel i zastosowanie modelu
[Co model przewiduje, jak jest używany]

### 2.3 Populacja docelowa
[Kogo / czego dotyczy model]

### 2.4 Powiązania regulacyjne
> ⚠️ **[REGULACYJNE — wypełnij jeśli dotyczy]**  
[Jakie regulacje dotyczą tego modelu, jak model je spełnia]

---

## 3. 🔴 Dokumentacja Danych

### 3.1 Źródła danych
| Źródło | Opis | Zakres | Właściciel |
|---|---|---|---|
| | | | |

### 3.2 Zakres próbki

- **Obserwacja (obserwation window):** `[od — do]`
- **Outcome window:** `[od — do]`
- **Liczba obserwacji (train):** `[N]`
- **Liczba obserwacji (test/OOT):** `[N]`

> 📋 **[SUPERVISED]** Opisz time-based split i uzasadnienie.

### 3.3 Jakość danych

[Wyniki oceny jakości, % braków, outliers, transformacje]

### 3.4 Data Dictionary (skrócony)

| Zmienna | Opis | Typ | Źródło | Odsetek braków |
|---|---|---|---|---|
| | | | | |

*Pełny słownik jako aneks lub osobny plik.*

---

## 4. 🔴 Metodologia

### 4.1 Wybrany algorytm/podejście

[Nazwa i opis]

### 4.2 Uzasadnienie wyboru

[Dlaczego ten algorytm? Jakie alternatywy były rozważane?]

| Alternatywa | Powód odrzucenia |
|---|---|
| | |

### 4.3 Feature Engineering

[Opis najważniejszych transformacji i zmiennych wytworzonych]

### 4.4 Selekcja zmiennych

[Metoda selekcji, liczba finalna zmiennych, top zmienne]

---

## 5. 🔴 Trening i Selekcja Modelu

### 5.1 Procedura treningu

[Opis, w tym CV schema, split strategy]

### 5.2 Hiperparametry — finalny model

| Parametr | Wartość |
|---|---|
| | |

### 5.3 Wersja modelu i środowisko

- **Wersja kodu (Git tag):** `[tag]`
- **Python / R version:** `[x.x]`
- **Kluczowe biblioteki:** `[nazwa==wersja, ...]`
- **Seed losowy:** `[N]`

---

## 6. 🔴 Wyniki Performance

### 6.1 Metryki kluczowe (zbiór testowy / out-of-time)

| Metryka | Wartość (Test) | Wartość (OOT) | Benchmark | Pass? |
|---|---|---|---|---|
| GINI/AUC | | | | |
| [Inna metryka] | | | | |

### 6.2 Backtesting / Out-of-Time Validation

[Opis i wyniki backtestingu]

### 6.3 Analiza podpopulacji

[Wyniki per segment populacji]

### 6.4 Stabilność (PSI)

[Wyniki PSI lub inne miary stabilności]

---

## 7. 🔴 Explainability

### 7.1 Feature Importance (globalna)

[Top 10 zmiennych z kierunkiem wpływu]

### 7.2 SHAP lub inne wyjaśnienia

> 📋 **[SUPERVISED — obowiązkowe dla Tier 1/2]**  
[Wyniki SHAP — globalne summary]

> 🔬 **[UNSUPERVISED — obowiązkowe]**  
[Profil każdego segmentu — tabela lub opis]

---

## 8. 🔴 Założenia i Ograniczenia

### 8.1 Założenia modelu

| # | Założenie | Uzasadnienie | Ryzyko przy naruszeniu |
|---|---|---|---|
| 1 | | | |

### 8.2 Ograniczenia

[Znane ograniczenia — kiedy model działa gorzej lub nie powinien być stosowany]

---

## 9. 🔴 Plan Monitoringu (skrócony)

*Pełny plan: TMPL-004*

| Metryka | Próg ostrzeżenia | Próg krytyczny | Częstotliwość |
|---|---|---|---|
| PSI | > 0.10 | > 0.25 | Miesięcznie |
| [Inna] | | | |

---

## Aneksy

- A: Pełny Data Dictionary
- B: Wyniki eksperymentów (link do MLflow lub plik)
- C: Code repository (link do Git)
- D: [Inne]

---

*Szablon v0.5 | Powiązany standard: STD-002 | Data Scientista: [imię]]*
