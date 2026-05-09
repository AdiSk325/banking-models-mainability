# Rozdział 2: Zasady Nadrzędne

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## Wprowadzenie

Zasady nadrzędne stanowią rdzeń tego przewodnika. Wszystkie wymagania szczegółowe opisane w kolejnych rozdziałach wywodzą się z jednej lub kilku z poniższych zasad. W przypadku wątpliwości interpretacyjnych, rozstrzygnięcie powinno być zgodne z duchem tych zasad.

Zasady są spójne z wymaganiami SR 11-7 (Federal Reserve), EBA Guidelines on Model Risk Management (2023) oraz SS1/23 (PRA).

---

## 2.1 Podejście Oparte na Ryzyku (Risk-Based Approach)

<!-- PROMPT DLA AUTORA:
Opisz jak zasada risk-based approach przekłada się na praktykę.
Wymień wymiary, wg których oceniamy ryzyko modelu.
Podaj przykłady co oznacza "więcej rygoryzmu" dla modeli wysokiego ryzyka.
Powiąż z rozdziałem 3 (klasyfikacja modeli).
-->

**Zasada:** Poziom rygoryzmu, zakres dokumentacji, częstotliwość walidacji i monitoringu powinny być proporcjonalne do ryzyka, jakie dany model wnosi do organizacji.

**W praktyce oznacza to:**
- Modele Tier 1 (regulacyjne, krytyczne) podlegają pełnemu zakresowi wymagań
- Modele Tier 3 (analityczne, pomocnicze) mogą korzystać z uproszczonej ścieżki
- Zmiana klasyfikacji modelu powinna uruchamiać przegląd obowiązujących wymagań

**Wymiary oceny ryzyka modelu:**

| Wymiar | Pytanie | Implikacje dla ryzyka |
|--------|---------|----------------------|
| Wpływ regulacyjny | Czy wyniki zasilają sprawozdawczość regulacyjną? | Wysoki |
| Wpływ finansowy | Jaki jest potencjalny wpływ błędu na wyniki finansowe? | Proporcjonalny |
| Automatyzacja decyzji | Czy model podejmuje decyzje bez interwencji ludzkiej? | Wysoki |
| Złożoność metodologiczna | Jak trudne jest zrozumienie i wytłumaczenie modelu? | Średni-wysoki |
| Explainability | Czy decyzja modelu może być wyjaśniona klientowi? | Prawny |
| Wrażliwość danych | Czy model przetwarza dane osobowe / wrażliwe? | Prawny / RODO |
| Pokrycie portfela | Jaki % portfela/klientów jest objęty modelem? | Materialnościowy |

---

## 2.2 Proporcjonalność (Proportionality)

<!-- PROMPT DLA AUTORA:
Wyjaśnij jak stosować proporcjonalność w codziennej pracy Data Scientist.
Podaj przykłady: kiedy można stosować skróconą ścieżkę?
Wskaż związek z klasyfikacją Tier.
-->

**Zasada:** Wymagania formalne są adekwatne do klasy i zastosowania modelu. Nie wszystkie modele wymagają takiego samego zakresu dokumentacji, walidacji i kontroli.

**Praktyczna zasada proporcjonalności:**

```
Tier 1 (regulacyjne/krytyczne): PEŁNY zakres wymagań
Tier 2 (istotne): STANDARDOWY zakres wymagań  
Tier 3 (niski wpływ): UPROSZCZONY zakres wymagań
```

> ⚠️ **Ważne dla Data Scientist:** Proporcjonalność nie oznacza pominięcia kluczowych kontroli — każdy model, niezależnie od Tiera, wymaga rejestracji w Model Inventory i przypisania Ownera.

---

## 2.3 Odtwarzalność (Reproducibility)

<!-- PROMPT DLA AUTORA:
Opisz minimalne wymagania techniczne dla zapewnienia odtwarzalności.
Wymień: wersjonowanie kodu, seed losowości, rejestr zależności, archiwalność danych.
Powiąż z MLOps Standard i wymaganiami wdrożeniowymi.
-->

