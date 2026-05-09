# TMPL-003: Raport Walidacji Modelu

> **Kiedy używać:** Po przeprowadzeniu niezależnej walidacji (Etap 7)  
> **Kto wypełnia:** Validator / MRM  
> **Cel:** Udokumentowanie wyników i wniosków z niezależnej walidacji modelu

---

# Raport Walidacji

**Tytuł modelu:** `[Pełna nazwa modelu]`  
**ID modelu:** `[ID z inwentarza]`  
**Wersja modelu (walidowanego):** `[wersja]`  
**Walidator:** `[Imię i nazwisko / Jednostka]`  
**Data raportu:** `[RRRR-MM-DD]`  
**Wersja raportu:** `[x.x]`

---

## Podsumowanie (Executive Summary)

**Ogólna ocena:** `[ ] Zatwierdzone bez warunków [ ] Zatwierdzone warunkowo [ ] Nie zatwierdzone`

**Liczba findings:**  
- 🔴 Krytyczne: `[N]`  
- 🟡 Poważne: `[N]`  
- 🟢 Informacyjne: `[N]`

**Kluczowe wnioski:**  
[Max 1 strona — główne wnioski z walidacji]

---

## 1. Zakres Walidacji

[Opis co było przedmiotem walidacji, co było poza zakresem i dlaczego]

**Dokumenty przejrzane:**
- [ ] MDD (wersja: `[x.x]`, data: `[data]`)
- [ ] Assumptions Register
- [ ] Data Dictionary
- [ ] Kod modelu (Git tag: `[tag]`)
- [ ] Test Results Report
- [ ] Plan Monitoringu
- [ ] Inne: `[wymień]`

---

## 2. Przegląd Konceptualny

### 2.1 Adekwatność metodologii

[Ocena: czy metodologia jest adekwatna do problemu?]

**Ocena:** `[ ] Adekwatna [ ] Adekwatna z zastrzeżeniami [ ] Nieadekwatna`

### 2.2 Jakość danych

[Ocena procesu przygotowania danych]

### 2.3 Jakość dokumentacji

[Ocena kompletności i rzetelności dokumentacji]

---

## 3. Niezależne Testy Ilościowe

> ✍️ **[DO UZUPEŁNIENIA]** Wypełnić sekcje testów zgodnie z STD-003 i typem modelu.

### 3.1 Discriminatory Power (dla supervised)

| Test | Wynik DS | Wynik Walidatora | Ocena |
|---|---|---|---|
| GINI | | | |
| AUC | | | |

### 3.2 Stabilność

| Test | Wynik DS | Wynik Walidatora | Ocena |
|---|---|---|---|
| PSI | | | |

### 3.3 Benchmark Comparison

| Model | GINI | Opis |
|---|---|---|
| Walidowany model | | |
| Benchmark | | |

---

## 4. Findings

### Finding 1

| Element | Treść |
|---|---|
| **ID Finding** | F-001 |
| **Kategoria** | `[ ] Krytyczne [ ] Poważne [ ] Informacyjne` |
| **Tytuł** | `[krótki opis]` |
| **Opis** | `[szczegółowy opis obserwacji i ryzyka]` |
| **Rekomendacja** | `[co powinien zrobić Developer / Model Owner]` |
| **Status** | `[ ] Otwarte [ ] Zaadresowane [ ] Akceptowane (ryzyko)` |
| **Termin** | `[RRRR-MM-DD]` |

*(Powiel blok dla każdego finding)*

---

## 5. Ocena Planu Monitoringu

[Ocena adekwatności planu monitoringu]

**Ocena:** `[ ] Adekwatny [ ] Wymaga uzupełnienia [ ] Nieadekwatny`

---

## 6. Rekomendacja Końcowa

**Decyzja:**  
`[ ] Zatwierdzone do wdrożenia bez warunków`  
`[ ] Zatwierdzone do wdrożenia warunkowo (patrz warunki)`  
`[ ] Niezatwierdzone — wymagana praca`

**Warunki (jeśli conditional approval):**
[Opis warunków]

**Ograniczenia stosowania (jeśli dotyczy):**
[Opis ograniczeń]

---

## Podpisy

| Rola | Imię i Nazwisko | Data |
|---|---|---|
| Walidator | | |
| Kierownik Walidacji / MRM | | |

---

*Szablon v0.5 | Powiązany standard: STD-003 | Powiązana procedura: PROC-003*
