# TMPL-005: Wniosek o Zmianę Modelu

> **Kiedy używać:** Przy każdej planowanej zmianie modelu produkcyjnego (Etap 12)  
> **Kto wypełnia:** Data Scientist + Model Owner  
> **Cel:** Dokumentacja i ścieżka zatwierdzenia zmiany w modelu

---

# Wniosek o Zmianę Modelu (Model Change Request)

**ID modelu:** `[ID z inwentarza]`  
**Tytuł modelu:** `[Nazwa]`  
**Data wniosku:** `[RRRR-MM-DD]`  
**Wnioskujący DS:** `[Imię i nazwisko]`  
**Model Owner:** `[Imię i nazwisko]`  
**Numer zmiany:** `[MCR-RRRR-NNN]`

---

## 1. Opis Zmiany

**Streszczenie zmiany (1-2 zdania):**  
`[Krótki opis co i dlaczego chcemy zmienić]`

**Szczegółowy opis:**  
`[Pełny opis zmian — co dokładnie się zmienia w metodologii/danych/kodzie]`

**Uzasadnienie:**  
`[Dlaczego zmiana jest potrzebna? Np. degradacja performance, nowe dane, zmiana regulacyjna]`

---

## 2. Klasyfikacja Zmiany

**Propozycja klasyfikacji:**

`[ ] Minor — zmiana techniczna bez wpływu na wyniki`  
`[ ] Significant — recalibration lub ograniczone zmiany`  
`[ ] Material — zmiana metodologii lub zakresu`

**Uzasadnienie klasyfikacji:**  
`[Dlaczego tak sklasyfikowałeś zmianę?]`

> ⚠️ **[REGULACYJNE]** Jeśli model regulacyjny: czy zmiana wymaga notyfikacji nadzorcy?  
> `[ ] Tak — konsultacja z Compliance wymagana [ ] Nie [ ] Do wyjaśnienia`

---

## 3. Wpływ Zmiany

| Aspekt | Ocena | Opis |
|---|---|---|
| Wpływ na wyniki modelu | Wysoki / Średni / Niski / Brak | |
| Wpływ na dokumentację | Wymaga aktualizacji / Brak | |
| Wpływ na plan monitoringu | Wymaga aktualizacji / Brak | |
| Wpływ na systemy powiązane | Tak / Nie | |

---

## 4. Wymagana Dokumentacja

| Dokument | Czy wymaga aktualizacji? |
|---|---|
| MDD | ☐ Tak ☐ Nie |
| Assumptions Register | ☐ Tak ☐ Nie |
| Plan Monitoringu | ☐ Tak ☐ Nie |
| Change Log | ☐ Tak — obowiązkowe |

---

## 5. Wymagana Ścieżka Zatwierdzeń

| Krok | Odpowiedzialny | Status | Data |
|---|---|---|---|
| Code review | Peer DS | ☐ | |
| Testy regresji | DS | ☐ | |
| Model Owner approval | Model Owner | ☐ | |
| MRM review | MRM | ☐ | |
| Walidacja (jeśli material) | Validator | ☐ | |
| MRC approval (jeśli material) | MRC | ☐ | |

---

## 6. Termin Wdrożenia

**Planowany termin:** `[RRRR-MM-DD]`  
**Uzasadnienie pilności:** `[jeśli dotyczy]`

---

## Podpisy

| Rola | Decyzja | Podpis | Data |
|---|---|---|---|
| Model Owner | ☐ Zatwierdzone ☐ Odrzucone | | |
| MRM | ☐ Zatwierdzone ☐ Odrzucone | | |
| MRC (jeśli material) | ☐ Zatwierdzone ☐ Odrzucone | | |

---

*Szablon v0.5 | Powiązany standard: STD-006 | Powiązana procedura: PROC-004*
