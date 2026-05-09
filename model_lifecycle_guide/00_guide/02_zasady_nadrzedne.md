# Rozdział 2: Zasady Nadrzędne (Guiding Principles)

> **Status:** 🔄 Szkielet — wymaga rozwinięcia każdej zasady z przykładami praktycznymi  
> **Priorytet uzupełnienia:** Wysoki

---

## 2.1 Wprowadzenie

Zasady nadrzędne stanowią fundament całego frameworku pracy z modelami. Wszystkie decyzje procesowe, wymagania etapów i reguły governance wynikają z tych zasad lub powinny być z nimi spójne.

> 🔴 **OBOWIĄZKOWE** — Znajomość i przestrzeganie zasad nadrzędnych jest wymagane od wszystkich osób uczestniczących w cyklu życia modelu.

---

## 2.2 Lista Zasad Nadrzędnych

### Zasada 1: Podejście oparte na ryzyku (Risk-Based Approach)

**Definicja:**  
Poziom rygoru wymagań, dokumentacji, walidacji i nadzoru jest proporcjonalny do ryzyka i materiality modelu. Modele o wyższym wpływie finansowym, decyzyjnym lub regulacyjnym wymagają bardziej intensywnych kontroli.

**Co to oznacza dla Data Scientistów:**
- Tier modelu determinuje zakres wymaganych artefaktów i proces zatwierdzania
- Modele Tier 1 (wysokie ryzyko) = pełna walidacja, pełna dokumentacja, governance approval
- Modele Tier 3 (niskie ryzyko) = uproszczone wymagania, szybsza ścieżka wdrożenia

> ✍️ **[DO UZUPEŁNIENIA]** Dodać przykład konkretnego modelu regulacyjnego vs. eksperymentalnego i różnicę w wymaganiach.

---

### Zasada 2: Proporcjonalność (Proportionality)

**Definicja:**  
Wymagania i kontrole są dostosowane do charakteru i złożoności modelu. Prosta reguła decyzyjna nie podlega tym samym wymogom co model IRB dla portfela korporacyjnego.

**Co to oznacza dla Data Scientistów:**
- Klasyfikacja modelu (Tier 1/2/3) następuje na etapie inicjacji
- DS powinien potwierdzić tier z Model Ownerem przed rozpoczęciem developmentu
- Tier wpływa bezpośrednio na nakład pracy dokumentacyjnej i walidacyjnej

---

### Zasada 3: Odtwarzalność (Reproducibility)

**Definicja:**  
Każdy model i każdy wynik powinny być możliwe do odtworzenia niezależnie przez inną osobę na podstawie dostępnej dokumentacji, kodu i danych.

**Co to oznacza dla Data Scientistów:**
- Wersjonowanie kodu (Git) jest obowiązkowe od pierwszego dnia projektu
- Dane treningowe muszą być dokumentowane i archiwizowane
- Seeds losowe, wersje bibliotek i środowisko muszą być zapisane
- Notebooki eksploracyjne nie zastępują produkcyjnego kodu z testami

> ⚠️ **[REGULACYJNE]** Dla modeli regulacyjnych możliwość odtworzenia wyników jest wymagana przez regulatora i audyt wewnętrzny.

---

### Zasada 4: Identyfikowalność i ślad audytowy (Traceability)

**Definicja:**  
Każda decyzja, zmiana i wynik pracy musi być udokumentowana, datowana i przypisana do osoby odpowiedzialnej. Historia decyzji musi być możliwa do odtworzenia.

**Co to oznacza dla Data Scientistów:**
- Change log modelu jest obowiązkowy
- Decyzje metodyczne powinny być uzasadnione w dokumentacji
- Wyniki walidacji i zatwierdzenia są archiwizowane

---

### Zasada 5: Niezależne kwestionowanie (Independent Challenge)

**Definicja:**  
Każdy model przed wdrożeniem do produkcji musi przejść niezależną ocenę przez stronę niemającą interesu w potwierdzeniu wyników developmentu.

**Co to oznacza dla Data Scientistów:**
- Walidacja niezależna jest obowiązkowym etapem dla modeli Tier 1 i Tier 2
- DS nie może być równocześnie developerem i walidatorem swojego modelu
- Uwagi walidatora muszą być adresowane przed wdrożeniem

> ⚠️ **[REGULACYJNE]** SR 11-7 i EBA Guidelines wymagają niezależnej walidacji jako standardu. Dla modeli IRB i IFRS 9 niezależność walidatora podlega ocenie nadzorcy.

---

### Zasada 6: Dokumentacja by design

**Definicja:**  
Dokumentacja jest integralną częścią procesu budowy modelu, nie czynnością wykonywaną "po fakcie". Model bez odpowiedniej dokumentacji nie jest kompletnym produktem.

