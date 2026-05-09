# Etap 5.9: Zarządzanie Zmianą

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Monitoring](./08_monitoring_przeglad.md) | [Następny: Wycofanie →](./10_wycofanie_archiwizacja.md)

---

## Cel Etapu

Zapewnienie, że zmiany w modelach produkcyjnych przebiegają w sposób kontrolowany, z właściwą oceną wpływu, zatwierdzone przez odpowiednie organy i udokumentowane w pełnym śladzie audytowym.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Data Scientist** | Przygotowanie change request, ocena techniczna |
| **Model Owner** | Inicjacja zmiany, akceptacja ścieżki |
| **MRM** | Klasyfikacja zmiany, decyzja o ścieżce |
| **Niezależny Walidator** | Re-walidacja (jeśli wymagana) |
| **IT / MLOps** | Implementacja techniczna zmiany |
| **Komitet** | Akceptacja zmian materialnych |

---

## Klasyfikacja Zmian

<!-- PROMPT DLA AUTORA:
Uzupełnij o konkretne progi i definicje klasyfikacji zmian obowiązujące w organizacji.
Kto podejmuje decyzję o klasyfikacji?
Jak wygląda dokumentacja zmiany?
-->

### Definicje klas zmian

| Klasa | Opis | Przykłady |
|-------|------|-----------|
| **Zmiana materialna** | Istotna zmiana metodologii, zakresu lub wyników | Nowa metodologia, zmiana zmiennych kluczowych, zmiana populacji docelowej |
| **Zmiana niematerialna** | Rekalibracja, korekta techniczna, drobna aktualizacja danych | Aktualizacja parametrów kalibracji, zmiana window obliczeniowego |
| **Zmiana techniczna** | Infrastrukturalna, bez wpływu na wyniki modelu | Migracja infrastruktury, zmiana platformy, optymalizacja kodu |
| **Zmiana awaryjna** | Natychmiastowa korekta krytycznego błędu | Błąd w kodzie, błędna transformacja danych powodująca materialne odchylenia |

### Ścieżki zatwierdzenia

| Klasa | Wymagana ścieżka |
|-------|-----------------|
| Materialna | Pełna re-walidacja + komitet akceptacji |
| Niematerialna | Ograniczona re-walidacja + MRM sign-off |
| Techniczna | Testy techniczne + IT + MRM informacyjnie |
| Awaryjna | Procedura awaryjna + retroaktywna dokumentacja |

---

## Definicja Zmiany Materialnej

<!-- PROMPT DLA AUTORA:
Podaj precyzyjną definicję materialności przyjętą w organizacji.
Np.: zmiana Gini o >X%, zmiana zmiennej wchodzącej do top-5 wagami, etc.
-->

Zmiana jest **materialna** jeśli spełnia co najmniej jeden z poniższych kryteriów:

- [ ] Zmiana metodologii modelowania (algorytm, transformacja)
- [ ] Dodanie lub usunięcie kluczowej zmiennej wejściowej (np. top-5 wg importance)
- [ ] Zmiana populacji docelowej modelu
- [ ] Zmiana horyzontu predykcji lub targetowanego procesu
- [ ] Oczekiwana zmiana wyników > [PLACEHOLDER: np. 5% Gini / 0.05 AUROC]
- [ ] Zmiana wynikająca ze zmiany regulacyjnej
- [ ] Zmiana w zakresie zastosowania (nowy produkt, nowy region)

Jeśli zmiana nie spełnia powyższych kryteriów — jest niematerialna lub techniczna.

> ⚠️ **W przypadku wątpliwości:** MRM podejmuje decyzję o klasyfikacji. Data Scientist nie decyduje samodzielnie o tym, że zmiana jest niematerialna.

---

## Proces Zarządzania Zmianą

1. **Zgłoszenie potrzeby zmiany** — Model Owner lub DS inicjuje Change Request
2. **Klasyfikacja przez MRM** — MRM decyduje o klasyfikacji i ścieżce
3. **Ocena wpływu (Impact Assessment)** — analiza wpływu zmiany na wyniki, populację, regulacje
4. **Zatwierdzenie ścieżki** — akceptacja przez właściwy organ
5. **Implementacja zmiany** — zgodnie ze standardami developmentu
6. **Testowanie i dokumentacja** — zakres zależy od klasy zmiany
7. **Re-walidacja** — jeśli wymagana przez klasę zmiany
8. **Wdrożenie zmiany** — zgodnie z procedurą wdrożeniową
9. **Aktualizacja dokumentacji** — MDD, Change Log, Model Inventory
10. **Zamknięcie zmiany** — Approval Record, aktualizacja Model Inventory

---

## Wymagane Artefakty

| Artefakt | Opis | Klasa zmiany |
|----------|------|-------------|
| **Change Request Form** | Opis zmiany, uzasadnienie, klasyfikacja | Wszystkie |
| **Impact Assessment** | Ocena wpływu na wyniki, populację, regulacje | Materialna, Awaryjna |
| **Updated MDD** | Aktualizacja dokumentacji modelu | Materialna, Niematerialna |
| **Updated Assumptions Register** | Aktualizacja założeń | Jeśli zmienione |
| **Change Test Results** | Wyniki testów po zmianie | Materialna, Niematerialna |
| **Validation Report (partial/full)** | Raport z re-walidacji | Materialna (pełna), Niematerialna (ograniczona) |
| **Approval Record** | Akceptacja zmiany | Wszystkie |
| **Change Log Update** | Zapis w historii zmian modelu | Wszystkie |

---

## Wersjonowanie Modelu

<!-- PROMPT DLA AUTORA:
Opisz schemat wersjonowania modeli przyjęty w organizacji.
Jak wersje są przechowywane? Jakie są wymogi archiwizacji poprzednich wersji?
-->

Każda zmiana modelu powoduje powstanie nowej wersji:

| Klasa zmiany | Zmiana wersji | Przykład |
|-------------|---------------|---------|
| Materialna | Major version | v1.0 → v2.0 |
| Niematerialna | Minor version | v1.0 → v1.1 |
| Techniczna | Patch version | v1.0.0 → v1.0.1 |

Poprzednie wersje modelu muszą być zachowane w repozytorium przez [PLACEHOLDER: N lat].

---

## Szczególna Sytuacja: Modele Regulacyjne i Zmiany Nadzorcze

<!-- PROMPT DLA AUTORA:
Opisz procedurę powiadamiania regulatora o zmianach w modelach IRB.
Kiedy wymagana jest uprzednia zgoda nadzorcy?
-->

Dla modeli Kategorii A (regulacyjnych), każda materialna zmiana wymaga oceny:
- Czy zmiana wymaga uprzedniej zgody nadzorcy (EBC, KNF)?
- Czy zmiana wymaga notyfikacji nadzorcy?
- Czy zmiana wymaga aktualizacji dokumentacji regulacyjnej?

---

## Kryteria Wyjścia — Stage Gate 8

- [ ] Change Request zatwierdzony przez właściwy organ
- [ ] Dokumentacja zaktualizowana (MDD, Change Log)
- [ ] Re-walidacja zakończona (jeśli wymagana)
- [ ] Approval Record podpisany
- [ ] Model Inventory zaktualizowany (nowa wersja)

---

*Szablony: [Change Request Form](../../templates/), [Impact Assessment Template](../../templates/), [Change Log Template](../../templates/)*