**Zasada:** Każdy model musi być możliwy do odtworzenia — możliwe powinno być ponowne wygenerowanie wyników i zreplikowanie procesu budowy modelu na podstawie zachowanych artefaktów.

**Minimalne wymagania odtwarzalności:**
- Kod modelu pod kontrolą wersji (Git lub równoważny system)
- Zarejestrowane i zamrożone wersje bibliotek i zależności
- Dostęp do danych treningowych (lub ich szczegółowej dokumentacji jeśli archiwizacja niemożliwa)
- Udokumentowane parametry modelu i procedura treningu
- Ustalony seed losowości dla procedur stochastycznych
- Środowisko wykonawcze udokumentowane (kontener, obraz Docker lub specyfikacja równoważna)

---

## 2.4 Identyfikowalność (Traceability)

<!-- PROMPT DLA AUTORA:
Opisz co rozumiemy przez pełny ślad audytowy modelu.
Wymień co musi być możliwe do prześledzenia: decyzje, zmiany, wyniki, użycia.
Wskaż jak to jest weryfikowane podczas audytu lub walidacji.
-->

**Zasada:** Pełny ślad decyzji, zmian i zastosowania modelu powinien być dostępny i możliwy do odtworzenia. Audytor lub walidator powinien być w stanie prześledzić historię modelu od inicjacji do chwili obecnej.

**Co musi być identyfikowalne:**

| Element | Wymaganie |
|---------|-----------|
| Historia zmian | Każda zmiana modelu zarejestrowana w Change Log |
| Decyzje akceptacyjne | Approval Records z datą, osobą, uzasadnieniem |
| Wyniki walidacji | Validation Report z każdej walidacji |
| Wyniki monitoringu | Raporty monitoringowe archiwizowane |
| Dane treningowe | Data snapshot lub szczegółowa dokumentacja |
| Wdrożenia i wersje | Rejestr wersji produkcyjnych |

---

## 2.5 Niezależne Weryfikowanie (Independent Challenge)

<!-- PROMPT DLA AUTORA:
Wyjaśnij co oznacza "niezależność" w kontekście walidacji modeli.
Opisz kiedy walidacja jest uznawana za wystarczająco niezależną.
Wskaż wyjątki i sytuacje kiedy niezależność jest trudna do osiągnięcia (małe organizacje).
-->

**Zasada:** Walidacja modelu musi być przeprowadzona przez podmiot niezależny od zespołu deweloperskiego. Niezależność jest warunkiem koniecznym wiarygodności oceny.

**Wymogi niezależności:**
- Walidator nie może być autorem modelu ani jego bezpośrednim przełożonym
- Walidator powinien raportować do linii niezależnej od MRM pierwszej linii
- W małych organizacjach: walidacja przez inną osobę / zewnętrznego eksperta jest akceptowalna pod warunkiem udokumentowania niezależności

**Kiedy wymagana jest re-walidacja:**
- Przy każdej materialnej zmianie modelu (definicja materialności → patrz Standard Change Management)
- Przy istotnej zmianie populacji docelowej lub zakresu zastosowania
- Po wykryciu materialnej degradacji w monitoringu
- Przy przeglądzie okresowym (frequency zależna od Tiera)

---

## 2.6 Dokumentacja jako Obowiązek (Documentation by Design)

<!-- PROMPT DLA AUTORA:
Opisz filozofię dokumentacji "by design" vs. dokumentacji "po fakcie".
Podaj praktyczne wskazówki dla Data Scientist jak integrować dokumentację z procesem pracy.
Odwołaj się do wymagań minimalnych z rozdziału 7.
-->

**Zasada:** Dokumentacja jest integralną częścią procesu budowy i utrzymania modelu — nie jest czynnością dodatkową wykonywaną po zakończeniu pracy.

