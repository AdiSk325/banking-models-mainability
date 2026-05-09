# STD-006: Standard Zarządzania Zmianą Modeli

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet  
> **Powiązany rozdział przewodnika:** Etap 12

---

## Cel standardu

Standard definiuje klasyfikację zmian w modelach produkcyjnych oraz wymagane ścieżki zatwierdzania, dokumentacji i weryfikacji dla każdej kategorii zmiany.

---

## 1. Definicja Zmiany

Zmiana modelu to każda modyfikacja komponentów modelu, która może wpłynąć na jego wyniki, zachowanie lub zgodność. Obejmuje:
- Zmiany metodologii lub algorytmu
- Zmiany danych wejściowych (nowe zmienne, usunięcie zmiennych)
- Aktualizację parametrów i wag modelu
- Zmiany kodu produkcyjnego
- Zmiany w preprocessing / feature engineering
- Zmiany w zakresie stosowania modelu

---

## 2. Klasyfikacja Zmian

### Zmiana Materialna (Major / Material Change)
**Definicja:** Zmiana o znaczącym wpływie na wyniki lub metodologię modelu.

**Przykłady:**
- Zmiana algorytmu (np. regresja → gradient boosting)
- Dodanie/usunięcie istotnych zmiennych (> X% impact)
- Zmiana zakresu stosowania modelu
- Zmiana target variable
- Re-development na nowych danych (> Y lat różnicy)

**Wymagania:**
- 🔴 Pełna rewalidacja
- 🔴 Nowe zatwierdzenie governance (MRC)
- 🔴 Aktualizacja MDD
- 🔴 Aktualizacja inwentarza

> ⚠️ **[REGULACYJNE]** Material change dla modeli regulacyjnych może wymagać notyfikacji lub zatwierdzenia przez KNF/ECB. DS/MRM musi skonsultować się z Compliance przed wdrożeniem.

---

### Zmiana Znacząca (Significant Change)
**Definicja:** Zmiana o ograniczonym wpływie metodycznym, ale wymagająca formalnego przeglądu.

**Przykłady:**
- Recalibration parametrów modelu (nowa próbka)
- Drobne zmiany feature engineering (bez zmiany logiki)
- Aktualizacja danych (nowy rocznik bez zmiany metodologii)

**Wymagania:**
- 🟡 Uproszczona walidacja (focused review)
- 🟡 Zatwierdzenie MRM + Model Owner
- 🔴 Aktualizacja MDD (sekcja changelog)
- 🔴 Aktualizacja inwentarza

---

### Zmiana Nieistotna (Minor Change)
**Definicja:** Zmiana techniczna bez wpływu na wyniki modelu.

**Przykłady:**
- Poprawki błędów technicznych (bug fixes) niezmienające wyników
- Refactoring kodu bez zmiany logiki
- Aktualizacja dokumentacji
- Zmiany infrastrukturalne (bez wpływu na model)

**Wymagania:**
- 🟢 Code review i test regresji
- 🟢 Zatwierdzenie przez Team Lead DS lub Model Owner
- 🔴 Aktualizacja change log w dokumentacji
- 🔴 Aktualizacja inwentarza

---

## 3. Change Management Process

```
Identyfikacja potrzeby zmiany
         ↓
Klasyfikacja zmiany (DS + MRM)
         ↓
    Minor? → Uproszczona ścieżka (code review + approval)
    Significant? → Focused review + MRM approval
    Material? → Pełna ścieżka (rewalidacja + MRC)
         ↓
Implementacja i testy
         ↓
Dokumentacja (change log, MDD update)
         ↓
Aktualizacja inwentarza
```

---

## 4. Change Log — Wymagania

Każda zmiana musi być udokumentowana w change logu z:
- Data zmiany
- Typ zmiany (material/significant/minor)
- Opis zmiany
- Uzasadnienie
- Autor
- Zatwierdzający
- Data zatwierdzenia

---

## Powiązania

- [Rozdział 5: Etap 12 — Zarządzanie Zmianą](../00_guide/05_etapy_cyklu_zycia.md#512-etap-12-zarządzanie-zmianą)
- [TMPL-005: Wniosek o Zmianę](../03_templates/TMPL-005_wniosek_o_zmiane.md)
