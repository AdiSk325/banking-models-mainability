# PROC-005: Procedura Monitoringu i Przeglądu Modelu

> **Typ dokumentu:** Procedura (Poziom 3)  
> **Status:** 🔄 Szkielet  
> **Powiązany etap:** Etapy 10–11

---

## Cel procedury

Opisuje działania wymagane do cyklicznego monitorowania modeli produkcyjnych oraz przeprowadzania przeglądów (periodic review / annual review).

---

## Część A: Cykliczny Monitoring

### Działania cykliczne

| Czynność | Tier 1 | Tier 2 | Tier 3 | Odpowiedzialny |
|---|---|---|---|---|
| Oblicz metryki monitoringowe | Miesięcznie | Kwartalnie | Półrocznie | DS |
| Sprawdź progi alertów | Miesięcznie | Kwartalnie | Półrocznie | DS |
| Raport do Model Ownera | Miesięcznie | Kwartalnie | Półrocznie | DS |
| Raport do MRM | Kwartalnie | Kwartalnie | Rocznie | Model Owner |

### Działania po przekroczeniu progu

> Gdy monitoring wykaże przekroczenie progu ostrzeżenia:
1. DS analizuje przyczynę w ciągu 5 dni roboczych
2. DS przekazuje wyniki analizy do Model Ownera
3. Model Owner decyduje o kolejnych krokach (akcja naprawcza / recalibration / review)
4. MRM jest informowany

> Gdy monitoring wykaże przekroczenie progu krytycznego:
1. DS i Model Owner eskalują do MRM niezwłocznie
2. MRM uruchamia formal review lub decyzję o zatrzymaniu modelu
3. Rozważane jest wstrzymanie decyzji modelarskich do czasu wyjaśnienia

---

## Część B: Periodic Review (Przegląd Cykliczny)

### Kiedy wymagany?
- Co roku (Annual Review) — dla modeli Tier 1 i Tier 2
- Co 2 lata — dla modeli Tier 3
- Po zdarzeniu trigger (przekroczenie progu, zmiana zewnętrzna)

### Zakres Annual Review

> ✍️ **[DO UZUPEŁNIENIA]** Opisać minimalny zakres rocznego przeglądu per tier.

**Elementy do sprawdzenia:**
- [ ] Wyniki monitoringowe za ostatni rok
- [ ] Czy model nadal jest fit-for-purpose? (czy problem biznesowy jest aktualny?)
- [ ] Czy dane treningowe nadal są reprezentatywne?
- [ ] Czy zaszły zmiany regulacyjne, które wpływają na model?
- [ ] Czy otwarte findings zostały zaadresowane?
- [ ] Czy tier modelu jest nadal adekwatny?
- [ ] Czy należy zaktualizować plan monitoringu?

### Decyzja po przeglądzie

Na podstawie przeglądu Model Owner i MRM podejmują jedną z decyzji:
- **Continue** — model pozostaje bez zmian
- **Recalibration** — aktualizacja parametrów (ścieżka minor/significant change)
- **Redevelopment** — nowy model (ścieżka material change, pełny cykl)
- **Retirement** — wycofanie modelu (→ PROC-006)

---

## Powiązania

- [STD-004: Standard Monitoringu](../01_supporting_standards/STD-004_monitoring.md)
- [TMPL-004: Plan Monitoringu](../03_templates/TMPL-004_plan_monitoringu.md)
- [PROC-006: Wycofanie](../02_procedures/PROC-006_wycofanie.md)