**W praktyce oznacza to:**
- Model Development Document (MDD) jest tworzony równolegle z rozwojem modelu, nie po jego zakończeniu
- Każde istotne założenie i decyzja metodologiczna są dokumentowane na bieżąco
- Brak dokumentacji jest blokadą do przejścia przez stage gate

> 💡 **Wskazówka dla Data Scientist:** Traktuj dokumentację jak testy jednostkowe w inżynierii oprogramowania — piszesz je w trakcie, a nie na końcu. Dobra dokumentacja to też zabezpieczenie Twojej pracy przy późniejszej walidacji lub onboardingu nowej osoby.

---

## 2.7 Segregacja Obowiązków (Segregation of Duties)

<!-- PROMPT DLA AUTORA:
Opisz wymagania segregacji dla różnych etapów lifecycle.
Wskaż konflikty interesów, których należy unikać.
Uzupełnij o specyfikę organizacji (jak wygląda podział ról).
-->

**Zasada:** Budowa, walidacja i akceptacja modelu muszą być wykonywane przez różne osoby lub zespoły, aby zapobiec konfliktowi interesów.

**Minimalne wymagania segregacji:**

| Aktywność | Kto wykonuje | Kto nie może wykonywać |
|-----------|-------------|----------------------|
| Budowa modelu | Data Scientist / DS Team | Walidator, Audytor |
| Niezależna walidacja | Validator (niezależny) | Autor modelu, bezpośredni przełożony |
| Akceptacja formalna | Model Owner + Komitet | Autor modelu |
| Monitoring produkcyjny | Model Owner / Ops | Audytor wewnętrzny |
| Audit modelu | Internal Audit | Wszyscy powyżej |

---

## 2.8 Kontrolowane Zmiany (Controlled Change)

<!-- PROMPT DLA AUTORA:
Opisz co oznacza "kontrolowana zmiana" w kontekście modeli.
Zdefiniuj rodzaje zmian i wymagany poziom kontroli.
Powiąż z rozdziałem 5.9 (Zarządzanie Zmianą).
-->

**Zasada:** Każda materialna zmiana modelu wymaga przejścia przez formalny proces zarządzania zmianą. Nie jest dopuszczalne modyfikowanie modelu produkcyjnego bez właściwej autoryzacji.

**Klasyfikacja zmian:**

| Klasa | Opis | Wymagana ścieżka |
|-------|------|-----------------|
| **Zmiana materialna** | Metodologia, zakres, zmienne kluczowe | Pełna re-walidacja + akceptacja komitetu |
| **Zmiana niematerialna** | Rekalibracja, drobne korekty danych | Walidacja ograniczona + akceptacja MRM |
| **Zmiana techniczna** | Migracja infrastruktury, bez wpływu na wyniki | Testy techniczne + IT sign-off |
| **Zmiana awaryjna** | Krytyczny błąd w modelu produkcyjnym | Procedura awaryjna + dokumentacja post-factum |

---

## 2.9 Ciągły Monitoring (Monitoring Throughout Lifecycle)

<!-- PROMPT DLA AUTORA:
Opisz filozofię "monitoring by design" — monitoring powinien być planowany przy budowie, nie dodany po wdrożeniu.
Wymień minimalne elementy Monitoring Plan wymaganego przed wdrożeniem.
Powiąż z rozdziałem 5.8 (Monitoring i Przegląd Okresowy).
-->

**Zasada:** Monitoring modelu jest obowiązkiem przez cały czas życia modelu w produkcji. Obowiązek monitoringu jest planowany jako część procesu budowy modelu, a nie dopiero po wdrożeniu.

**Minimalne elementy planu monitoringu (wymagane przed wdrożeniem):**
- Zdefiniowane metryki performance (np. AUC, Gini, accuracy)
- Zdefiniowane metryki stabilności (PSI, CSI)
- Thresholdy alarmowe i eskalacyjne
- Częstotliwość raportowania
- Odpowiedzialny za monitoring (Model Owner)
- Trigger events uruchamiające review lub re-walidację

---

## 2.10 Ludzka Odpowiedzialność (Human Accountability)

