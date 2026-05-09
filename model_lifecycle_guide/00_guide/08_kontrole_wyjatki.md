# Rozdział 8: Kontrole, Wyjątki i Eskalacja

> **Status:** 🔄 Szkielet — wymaga uzupełnienia o specifics governance  
> **Priorytet uzupełnienia:** Średni

---

## 8.1 Governance Forums

> ✍️ **[DO UZUPEŁNIENIA]** Uzupełnić o nazwy i skład konkretnych komitetów w organizacji.

| Forum | Rola | Skład | Częstotliwość |
|---|---|---|---|
| **Model Risk Committee (MRC)** | Zatwierdzenie modeli Tier 1/2, polityk i wyjątków | [do uzupełnienia] | [do uzupełnienia] |
| **[Komitet Tier 3]** | Zatwierdzenie modeli Tier 3 | [do uzupełnienia] | [do uzupełnienia] |
| **Zarząd / Komitet Ryzyka** | Nadzór nad portfelem ryzyka modelowego | [do uzupełnienia] | Kwartalnie |

---

## 8.2 Approval Gates — Przegląd

Każda bramka decyzyjna (BG) ma zdefiniowane:
- Co musi być gotowe (kryteria wejścia)
- Kto zatwierdza
- Jakie dokumenty są wymagane
- Co się dzieje gdy bramka nie jest spełniona

| Bramka | Kryteria | Zatwierdzający | Konsekwencja niespełnienia |
|---|---|---|---|
| BG-01 | Business Case zatwierdzony, tier potwierdzony | Model Owner + MRM | Zatrzymanie projektu |
| BG-02 | Dane ocenione jako adekwatne | Data Owner + MRM | Poszukiwanie alternatywnych źródeł / zatrzymanie |
| BG-03 | Metodologia zatwierdzona | Model Owner + MRM | Redesign |
| BG-05 | Dokumentacja kompletna | Model Owner | Uzupełnienie dokumentacji |
| BG-06 | Brak krytycznych findings walidacyjnych | Validator | Adresowanie findings lub warunkowe wdrożenie |
| BG-07 | Governance approval | MRC | Model nie przechodzi do wdrożenia |
| BG-08 | UAT pass, production readiness | IT + Model Owner | Wstrzymanie go-live |

---

## 8.3 Exception Management (Zarządzanie Wyjątkami)

### Kiedy wyjątek jest potrzebny?
Wyjątek jest wymagany gdy model nie spełnia standardowych wymagań przewodnika, ale musi być stosowany z uzasadnionych powodów (np. wymóg regulacyjny wymuszający użycie modelu mimo ograniczeń, nagłe potrzeby biznesowe).

### Typy wyjątków

| Typ | Przykład | Ścieżka zatwierdzenia |
|---|---|---|
| **Walidacja częściowa** | Wdrożenie z otwartymi findings niskiej istotności | MRM + MRC |
| **Dokumentacja niepełna** | Wdrożenie z planem uzupełnienia dokumentacji | Model Owner + MRM |
| **Monitoring uproszczony** | Zmniejszona częstotliwość monitoringu | MRM |
| **Fast-track approval** | Pilne wdrożenie z ograniczonym review | MRC (quorum) |

### Wymagania dla wyjątku
> 🔴 **OBOWIĄZKOWE** dla każdego wyjątku:
1. Uzasadnienie w formie pisemnej
2. Opis ryzyk wynikających z wyjątku
3. Plan mitigacji lub plan zamknięcia odstępstwa
4. Określony czas obowiązywania wyjątku
5. Formalne zatwierdzenie przez MRC lub MRM (zależnie od tieru)
6. Rejestracja w inwentarzu wyjątków

### Monitoring wyjątków
- MRM raportuje otwarte wyjątki do MRC kwartalnie
- Każdy wyjątek ma właściciela i termin zamknięcia
- Wyjątki niespełnione w terminie eskalują do zarządu

---

## 8.4 Eskalacja

### Ścieżka eskalacji technicznej
```
DS → Team Lead DS → Model Owner → MRM → MRC → Zarząd
```

### Ścieżka eskalacji regulacyjnej
```
MRM → Compliance → Zarząd → (KNF/ECB jeśli dotyczy)
```

### Trigger events dla eskalacji

| Zdarzenie | Eskalacja do | Czas reakcji |
|---|---|---|
| Krytyczne finding walidacyjne | MRM + Model Owner | Niezwłocznie |
| Naruszenie progu monitoringowego (PSI > threshold) | Model Owner | 5 dni roboczych |
| Błąd produkcyjny modelu | IT + Model Owner + MRM | Niezwłocznie |
| Podejrzenie naruszenia regulacyjnego | Compliance + MRM | Niezwłocznie |
| Otwarte wyjątki przeterminowane | MRC | Najbliższe posiedzenie |

---

## 8.5 Model Incident Management

> ✍️ **[DO UZUPEŁNIENIA]** Opisać procedurę obsługi incydentów modelarskich (np. błąd scoring, awaria modelu, odkrycie data leakage po wdrożeniu).

Kluczowe elementy do opisania:
- Definicja incydentu modelarskiego
- Klasyfikacja incydentów (P1/P2/P3)
- Procedura zgłaszania i pierwszej oceny
- Rollback procedure
- Root cause analysis
- Raportowanie do MRC i nadzorcy (jeśli dotyczy)

---

## 8.6 Powiązane Dokumenty

- [Rozdział 6: Role i Odpowiedzialności](./06_role_i_odpowiedzialnosci.md)
- [STD-006: Zarządzanie Zmianą](../01_supporting_standards/STD-006_zarzadzanie_zmiana.md)
- [PROC-005: Monitoring](../02_procedures/PROC-005_monitoring.md)

---

*Poprzedni: [07 — Artefakty](./07_wymagane_artefakty.md) | Następny: [09 — Powiązane Dokumenty](./09_powiazane_dokumenty.md)*
