# PROC-003: Procedura Walidacji Modelu

> **Typ dokumentu:** Procedura (Poziom 3)  
> **Status:** 🔄 Szkielet  
> **Powiązany etap:** Etap 7

---

## Cel procedury

Opisuje działania wymagane do przeprowadzenia niezależnej walidacji modelu — zarówno z perspektywy Data Scientista (przygotowanie do walidacji) jak i Walidatora (wykonanie walidacji).

---

## Część A: Przygotowanie przez Data Scientista

### Krok A1: Kompletność dokumentacji

**Sprawdź przed przekazaniem do walidacji:**
- [ ] MDD wypełniony kompletnie (wszystkie sekcje)
- [ ] Assumptions Register aktualny
- [ ] Data Dictionary kompletny
- [ ] Test Results Report gotowy
- [ ] Plan monitoringu przygotowany
- [ ] Kod w Git z tagiem wersji do walidacji

> 🔴 **OBOWIĄZKOWE** — Niekompletna dokumentacja jest powodem zwrotu do developmentu bez walidacji.

### Krok A2: Przygotowanie paczki walidacyjnej

**Przygotuj dla walidatora:**
- [ ] MDD + wszystkie aneksy
- [ ] Dostęp do kodu (read-only lub kopia)
- [ ] Dataset (lub próbka reprezentatywna zgodna z polityką danych)
- [ ] Wyniki eksperymentów (MLflow lub inne)
- [ ] Plan walidacji (uzgodniony wcześniej w etapie projektowania)
- [ ] Lista kluczowych decyzji i uzasadnień

---

## Część B: Wykonanie Walidacji (Walidator)

### Krok B1: Przegląd konceptualny

> ✍️ **[DO UZUPEŁNIENIA]** Opisać szczegółowy zakres przeglądu konceptualnego.

**Elementy przeglądu:**
- [ ] Adekwatność metodologii do problemu
- [ ] Jakość danych i procesu data preparation
- [ ] Kompletność i wiarygodność założeń
- [ ] Dokumentacja ograniczeń

### Krok B2: Niezależne testy ilościowe

> ✍️ **[DO UZUPEŁNIENIA]** Opisać minimalne testy per typ modelu zgodnie z STD-003.

### Krok B3: Raportowanie

- [ ] Wypełnij TMPL-003: Raport Walidacji
- [ ] Sklasyfikuj każde finding (krytyczne / poważne / informacyjne)
- [ ] Przygotuj listę rekomendacji
- [ ] Wskaż zdanie na temat gotowości do wdrożenia

---

## Część C: Adresowanie Findings przez DS

### Krok C1: Analiza findings

- [ ] Przejrzyj każde finding z walidatorem
- [ ] Zgódź się lub zakwestionuj klasyfikację (pisemnie)
- [ ] Przygotuj plan adresowania dla findings krytycznych i poważnych

### Krok C2: Zamknięcie findings

- [ ] Zaimplementuj poprawki (jeśli wymagane)
- [ ] Udokumentuj zamknięcie każdego finding
- [ ] Uzyskaj potwierdzenie zamknięcia od Walidatora

---

## Bramka BG-06

> ✅ **Warunki zaliczenia bramki BG-06:**
> - [ ] Brak otwartych krytycznych findings
> - [ ] Plan adresowania poważnych findings zatwierdzony
> - [ ] Raport walidacji finalizowany przez walidatora

---

## Powiązania

- [STD-003: Standard Walidacji](../01_supporting_standards/STD-003_walidacja.md)
- [TMPL-003: Raport Walidacji](../03_templates/TMPL-003_raport_walidacji.md)