<!-- PROMPT DLA AUTORA:
Opisz wymaganie przypisania ludzkiej odpowiedzialności za każdy model.
Wskaż co dzieje się gdy Owner zmienia rolę lub odchodzi z organizacji.
Powiąż z Model Inventory i rozdziałem 6 (Role).
-->

**Zasada:** Każdy model w produkcji musi mieć zidentyfikowanego, imiennie wskazanego Model Ownera odpowiedzialnego za jego działanie i zgodność z wymaganiami.

**Wymagania:**
- Każdy model w rejestrze (Model Inventory) musi mieć przypisanego Model Ownera
- Model Owner ponosi odpowiedzialność za monitoring, dokumentację aktualności i eskalację problemów
- Zmiana Ownera wymaga formalnego procesu przekazania odpowiedzialności (handover)
- Modele bez przypisanego Ownera nie mogą pozostawać w produkcji

---

## 2.11 Zgodność z Regulacjami (Regulatory Compliance)

<!-- PROMPT DLA AUTORA:
Wymień kluczowe regulacje i wytyczne obowiązujące w organizacji.
Wskaż jak wymagania z tych dokumentów są uwzględnione w tym przewodniku.
Dodaj odniesienia do lokalnych wymagań KNF.
-->

**Zasada:** Wszystkie modele i procesy związane z ich lifecycle muszą być zgodne z obowiązującymi regulacjami, wytycznymi nadzorczymi i politykami wewnętrznymi.

**Kluczowe dokumenty regulacyjne:**

| Dokument | Organizacja | Dotyczy |
|----------|-------------|---------|
| SR 11-7 Guidance on Model Risk Management | US Federal Reserve (2011) | Framework MRM — globalny standard branżowy |
| OCC Bulletin 2011-12 | OCC (2011) | Model risk management |
| EBA Guidelines on Model Risk Management | EBA (2023) | Europejskie banki — obowiązujące |
| ECB Guide to Internal Models (TRIM) | ECB (2018) | Modele IRB, IRRBB, CCR |
| SS1/23 Model Risk Management | PRA/BoE (2023) | Banki brytyjskie — dobra praktyka |
| Rekomendacje KNF | KNF | Wymagania polskiego nadzorcy |
| CRR/CRD IV/V | EU | Wymogi kapitałowe — modele IRB |
| IFRS 9 | IASB | Modele ECL |
| RODO/GDPR | EU | Dane osobowe w modelach |

> 📚 **Pełna bibliografia:** [../references/README.md](../references/README.md)

---

## Podsumowanie: Zasady a Etapy Lifecycle

<!-- PROMPT DLA AUTORA:
Uzupełnij tabelę powiązań zasad z etapami lifecycle.
Cel: pokazać Data Scientist, która zasada jest najbardziej istotna na danym etapie.
-->

| Zasada | Inicjacja | Budowa | Walidacja | Wdrożenie | Monitoring | Zmiana |
|--------|-----------|--------|-----------|-----------|------------|--------|
| Risk-Based | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Proporcjonalność | ✅ | | ✅ | | ✅ | ✅ |
| Odtwarzalność | | ✅✅ | ✅ | ✅ | | ✅ |
| Identyfikowalność | | ✅ | ✅ | ✅ | ✅ | ✅✅ |
| Niezależność | | | ✅✅ | | ✅ | ✅✅ |
| Dokumentacja | ✅ | ✅✅ | ✅ | ✅ | ✅ | ✅ |
| Segregacja | | ✅ | ✅✅ | ✅ | | ✅ |
| Kont. Zmiany | | | | | | ✅✅ |
| Monitoring | | ✅ | | ✅ | ✅✅ | ✅ |
| Odpowiedzialność | ✅✅ | | | ✅ | ✅✅ | ✅ |
| Zgodność | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

*✅✅ = kluczowa zasada dla tego etapu*

---

*Następny rozdział: [03_klasyfikacja_modeli.md — Klasyfikacja i Tiering Modeli](./03_klasyfikacja_modeli.md)*
