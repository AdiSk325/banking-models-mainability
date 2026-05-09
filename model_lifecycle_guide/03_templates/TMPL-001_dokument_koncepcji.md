# TMPL-001: Dokument Koncepcji Modelu (Model Concept Note)

> **Kiedy używać:** Na etapie inicjacji projektu modelarskiego (Etap 1–2)  
> **Kto wypełnia:** Data Scientist + Model Owner  
> **Cel:** Uzasadnienie biznesowe i wstępna charakterystyka modelu do zatwierdzenia przez MRM

---

## Instrukcja wypełnienia

Zastąp tekst w nawiasach `[...]` właściwą treścią. Usuń komentarze w kursywie po wypełnieniu.

---

# Dokument Koncepcji Modelu

**ID modelu:** `[zostanie nadane przez MRM]`  
**Nazwa modelu:** `[opisowa nazwa modelu]`  
**Data:** `[RRRR-MM-DD]`  
**Data Scientist:** `[imię i nazwisko]`  
**Model Owner:** `[imię i nazwisko i jednostka]`  
**Wersja dokumentu:** `0.1`

---

## 1. Problem Biznesowy

*Opisz problem biznesowy lub regulacyjny, który model ma rozwiązać. Co się stanie jeśli model nie zostanie zbudowany?*

[Opis problemu]

---

## 2. Cel Modelu

*Zdefiniuj precyzyjnie co model ma przewidywać lub obliczać.*

**Pytanie modelarskie:** `[np. "Jakie jest prawdopodobieństwo, że klient nie spłaci kredytu w ciągu 12 miesięcy?"]`

**Populacja docelowa:** `[np. "Klienci indywidualni z aktywnym kredytem konsumpcyjnym"]`

**Zastosowanie:** `[np. "Automatyczny scoring przy wnioskowaniu o kredyt"]`

---

## 3. Typ Modelu

| Aspekt | Odpowiedź |
|---|---|
| Kategoria | ☐ Regulacyjny ☐ Supervised ☐ Unsupervised ☐ Inny |
| Klasa techniczna | ☐ Klasyfikacja ☐ Regresja ☐ Clustering ☐ Anomalia ☐ Inne |
| Regulacje | `[np. "IRB PD" lub "Brak"]` |

---

## 4. Proponowana Klasyfikacja Tieru

**Proponowany tier:** `[1 / 2 / 3]`

**Uzasadnienie tieru:**

| Kryterium | Ocena | Uzasadnienie |
|---|---|---|
| Wpływ finansowy | Wysoki / Średni / Niski | |
| Wpływ regulacyjny | Tak / Pośredni / Nie | |
| Automatyzacja decyzji | Pełna / Częściowa / Nie | |
| Skala populacji | Wysoka / Średnia / Niska | |

---

## 5. Dane

**Wstępna ocena dostępności danych:**

| Źródło danych | Dostępność | Zakres | Uwagi |
|---|---|---|---|
| [Źródło 1] | ☐ Dostępne ☐ Do potwierdzenia | | |
| [Źródło 2] | ☐ Dostępne ☐ Do potwierdzenia | | |

**Wstępne ryzyko datowe:** `[Opisz główne ryzyka związane z danymi]`

---

## 6. Proponowana Metodologia

*Wstępna propozycja podejścia — może ulec zmianie po głębszej analizie.*

`[np. "Logistic Regression lub Gradient Boosting — do decyzji po EDA"]`

---

## 7. Harmonogram i Zasoby

| Element | Szacunek |
|---|---|
| Czas developmentu | `[X tygodni / miesięcy]` |
| Czas walidacji | `[X tygodni]` |
| Data planowanego wdrożenia | `[RRRR-MM]` |
| Wymagane zasoby (osoby) | `[np. 1 DS seniorski + 1 DS junior]` |

---

## 8. Zatwierdzenia

| Rola | Imię i Nazwisko | Podpis | Data |
|---|---|---|---|
| Data Scientist | | | |
| Model Owner | | | |
| MRM (tier confirmation) | | | |

---

## 9. Uwagi MRM

*Wypełnia MRM po przejrzeniu dokumentu.*

`[Uwagi, korekty tieru, dodatkowe wymagania]`

---

*Szablon v0.5 | Powiązany standard: STD-001, STD-005 | Powiązana procedura: PROC-001*
