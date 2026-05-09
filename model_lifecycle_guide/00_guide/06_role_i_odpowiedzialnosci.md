# Rozdział 6: Role i Odpowiedzialności

> **Status:** 🔄 Szkielet — wymaga uzupełnienia macierzy RACI  
> **Priorytet uzupełnienia:** Wysoki

---

## 6.1 Definicje Ról

### Data Scientist / Model Developer
**Główna odpowiedzialność:** Budowa, dokumentacja i wsparcie techniczne modelu.

**Zakres obowiązków:**
- Ocena i przygotowanie danych
- Projektowanie i budowa modelu
- Testowanie (jednostkowe, backtesting)
- Dokumentacja modelarska (MDD, kod)
- Wsparcie podczas walidacji (odpowiedzi na pytania, nie modyfikacja)
- Monitoring techniczny (obliczanie metryk)
- Wsparcie przy zmianach i aktualizacjach

---

### Model Owner
**Główna odpowiedzialność:** Biznesowa odpowiedzialność za model — od inicjacji do wycofania.

**Zakres obowiązków:**
- Uzasadnienie biznesowe i inicjacja
- Zatwierdzenie podejścia i metodologii
- Akceptacja dokumentacji
- Formalne zatwierdzenie wdrożenia
- Odpowiedzialność za monitoring i reagowanie
- Zatwierdzanie zmian i decyzja o wycofaniu
- Raportowanie do governance

---

### Model User
**Główna odpowiedzialność:** Operacyjne użycie modelu zgodnie z jego przeznaczeniem.

**Zakres obowiązków:**
- Użycie modelu zgodnie z zakresem
- Raportowanie anomalii i problemów do Model Ownera
- Przestrzeganie limitów i ograniczeń modelu

---

### Niezależny Walidator
**Główna odpowiedzialność:** Niezależna ocena modelu i jego dokumentacji.

**Zakres obowiązków:**
- Przegląd konceptualny
- Niezależne testy ilościowe
- Ocena dokumentacji i założeń
- Raportowanie findings
- Follow-up na adresowanie findings

**Kluczowy warunek:** Organizacyjna niezależność od zespołu developmentu.

---

### Model Risk Management (MRM)
**Główna odpowiedzialność:** Zarządzanie ryzykiem modelowym na poziomie portfela.

**Zakres obowiązków:**
- Klasyfikacja i tiering modeli
- Utrzymanie inwentarza modeli
- Koordynacja procesu walidacji
- Raportowanie do zarządu/komitetu
- Polityki i standardy
- Relacje z nadzorcą

---

### IT / MLOps / Engineering
**Główna odpowiedzialność:** Techniczne wdrożenie i utrzymanie infrastruktury modelarskiej.

**Zakres obowiązków:**
- Środowisko deweloperskie i produkcyjne
- Pipeline wdrożeniowy
- Code review z perspektywy technicznej
- Kontrola dostępu i bezpieczeństwo
- Backup i disaster recovery
- SLA monitoringu technicznego

---

### Compliance
**Główna odpowiedzialność:** Ocena zgodności z regulacjami zewnętrznymi i wewnętrznymi politykami.

**Zakres obowiązków:**
- Ocena wymogów privacy (RODO)
- Compliance z wymogami anti-discrimination (fair lending)
- Ocena regulacyjna (jeśli model ma implikacje compliance)
- Wsparcie przy interakcjach z nadzorcą

---

### Internal Audit
**Główna odpowiedzialność:** Niezależna ocena systemu kontroli wewnętrznej.

**Zakres obowiązków:**
- Cykliczne audyty procesu model governance
- Ocena skuteczności kontroli
- Raportowanie do zarządu

---

### Model Risk Committee (MRC) / Governance Forum
**Główna odpowiedzialność:** Formalne zatwierdzenie modeli i polityk.

**Zakres obowiązków:**
- Zatwierdzenie modeli Tier 1 i Tier 2 do wdrożenia
- Zatwierdzenie polityk i standardów
- Zatwierdzenie odstępstw (exceptions)
- Nadzór nad portfelem modeli

---

## 6.2 Macierz RACI

> ✍️ **[DO UZUPEŁNIENIA]** Uzupełnić pełną macierz RACI dla wszystkich 13 etapów.  
> Legenda: **R** = Responsible (wykonuje) | **A** = Accountable (zatwierdza) | **C** = Consulted | **I** = Informed

| Etap | DS | Model Owner | Validator | MRM | IT/MLOps | Compliance | MRC |
|---|---|---|---|---|---|---|---|
| 1. Identyfikacja potrzeby | R | A | I | C | I | C | I |
| 2. Inicjacja | R | A | I | A | I | I | I |
| 3. Dane i ocena | R | C | I | C | C | C | I |
| 4. Projektowanie | R | A | C | C | C | I | I |
| 5. Development | R | I | I | I | C | I | I |
| 6. Testy i dokumentacja | R | A | I | C | C | I | I |
| 7. Walidacja niezależna | C | C | R,A | A | I | I | I |
| 8. Zatwierdzenie governance | I | R | C | A | I | C | A |
| 9. Wdrożenie | C | A | I | I | R | I | I |
| 10. Monitoring | R | A | I | I | C | I | I |
| 11. Review i aktualizacja | R | A | C | C | C | I | I |
| 12. Change management | R | A | C | A | C | I | A* |
| 13. Wycofanie | C | A | I | A | R | I | I |

*MRC dla material changes

---

## 6.3 Specyfika Ról per Typ Modelu

> ⚠️ **[REGULACYJNE]** Dla modeli regulacyjnych rola MRM jest wzmocniona — MRM funkcjonuje jako pierwsza linia obrony przed nadzorcą. Relacja z walidatorem jest formalna i udokumentowana.

> 📋 **[SUPERVISED]** Rola DS jest szczególnie ważna w etapie danych — definicja target variable jest decyzją metodyczną o ogromnych konsekwencjach.

> 🔬 **[UNSUPERVISED]** Rola ekspertów domenowych (często Business Owner lub Model Owner) jest kluczowa przy interpretacji segmentów — DS nie może samodzielnie walidować sensu biznesowego klasteryzacji.

---

## 6.4 Powiązane Dokumenty

- [Rozdział 5: Etapy Cyklu Życia](./05_etapy_cyklu_zycia.md) — co robi każda rola na każdym etapie
- [Rozdział 8: Kontrole i Wyjątki](./08_kontrole_wyjatki.md) — eskalacja i exception management

---

*Poprzedni: [05 — Etapy](./05_etapy_cyklu_zycia.md) | Następny: [07 — Wymagane Artefakty](./07_wymagane_artefakty.md)*
