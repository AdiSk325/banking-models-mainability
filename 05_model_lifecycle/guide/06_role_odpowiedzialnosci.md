# Rozdział 6: Role i Odpowiedzialności

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## Wprowadzenie

Ten rozdział definiuje role zaangażowane w cykl życia modeli oraz ich obowiązki. Jasne przypisanie odpowiedzialności jest fundamentem skutecznego zarządzania ryzykiem modelowym.

---

## 6.1 Definicje Ról

### Data Scientist / Model Developer

<!-- PROMPT DLA AUTORA:
Opisz szczegółowe obowiązki Data Scientist w organizacji.
Czym różni się DS Senior od DS Junior pod kątem uprawnień?
Jak wygląda podział na różne specjalizacje (ML, statystyka, regulatory)?
-->

**Odpowiedzialność za:**
- Budowę modelu zgodnie ze standardami deweloperskimi
- Dokumentację metodologii, założeń i ograniczeń (MDD)
- Przeprowadzenie wewnętrznych testów jakości
- Wsparcie procesu walidacji (dostęp do danych i wyjaśnień)
- Implementację remediation findings z walidacji

**Uprawnienia:**
- Dostęp do środowisk DEV i TEST
- Brak dostępu do bezpośredniej modyfikacji modelu produkcyjnego

**Raportuje do:** Lead Data Scientist / Head of Modelling

---

### Model Owner

<!-- PROMPT DLA AUTORA:
Opisz szczegółowe obowiązki Model Ownera.
Jaka jest różnica między Model Ownerem a Business Ownerem?
Co się dzieje gdy Model Owner zmienia rolę?
-->

**Odpowiedzialność za:**
- Uzasadnienie biznesowe modelu i inicjacja potrzeby modelowej
- Całościowy nadzór nad lifecycle modelu
- Akceptacja wyników testów i zgłoszenie do walidacji
- Monitoring modelu produkcyjnego (oversight)
- Eskalacja problemów z modelem
- Inicjacja zmiany lub wycofania modelu
- Zachowanie aktualności dokumentacji

**Uprawnienia:**
- Akceptacja Gate 4 (po testowaniu)
- Uczestnictwo w Komitecie Akceptacji Modeli
- Inicjacja Change Request

**Raportuje do:** Business Owner / CRO

---

### Model User

<!-- PROMPT DLA AUTORA:
Opisz rolę Model Usera — osoby / systemu korzystającego z wyników modelu.
Jakie są obowiązki wobec governance?
-->

**Odpowiedzialność za:**
- Stosowanie modelu zgodnie z jego udokumentowanym zastosowaniem
- Zgłaszanie nieoczekiwanego zachowania modelu
- Dokumentowanie decyzji opartych na modelu (override, uzasadnienie)

---

### Niezależny Walidator

<!-- PROMPT DLA AUTORA:
Opisz wymagania kwalifikacyjne dla walidatora.
Jak zorganizowany jest zespół walidacji?
Jakie są wymogi niezależności?
-->

**Odpowiedzialność za:**
- Niezależną ocenę modelu zgodnie z zakresem walidacji
- Wystawienie Validation Report z wynikami i findings
- Ocenę zgodności z wymogami regulacyjnymi (Kat. A)
- Śledzenie i weryfikację zamknięcia findings

**Wymogi:**
- Niezależność od zespołu deweloperskiego
- Kwalifikacje metodologiczne odpowiednie do oceny danego modelu
- Brak konfliktu interesów

---

### Model Risk Management (MRM)

<!-- PROMPT DLA AUTORA:
Opisz rolę MRM w organizacji — czy jest to Druga Linia Obrony?
Jakie są uprawnienia MRM?
-->

**Odpowiedzialność za:**
- Utrzymanie frameworku zarządzania ryzykiem modelowym
- Model Inventory — zarządzanie rejestrem modeli
- Klasyfikacja modeli (Tier, Kategoria)
- Nadzór nad procesem walidacji
- Tracking findings i remediation
- Raportowanie do komitetu i zarządu
- Aktualizacja polityk i standardów

**Linia obrony:** Druga Linia Obrony (2LoD)

---

### Business Owner / Sponsor

**Odpowiedzialność za:**
- Inicjacja potrzeby modelowej
- Zapewnienie zasobów i priorytetu dla projektu modelowego
- Uczestnictwo w Komitecie Akceptacji Modeli