**Co to oznacza dla Data Scientistów:**
- Dokumentację piszesz na bieżąco, nie na koniec projektu
- Struktura dokumentacji jest znana na starcie projektu (→ TMPL-002)
- Dokumentacja jest wejściem do walidacji, nie jej efektem ubocznym

---

### Zasada 7: Rozdzielność obowiązków (Segregation of Duties)

**Definicja:**  
Różne role w procesie lifecycle modelu są rozdzielone, aby uniknąć konfliktu interesów i zapewnić system kontroli wzajemnych.

**Co to oznacza dla Data Scientistów:**
- DS buduje model, ale nie zatwierdza go do wdrożenia samodzielnie
- Model Owner zatwierdza zastosowanie, ale nie jest odpowiedzialny za metodologię
- Validator ocenia model niezależnie od developmentu
- IT/MLOps wdraża, ale nie decyduje o metodologii

---

### Zasada 8: Kontrolowane zarządzanie zmianą (Controlled Change)

**Definicja:**  
Zmiany w modelach produkcyjnych wymagają formalnej oceny, dokumentacji i zatwierdzenia proporcjonalnego do materialności zmiany.

**Co to oznacza dla Data Scientistów:**
- Nie wszystkie zmiany wymagają pełnej ścieżki — tiering zmian jest opisany w STD-006
- Minor changes (poprawki błędów, drobne parametry) ≠ material changes
- Material changes wymagają rewalidacji i nowego zatwierdzenia governance

> ✍️ **[DO UZUPEŁNIENIA]** Dodać przykłady minor vs. major changes dla różnych typów modeli.

---

### Zasada 9: Monitoring przez cały lifecycle (Monitoring Throughout Lifecycle)

**Definicja:**  
Monitoring nie jest czynnością wykonywaną "po wdrożeniu" — plan monitoringu jest planowany i projektowany na etapie developmentu.

**Co to oznacza dla Data Scientistów:**
- Przed wdrożeniem musisz mieć gotowy plan monitoringu (→ TMPL-004)
- Monitoring definiujesz podczas developmentu, gdy rozumiesz model najlepiej
- Trigger events dla review/recalibration muszą być z góry zdefiniowane

> 📋 **[SUPERVISED]** Dla modeli supervised zdefiniuj progi PSI, drift scores i degradacji performance z góry.

> 🔬 **[UNSUPERVISED]** Dla modeli unsupervised zdefiniuj miary stabilności segmentów i kryteria re-clusteringu.

---

### Zasada 10: Odpowiedzialność ludzka (Human Accountability)

**Definicja:**  
Każdy model ma zdefiniowanego właściciela (Model Owner) i twórcę (Developer). Automatyzacja decyzji nie zwalnia z odpowiedzialności za działanie modelu.

---

### Zasada 11: Zgodność regulacyjna (Regulatory Compliance)

**Definicja:**  
Wszystkie modele muszą być zgodne z obowiązującymi regulacjami. Wymagania regulacyjne mają pierwszeństwo przed efektywnością operacyjną.

> ⚠️ **[REGULACYJNE]** Model regulacyjny nie może być wdrożony bez spełnienia wszystkich wymagań nadzorczych, nawet jeśli opóźnia to harmonogram projektu.

---

## 2.3 Zastosowanie Zasad do Typów Modeli

| Zasada | Regulacyjne | Supervised | Unsupervised |
|---|---|---|---|
| Risk-Based Approach | 🔴 Tier 1 z reguły | 🟡 Zależny od use case | 🟡 Zależny od use case |
| Reproducibility | 🔴 Wymóg regulatora | 🔴 Standard | 🔴 Standard |
| Independent Challenge | 🔴 Pełna walidacja | 🟡 Tier-zależna | 🟡 Tier-zależna |
| Monitoring Throughout Lifecycle | 🔴 Ciągły monitoring | 🔴 Performance monitoring | 🟡 Stability monitoring |
| Controlled Change | 🔴 Notyfikacja nadzorcy | 🟡 Tier-zależna | 🟡 Tier-zależna |

---

## 2.4 Powiązane Dokumenty

- [Rozdział 3: Klasyfikacja Modeli](./03_klasyfikacja_modeli.md) — jak risk-based approach przekłada się na tiering
- [STD-001: Standard Rozwoju Modeli](../01_supporting_standards/STD-001_rozwoj_modeli.md) — praktyczne implikacje zasady Reproducibility
- [STD-003: Standard Walidacji](../01_supporting_standards/STD-003_walidacja.md) — praktyczne implikacje zasady Independent Challenge

---

*Poprzedni: [01 — Cel i Zakres](./01_cel_i_zakres.md) | Następny: [03 — Klasyfikacja Modeli](./03_klasyfikacja_modeli.md)*
