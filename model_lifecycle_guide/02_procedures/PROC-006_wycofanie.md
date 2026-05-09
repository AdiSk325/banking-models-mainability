# PROC-006: Procedura Wycofania Modelu

> **Typ dokumentu:** Procedura (Poziom 3)  
> **Status:** 🔄 Szkielet  
> **Powiązany etap:** Etap 13

---

## Cel procedury

Opisuje działania wymagane do bezpiecznego i udokumentowanego wycofania modelu z produkcji oraz archiwizacji dokumentacji.

---

## Kiedy model powinien być wycofany?

Model powinien być wycofany gdy:
- Nowy, lepszy model jest dostępny i gotowy do wdrożenia
- Model nie spełnia minimalnych wymagań performance pomimo prób recalibration
- Zmiana regulacyjna wymusza wycofanie lub zastąpienie
- Proces biznesowy, który obsługiwał model, został zlikwidowany
- Koszt utrzymania przekracza wartość

---

## Krok 1: Decyzja o wycofaniu

**Odpowiedzialny:** Model Owner + MRM

**Działania:**
- [ ] Przygotuj uzasadnienie decyzji o wycofaniu (Retirement Decision Document)
- [ ] Zidentyfikuj model zastępczy lub procedurę alternatywną
- [ ] Uzyskaj formalne zatwierdzenie wycofania przez MRC (dla Tier 1/2)
- [ ] Ustal harmonogram wycofania

---

## Krok 2: Plan Transition

**Działania:**
- [ ] Zidentyfikuj wszystkich użytkowników i systemy zależne od modelu
- [ ] Zaplanuj komunikację do użytkowników
- [ ] Ustanów parallel run z modelem zastępczym (jeśli dotyczy)
- [ ] Zaplanuj okres przejściowy

---

## Krok 3: Wycofanie z produkcji

**Odpowiedzialny:** IT/MLOps + Model Owner

**Działania:**
- [ ] Odłącz model od systemów produkcyjnych
- [ ] Potwierdź, że żaden system nie korzysta z wycofanego modelu
- [ ] Zaktualizuj inwentarz modeli (status: Retired, data wycofania)

---

## Krok 4: Archiwizacja

**Działania:**
- [ ] Archiwizuj kod modelu (versioned, z tagiem)
- [ ] Archiwizuj dokumentację (MDD, raporty walidacji, monitoring history)
- [ ] Archiwizuj approval records i change log
- [ ] Zachowaj archiwum przez wymagany okres retencji

> ⚠️ **[REGULACYJNE]** Dla modeli regulacyjnych — okres archiwizacji i wymagania archiwizacyjne mogą być określone regulacyjnie (np. 10 lat). Skonsultuj się z Compliance przed archiwizacją.

---

## Krok 5: Lessons Learned

**Działania (zalecane):**
- [ ] Przygotuj podsumowanie lessons learned z życia modelu
- [ ] Udokumentuj co działało dobrze i co można poprawić
- [ ] Podziel się wnioskami z zespołem DS

---

## Powiązania

- [TMPL-006: Formularz Wycofania](../03_templates/TMPL-006_wycofanie_modelu.md)
- [STD-005: Inwentarz Modeli](../01_supporting_standards/STD-005_inwentarz.md)
- [Rozdział 5: Etap 13](../00_guide/05_etapy_cyklu_zycia.md#513-etap-13-wycofanie-i-archiwizacja)
