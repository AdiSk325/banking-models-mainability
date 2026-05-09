# TMPL-006: Formularz Wycofania Modelu

> **Kiedy używać:** Przy wycofaniu modelu z produkcji (Etap 13)  
> **Kto wypełnia:** Data Scientist + Model Owner  
> **Cel:** Dokumentacja decyzji o wycofaniu i procesu archiwizacji

---

# Formularz Wycofania Modelu (Model Retirement Record)

**ID modelu:** `[ID z inwentarza]`  
**Tytuł modelu:** `[Nazwa]`  
**Data wniosku:** `[RRRR-MM-DD]`  
**Data planowanego wycofania:** `[RRRR-MM-DD]`  
**DS:** `[Imię i nazwisko]`  
**Model Owner:** `[Imię i nazwisko]`

---

## 1. Uzasadnienie Wycofania

**Powód wycofania:**  
`[ ] Nowy model zastępczy gotowy`  
`[ ] Degradacja performance — bez możliwości naprawy`  
`[ ] Zmiana regulacyjna`  
`[ ] Wycofanie procesu biznesowego`  
`[ ] Inne: [opisz]`

**Szczegółowe uzasadnienie:**  
`[Opis]`

---

## 2. Model Zastępczy

**Czy istnieje model zastępczy?**  
`[ ] Tak — ID modelu zastępczego: [ID]`  
`[ ] Nie — alternatywa: [opisz co zastępuje model]`  
`[ ] Nie — model nie będzie zastępowany (uzasadnienie: [opis])`

---

## 3. Plan Transition

**Lista systemów i procesów korzystających z modelu:**
| System / Proces | Status migracji | Odpowiedzialny | Data |
|---|---|---|---|
| | ☐ Gotowe ☐ W trakcie ☐ Nie dotyczy | | |

**Parallel run (jeśli zastępujemy modelem):**  
`[ ] Tak — od [data] do [data]`  
`[ ] Nie — uzasadnienie: [opis]`

---

## 4. Checklist Wycofania

| Czynność | Status | Data |
|---|---|---|
| Decyzja o wycofaniu zatwierdzona (MRC/Model Owner) | ☐ | |
| Wszystkie systemy odłączone od modelu | ☐ | |
| Parallel run zakończony (jeśli dotyczy) | ☐ | |
| Kod zarchiwizowany (Git tag + backup) | ☐ | |
| Dokumentacja zarchiwizowana | ☐ | |
| Inwentarz zaktualizowany (status: Retired) | ☐ | |
| Użytkownicy poinformowani | ☐ | |
| Lessons Learned udokumentowane | ☐ | |

---

## 5. Archiwizacja

**Lokalizacja archiwum kodu:** `[ścieżka / link]`  
**Lokalizacja archiwum dokumentacji:** `[ścieżka / link]`  
**Okres retencji:** `[X lat — zgodnie z polityką / wymogiem regulacyjnym]`  
**Termin przeglądu archiwum:** `[RRRR-MM-DD]`

---

## 6. Lessons Learned (opcjonalne)

`[Co działało dobrze w lifecycle tego modelu? Co można zrobić lepiej następnym razem?]`

---

## Podpisy

| Rola | Podpis | Data |
|---|---|---|
| Model Owner | | |
| MRM | | |
| MRC (Tier 1/2) | | |

---

*Szablon v0.5 | Powiązana procedura: PROC-006*
