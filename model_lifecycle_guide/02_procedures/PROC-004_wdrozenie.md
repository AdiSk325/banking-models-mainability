# PROC-004: Procedura Wdrożenia Modelu

> **Typ dokumentu:** Procedura (Poziom 3)  
> **Status:** 🔄 Szkielet  
> **Powiązany etap:** Etap 9

---

## Cel procedury

Opisuje działania wymagane do bezpiecznego wdrożenia zatwierdzonego modelu do środowiska produkcyjnego.

---

## Warunki wstępne (przed rozpoczęciem procedury)

> 🔴 Wszystkie poniższe warunki muszą być spełnione przed wdrożeniem:
> - [ ] Governance approval (BG-07) uzyskane
> - [ ] Findings walidacyjne zaadresowane lub plan zaakceptowany
> - [ ] Plan monitoringu zatwierdzony
> - [ ] Rollback plan przygotowany

---

## Krok 1: Przygotowanie środowiska i kodu

**Odpowiedzialny:** IT/MLOps + DS

**Działania:**
- [ ] Potwierdź, że kod w produkcji = kod zatwierdzony (hash/tag Git)
- [ ] Przygotuj i przetestuj środowisko produkcyjne
- [ ] Zweryfikuj dostępność wymaganych danych w produkcji
- [ ] Przeprowadź testy wydajnościowe (latency, throughput)

---

## Krok 2: User Acceptance Testing (UAT)

**Odpowiedzialny:** Model User + DS + IT

**Działania:**
- [ ] Przygotuj przypadki testowe UAT
- [ ] Przeprowadź testy z udziałem Model Userów
- [ ] Udokumentuj wyniki UAT
- [ ] Uzyskaj UAT Sign-off od Model Ownera

---

## Krok 3: Parallel Run (jeśli zastępujemy stary model)

**Działania:**
- [ ] Uruchom nowy i stary model równolegle przez [X] tygodni
- [ ] Porównaj wyniki obu modeli
- [ ] Udokumentuj różnice i wyjaśnij rozbieżności
- [ ] Uzyskaj akceptację Model Ownera do odłączenia starego modelu

---

## Krok 4: Go-Live

**Działania:**
- [ ] Wypełnij Go-Live Checklist
- [ ] Przełącz ruch produkcyjny na nowy model
- [ ] Monitoruj intensywnie przez pierwsze [X] dni
- [ ] Potwierdź poprawność działania

---

## Krok 5: Finalizacja wdrożenia

**Działania:**
- [ ] Zaktualizuj inwentarz modeli (status: Production, data wdrożenia)
- [ ] Uruchom plan monitoringu (dostosuj harmonogram)
- [ ] Przekaż dokumentację operacyjną do IT/MLOps
- [ ] Poinformuj wszystkich stakeholders o go-live

---

## Go-Live Checklist

| Pozycja | Status |
|---|---|
| Governance approval | ☐ |
| UAT Sign-off | ☐ |
| Performance tests OK | ☐ |
| Rollback plan gotowy | ☐ |
| Monitoring uruchomiony | ☐ |
| Inwentarz zaktualizowany | ☐ |
| Dokumentacja operacyjna przekazana | ☐ |
| Model Owner powiadomiony | ☐ |

---

## Powiązania

- [STD-008: Standard Wdrożenia](../01_supporting_standards/STD-008_wdrozenie.md)
- [Rozdział 5: Etap 9](../00_guide/05_etapy_cyklu_zycia.md#59-etap-9-wdrożenie)
