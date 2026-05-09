# Etap 5.5: Niezależna Walidacja

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Testowanie](./04_testowanie_dokumentacja.md) | [Następny: Akceptacja →](./06_akceptacja_governance.md)

---

## Cel Etapu

Niezależna, obiektywna ocena jakości, metodologii, dokumentacji i wyników modelu przez podmiot niezależny od zespołu deweloperskiego. Walidacja jest kluczową kontrolą jakości przed wdrożeniem modelu.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Niezależny Walidator** | Przeprowadza walidację, wystawia Validation Report |
| **Data Scientist (pasywny)** | Odpowiada na pytania, dostarcza wyjaśnień, nie modyfikuje modelu |
| **Model Owner** | Koordynuje dostęp, śledzi postęp |
| **MRM** | Nadzór nad procesem walidacji, tracking findings |

---

## Wymagania Niezależności

<!-- PROMPT DLA AUTORA:
Opisz wymagania niezależności walidatora w organizacji.
Jak jest zorganizowany zespół walidacji?
W jakich przypadkach dopuszczalna jest zewnętrzna walidacja?
-->

- Walidator nie może być autorem modelu ani jego bezpośrednim przełożonym
- Walidator powinien raportować do linii niezależnej od MRM pierwszej linii
- W przypadku braku wystarczających zasobów wewnętrznych: walidacja zewnętrzna akceptowalna z udokumentowaniem niezależności
- Konflikty interesów muszą być ujawniane i zarządzane

---

## Zakres Walidacji

### Obligatoryjne elementy walidacji

<!-- PROMPT DLA AUTORA:
Uzupełnij o zakres walidacji przyjęty w organizacji.
Który element jest priorytetem dla każdej kategorii modelu?
Jakie są akceptowalne wyłączenia ze scope walidacji?
-->

| Element | Opis | Wymagany dla |
|---------|------|--------------|
| **Conceptual Soundness** | Ocena zasadności metodologicznej — czy podejście jest właściwe? | Wszystkie |
| **Data Quality Review** | Niezależna ocena jakości i adekwatności danych | Wszystkie |
| **Outcomes Analysis / Backtesting** | Ocena performance na danych historycznych | Kat. A, B, C |
| **Benchmarking** | Porównanie z modelem alternatywnym lub regułą prostą | Kat. A, B, C |
| **Sensitivity Analysis** | Wrażliwość wyników na zmianę założeń / parametrów | Kat. A, B, C |
| **Stress Testing** | Zachowanie modelu w scenariuszach stresowych | Kat. A |
| **Documentation Review** | Ocena kompletności i jakości dokumentacji | Wszystkie |
| **Explainability Assessment** | Ocena wyjaśnialności wyników | Kat. C, D |
| **Bias & Fairness Review** | Weryfikacja testów dyskryminacji | Kat. B, C |
| **Regulatory Compliance** | Ocena zgodności z wymaganiami regulacyjnymi | Kat. A |
| **Business Use Alignment** | Czy model jest właściwy do deklarowanego zastosowania? | Wszystkie |

---

## Wyniki Walidacji i Klasyfikacja Findings

<!-- PROMPT DLA AUTORA:
Opisz klasyfikację findings stosowaną w organizacji.
Jak przebiega zamknięcie findingów?
W jakich przypadkach model może być wdrożony warunkowo?
-->

### Klasyfikacja findings

| Klasa | Opis | Skutek |
|-------|------|--------|
| **Critical** | Błąd metodologiczny lub fałszywa dokumentacja — model nie może być wdrożony | Blokuje wdrożenie |
| **High** | Istotna słabość metodologiczna lub dokumentacyjna | Wymaga remediation przed wdrożeniem |
| **Medium** | Ograniczenie lub rekomendacja poprawy | Plan remediation w wyznaczonym terminie |
| **Low / Informational** | Sugestia poprawy bez istotnego wpływu | Opcjonalna poprawa |

### Warunkowe wdrożenie (Provisional Deployment)

<!-- PROMPT DLA AUTORA:
Opisz politykę warunkowego wdrożenia (provisional deployment) w organizacji.
Kiedy jest dopuszczalne? Jakie są warunki i terminy?
-->

Model może być wdrożony warunkowo jeśli:
- Brak findings klasy Critical
- Findings klasy High mają udokumentowany plan remediation z terminem
- Model Owner i MRM akceptują warunki wdrożenia
- Maksymalny czas na remediation: [PLACEHOLDER: np. 3/6 miesięcy] od wdrożenia

---

## Wymagane Artefakty Walidacji

| Artefakt | Opis | Wystawia |
|----------|------|---------|
| **Validation Report** | Pełny raport z wynikami walidacji | Walidator |
| **Findings Register** | Lista findings z klasą, opisem, rekomendacją | Walidator |
| **Remediation Plan** | Plan działań dla findings H/M (jeśli dotyczy) | DS / Model Owner |
| **Validation Sign-off** | Formalne potwierdzenie zakończenia walidacji | Walidator |
| **Approval Record (Gate 5)** | Walidator sign-off (z ewentualnymi warunkami) | Walidator |

---

## Kryteria Wyjścia — Stage Gate 5

- [ ] Validation Report ukończony
- [ ] Brak findings klasy Critical
- [ ] Plan remediation dla findings H/M zaakceptowany
- [ ] Walidator sign-off udzielony (bezwarunkowy lub warunkowy)

---

## Specyfika według Kategorii Modelu

### Kategoria A — Regulacyjny

- Ocena zgodności z EBA GL / ECB TRIM / KNF jako obowiązkowe kryterium
- Ocena czy Margin of Conservatism jest właściwy (jeśli dotyczy)
- Stress testing w scenariuszach regulacyjnych
- Backtesting z wymaganymi okienkami historii

### Kategoria B — Scorecard

- Niezależna weryfikacja WoE/IV i procesu binningu
- Backtesting na OOT sample (co najmniej [PLACEHOLDER: N] miesięcy)
- Test Gini/AUC, KS, PSI
- Weryfikacja kalibracji

### Kategoria C — Supervised ML

- Niezależna ocena wyjaśnialności (SHAP/LIME) — czy wyniki są interpretowalnie poprawne?
- Niezależna weryfikacja bias assessment
- Ocena feature importance — czy zmienne mają sens biznesowy?
- Benchmarking vs. prostszy model (scorecard lub reguła prosta)

### Kategoria D — Unsupervised

- Ocena zasadności metodologicznej (conceptual soundness) — najważniejszy element
- Niezależna ocena sensowności biznesowej wyników
- Weryfikacja stabilności metodologią niezależną
- Ocena planu monitoringu

---

## Kiedy Wymagana Re-walidacja

| Trigger | Wymagana akcja |
|---------|----------------|
| Materialna zmiana modelu | Re-walidacja obowiązkowa |
| Zmiana zakresu stosowania | Ocena potrzeby re-walidacji przez MRM |
| Materialna degradacja w monitoringu | Re-walidacja zalecana |
| Periodyczny przegląd (Tier 1: rok, Tier 2: 2 lata) | Re-walidacja lub Ongoing Monitoring Review |
| Zmiana regulacji dotycząca modelu | Ocena wpływu + ewentualna re-walidacja |

---

*Szablony: [Validation Report Template](../../templates/), [Findings Register Template](../../templates/)*
