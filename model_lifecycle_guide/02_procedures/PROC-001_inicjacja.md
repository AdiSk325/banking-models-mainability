# PROC-001: Procedura Inicjacji Modelu

> **Typ dokumentu:** Procedura (Poziom 3)  
> **Status:** 🔄 Szkielet — wymaga uzupełnienia kroków operacyjnych  
> **Powiązany etap:** Etapy 1–2 cyklu życia

---

## Cel procedury

Opisuje krok po kroku działania wymagane do formalnego zainicjowania nowego projektu modelarskiego, rejestracji modelu i uzyskania zatwierdzenia do rozpoczęcia developmentu.

---

## Krok 1: Identyfikacja i uzasadnienie potrzeby biznesowej

**Odpowiedzialny:** Data Scientist + Model Owner (wnioskujący)

**Działania:**
- [ ] Zdefiniuj problem decyzyjny lub regulacyjny, który model ma rozwiązać
- [ ] Uzasadnij dlaczego model jest potrzebny (vs. alternatywy bez modelu)
- [ ] Zidentyfikuj potencjalnych odbiorców (Model Users)
- [ ] Przeprowadź wstępną ocenę dostępności danych
- [ ] Zaproponuj wstępną klasyfikację tieru
- [ ] Wypełnij **TMPL-001: Dokument Koncepcji Modelu**

**Wyjście:** Wypełniony TMPL-001

---

## Krok 2: Zatwierdzenie Business Case przez Model Owner

**Odpowiedzialny:** Model Owner

**Działania:**
- [ ] Przejrzyj i zatwierdź uzasadnienie biznesowe
- [ ] Potwierdź sponsorowanie projektu i alokację zasobów
- [ ] Zidentyfikuj inne zainteresowane strony (Compliance, IT)

**Wyjście:** Podpisany TMPL-001 przez Model Owner

---

## Krok 3: Konsultacja z MRM i zatwierdzenie tieru

**Odpowiedzialny:** MRM

**Działania:**
- [ ] Dokonaj przeglądu Business Case
- [ ] Potwierdź lub skoryguj klasyfikację tieru
- [ ] Wskaż wymagania specyficzne per tier

> ⚠️ **[REGULACYJNE]** Na tym etapie MRM identyfikuje potencjalne wymogi nadzorcze i czy model może wymagać notyfikacji KNF/ECB. Data Scientist powinien być o tym poinformowany na starcie.

**Wyjście:** Zatwierdzony tier przez MRM

---

## Krok 4: Rejestracja w inwentarzu modeli

**Odpowiedzialny:** MRM (z pomocą DS)

**Działania:**
- [ ] Utwórz wpis w inwentarzu modeli (zgodnie z STD-005)
- [ ] Przypisz unikalny ID modelu
- [ ] Ustaw status: "In Development"
- [ ] Uzupełnij minimalne pola inwentarza

**Wyjście:** Wpis w inwentarzu z ID modelu

---

## Krok 5: Przygotowanie planu developmentu

**Odpowiedzialny:** Data Scientist

**Działania:**
- [ ] Przygotuj plan developmentu z kluczowymi milestones
- [ ] Zidentyfikuj zasoby danych i dostępy wymagane
- [ ] Zaplanuj zaangażowanie walidatora (dla Tier 1/2)
- [ ] Określ wstępny harmonogram

**Wyjście:** Plan developmentu zatwierdzony przez Model Owner

---

## Bramka BG-01

> ✅ **Warunki zaliczenia bramki BG-01:**
> - [ ] Business Case zatwierdzony przez Model Owner
> - [ ] Tier potwierdzony przez MRM
> - [ ] Model zarejestrowany w inwentarzu z ID
> - [ ] Plan developmentu gotowy

---

## Powiązania

- [TMPL-001: Dokument Koncepcji](../03_templates/TMPL-001_dokument_koncepcji.md)
- [STD-005: Inwentarz Modeli](../01_supporting_standards/STD-005_inwentarz.md)
- [Rozdział 5: Etap 1–2](../00_guide/05_etapy_cyklu_zycia.md)
