# STD-001: Standard Rozwoju Modeli

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet — wymaga uzupełnienia treścią merytoryczną  
> **Powiązany rozdział przewodnika:** Etapy 3, 4, 5, 6

---

## Cel standardu

Ten standard określa minimalne wymagania dla procesu rozwoju modeli, obejmując przygotowanie danych, projektowanie, budowę, testowanie oraz dokumentację techniczną.

---

## Zakres

Standard dotyczy wszystkich modeli zarejestrowanych w inwentarzu, z różnicowaniem wymagań per tier.

---

## 1. Wymagania dotyczące środowiska i kodu

> ✍️ **[DO UZUPEŁNIENIA]** Opisać wymagania dotyczące:
> - Wersjonowania kodu (Git — obligatoryjne narzędzie i standard branching)
> - Środowisk (dev / staging / prod) i ich separacji
> - Zarządzania zależnościami (requirements.txt, conda env, Docker)
> - Standardów kodowania (PEP 8 lub inny przyjęty standard)
> - Code review procesu

**Minimalne wymagania:**
- [ ] Kod modelu w repozytorium Git od pierwszego dnia projektu
- [ ] Oddzielne branche dla development / release
- [ ] Code review przez co najmniej jednego peer DS przed dokumentacją
- [ ] Zapis wersji bibliotek (requirements.txt lub równorzędny)
- [ ] Seed losowy zapisany i udokumentowany

---

## 2. Wymagania dotyczące danych

> ✍️ **[DO UZUPEŁNIENIA]** Opisać wymagania dotyczące:
> - Data lineage (skąd dane, jak przetworzone)
> - Train/validation/test split (zasady podziału, time-based split)
> - Handling missing values, outliers
> - Feature engineering standards
> - Archiwizacja zbiorów treningowych

> 📋 **[SUPERVISED]** Dodatkowe wymagania:
> - Definicja target variable musi być pisemnie zatwierdzona
> - Time-based split jako domyślne podejście (unikanie data leakage)
> - Dokumentacja obserwacji z przyszłości (look-ahead bias prevention)

> 🔬 **[UNSUPERVISED]** Dodatkowe wymagania:
> - Dokumentacja kryterium klasteryzacji i celu biznesowego
> - Outlier treatment i jego wpływ na klastry musi być przeanalizowany

---

## 3. Wymagania dotyczące eksperymentów

> ✍️ **[DO UZUPEŁNIENIA]** Opisać wymagania dotyczące:
> - Experiment tracking (MLflow, W&B lub inne narzędzie)
> - Dokumentowania próbowanych podejść i ich wyników
> - Selekcji modelu ostatecznego z uzasadnieniem

---

## 4. Wymagania dotyczące testów

> ✍️ **[DO UZUPEŁNIENIA]** Opisać wymagania dotyczące:
> - Unit tests dla kodu modelarskiego
> - Integration tests
> - Performance tests (backtesting, out-of-time)
> - Minimalnych progów performance

---

## 5. Specyfika per typ modelu

> ⚠️ **[REGULACYJNE]** — wymagania dodatkowe:
> ✍️ **[DO UZUPEŁNIENIA]** Dodać wymagania specyficzne dla modeli regulacyjnych per typ (PD, LGD, IFRS 9, stress-testy).

> 📋 **[SUPERVISED]** — wymagania dodatkowe:
> ✍️ **[DO UZUPEŁNIENIA]** Dodać wymagania dla modeli supervised (label quality, leakage prevention, explainability).

> 🔬 **[UNSUPERVISED]** — wymagania dodatkowe:
> ✍️ **[DO UZUPEŁNIENIA]** Dodać wymagania dla modeli unsupervised (cluster validation, stability).

---

## Powiązania

- [Rozdział 5: Etapy Cyklu Życia](../00_guide/05_etapy_cyklu_zycia.md)
- [STD-002: Standard Dokumentacji](./STD-002_dokumentacja.md)
- [PROC-002: Procedura Oceny Danych](../02_procedures/PROC-002_dane_i_ocena.md)