---

### Data Owner / Data Steward

**Odpowiedzialność za:**
- Formalne potwierdzenie dostępności i jakości danych
- Weryfikacja zgodności z polityką danych i RODO
- Data lineage i dokumentacja źródeł danych

---

### IT / MLOps / Engineering

**Odpowiedzialność za:**
- Infrastruktura wdrożeniowa i środowiska
- Implementacja techniczna modeli w produkcji
- Code standards i pipeline CI/CD
- Monitoring infrastruktury technicznej
- Zarządzanie model registry

---

### Compliance

**Odpowiedzialność za:**
- Weryfikacja zgodności z wymogami regulacyjnymi
- Opinion w zakresie nowych przepisów dotyczących modeli
- Wsparcie przy przygotowaniu do inspekcji regulacyjnej

---

### Internal Audit

**Odpowiedzialność za:**
- Niezależna ocena frameworku governance modeli
- Audyt wybranych modeli i procesów
- Opinia o skuteczności kontroli

**Linia obrony:** Trzecia Linia Obrony (3LoD)

---

### Komitet Akceptacji Modeli

<!-- PROMPT DLA AUTORA:
Opisz skład, częstotliwość spotkań i mandat komitetu.
Jakie decyzje komitet jest uprawniony podejmować?
Czy istnieje hierarchia komitetów (np. dla różnych Tierów)?
-->

**Skład:** [PLACEHOLDER — do uzupełnienia przez organizację]  
**Częstotliwość:** [PLACEHOLDER]  
**Mandat:** Formalna akceptacja modeli przed wdrożeniem, zarządzanie materialnymi zmianami, oversight ryzyka modelowego

---

## 6.2 RACI Matrix — Cykl Życia Modelu

<!-- PROMPT DLA AUTORA:
Uzupełnij RACI matrix o brakujące role specyficzne dla organizacji.
R = Responsible (wykonuje), A = Accountable (odpowiada), C = Consulted (konsultowany), I = Informed (informowany)
-->

| Aktywność | DS/Dev | Model Owner | Validator | MRM | IT/MLOps | Compliance | Komitet |
|-----------|--------|-------------|-----------|-----|----------|------------|---------|
| **Inicjacja — Concept Note** | R | A | I | C | I | — | I |
| **Klasyfikacja Tiera** | C | C | — | A/R | — | — | I |
| **Ocena danych** | R | C | — | I | — | C | — |
| **Budowa modelu** | R | I | — | I | C | — | — |
| **Testowanie** | R | A | — | I | — | — | — |
| **Walidacja niezależna** | C | I | R/A | I | — | — | I |
| **Akceptacja** | C | A | C | C | — | C | R |
| **Wdrożenie** | C | I | — | I | R/A | — | — |
| **Monitoring** | C | A/R | — | I | R | — | I |
| **Zmiana — ocena** | R | A | C | R | — | C | I/C |
| **Wycofanie** | C | A | — | R | R | C | I |

---

## 6.3 Three Lines of Defense

```
┌──────────────────────────────────────────────────────────────────┐
│                 THREE LINES OF DEFENSE                           │
│                                                                  │
│  PIERWSZA LINIA (1LoD)                                          │
│  ┌────────────────────────────────────────────────┐             │
│  │ Data Scientists, Model Owners, Model Users,    │             │
│  │ Business Teams, IT/MLOps                       │             │
│  │ → Budują, wdrażają, używają, monitorują modele │             │
│  └────────────────────────────────────────────────┘             │
│                          ↕ challenge                             │
│  DRUGA LINIA (2LoD)                                             │
│  ┌────────────────────────────────────────────────┐             │
│  │ Model Risk Management, Independent Validators, │             │
│  │ Compliance, Risk Functions                     │             │
│  │ → Nadzorują, walidują, zarządzają ryzykiem     │             │
│  └────────────────────────────────────────────────┘             │
│                          ↕ audit                                 │
│  TRZECIA LINIA (3LoD)                                           │
│  ┌────────────────────────────────────────────────┐             │
│  │ Internal Audit                                 │             │
│  │ → Niezależnie audytują framework i procesy     │             │
│  └────────────────────────────────────────────────┘             │
└──────────────────────────────────────────────────────────────────┘
```

---

*Następny rozdział: [07_wymagane_artefakty.md — Wymagane Artefakty](./07_wymagane_artefakty.md)*
