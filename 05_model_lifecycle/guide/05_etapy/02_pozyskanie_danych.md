# Etap 5.2: Pozyskiwanie i Ocena Danych

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Inicjacja](./01_inicjacja.md) | [Następny: Budowa →](./03_projektowanie_rozwoj.md)

---

## Cel Etapu

Identyfikacja, pozyskanie i ocena jakości danych niezbędnych do budowy modelu. Celem jest potwierdzenie, że dane są odpowiedniej jakości, dostępne i odpowiednie do zastosowania modelowego, zanim rozpocznie się właściwa budowa modelu.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Data Scientist** | Eksploracja danych, ocena jakości, EDA |
| **Data Owner / Data Steward** | Formalne potwierdzenie dostępności i jakości |
| **Model Owner** | Weryfikacja adekwatności danych do celu biznesowego |
| **Compliance / Legal** | Weryfikacja dopuszczalności użycia danych (RODO) |

---

## Wejścia (Inputs)

- Model Concept Note (z etapu 5.1)
- Dostęp do potencjalnych źródeł danych
- Wymagania regulacyjne dotyczące danych (jeśli Kategoria A)

---

## Główne Aktywności

<!-- PROMPT DLA AUTORA:
Opisz szczegółowo proces oceny danych w organizacji.
Jakie źródła danych są typowo dostępne?
Jak wygląda proces uzyskania dostępu do danych?
Jakie narzędzia są stosowane do profilowania danych?
-->

1. **Identyfikacja źródeł danych** — lista potencjalnych źródeł, tabel, systemów
2. **Uzyskanie dostępu do danych** — formalne wnioski o dostęp, compliance check
3. **Profilowanie danych** — statystyki opisowe, rozkłady, missing values, outliers
4. **Ocena jakości danych** — completeness, accuracy, timeliness, consistency
5. **Ocena historii danych** — długość historii, stabilność definicji, zmiany w czasie
6. **Analiza dopuszczalności** — weryfikacja RODO, zakazy stosowania zmiennych
7. **Exploratory Data Analysis (EDA)** — wstępne badanie relacji w danych
8. **Przygotowanie Data Assessment Report**
9. **Uzyskanie akceptacji Gate 2** — Data Owner sign-off

---

## Wymagane Artefakty

| Artefakt | Opis | Obowiązkowość |
|----------|------|---------------|
| **Data Assessment Report** | Ocena jakości, dostępności, historii, dopuszczalności | ✅ Obowiązkowy |
| **Data Dictionary (draft)** | Definicje zmiennych, źródła, transformacje | ✅ Obowiązkowy |
| **EDA Report** | Wyniki eksploracyjnej analizy danych | ✅ Obowiązkowy |
| **Data Access Records** | Formalne potwierdzenie dostępu i uprawnień | ✅ Obowiązkowy |
| **RODO Assessment** | Dopuszczalność przetwarzania danych osobowych | ✅ Jeśli dane osobowe |
| **Approval Record (Gate 2)** | Data Owner sign-off | ✅ Obowiązkowy |

---

## Minimalne Wymagania Data Assessment

<!-- PROMPT DLA AUTORA:
Uzupełnij o specyficzne progi jakości danych obowiązujące w organizacji.
Wskaż co jest "deal-breaker" — jakie problemy z danymi blokują dalszy rozwój?
-->

### Kryteria jakości danych

| Wymiar | Minimalne kryterium | Uwagi |
|--------|---------------------|-------|
| Kompletność | Brakujące wartości < [PLACEHOLDER: %] dla zmiennych kluczowych | Do uzupełnienia |
| Pokrycie historyczne | Co najmniej [PLACEHOLDER: N] lat danych historycznych | Zależy od modelu |
| Stabilność definicji | Brak materialnnych zmian definicji w oknie historycznym | Zmiana = potencjalny bias |
| Aktualność | Dane nie starsze niż [PLACEHOLDER: N] miesięcy | Do uzupełnienia |
| Populacja reprezentatywna | Dane reprezentują populację docelową modelu | Bias selection |

### Ocena dopuszczalności prawnej

- [ ] Dane osobowe przetwarzane zgodnie z RODO
- [ ] Zmienne nie zawierają chronionych cech demograficznych (bezpośrednio)
- [ ] Data lineage pozwala na śledzenie pochodzenia danych
- [ ] Data retention policy nie wyklucza planowanego okna historycznego

---

## Kryteria Wejścia (Stage Gate 2 — Input)

- Gate 1 zaakceptowany (Concept Note)
- Dostęp do danych uzyskany lub w trakcie uzyskania

## Kryteria Wyjścia — Stage Gate 2

- [ ] Data Assessment Report ukończony
- [ ] Kluczowe problemy z jakością danych zidentyfikowane i zaadresowane (lub plan działania)
- [ ] Data Dictionary (draft) dostępny
- [ ] RODO assessment zakończony (jeśli dotyczy)
- [ ] Data Owner sign-off udzielony

---

## Specyfika według Kategorii Modelu

| Kategoria | Dodatkowe wymagania na etapie oceny danych |
|-----------|------------------------------------------|
| A — Regulacyjny | Ocena zgodności danych z wymaganiami regulacyjnymi (EBA GL, ECB TRIM); dokumentacja próby treningowej wymagana w MDD |
| B — Scorecard | Analiza populacji aplikacyjnej / behawioralnej; window selection; reject inference jeśli dotyczy |
| C — Supervised ML | Ocena quality etykiet (target leakage check); ocena class imbalance; time-series split jeśli time-series data |
| D — Unsupervised | Szczególna uwaga na outliers i missing values — mogą zaburzić clustering; ocena stabilności podziału w różnych podpróbach |

---

## Najczęstsze Błędy na tym Etapie

<!-- PROMPT DLA AUTORA:
Uzupełnij o typowe problemy z danymi obserwowane w projektach modelowych w organizacji.
-->

- ❌ Pominięcie analizy historii danych — ukryte zmiany w definicjach
- ❌ Brak sprawdzenia target leakage w modelach supervised
- ❌ Niepoprawny time-split (data leakage przez chronologię)
- ❌ Użycie zmiennych niedozwolonych prawnie lub etycznie bez oceny
- ❌ EDA pominięta — model budowany "na ślepo"

---

*Szablony: [Data Assessment Template](../../templates/), [Data Dictionary Template](../../templates/)*
