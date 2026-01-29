# Template: Dokumentacja Znalezisk Badawczych

## Informacje o Szablonie

**Cel:** Standaryzacja dokumentowania znalezisk z prac naukowych i wiedzy specjalistycznej  
**Zastosowanie:** Synteza wiedzy z publikacji, white papers, dokumentów regulacyjnych  
**Format:** Markdown (.md)

---

## Metadata Dokumentu

| Pole | Wartość |
|------|---------|
| **Tytuł znaleziska** | [Tytuł opisowy, np. "Implementacja PSI dla monitorowania stabilności modeli"] |
| **Data stworzenia** | [YYYY-MM-DD] |
| **Autor dokumentacji** | [Imię Nazwisko lub ID] |
| **Kategoria** | [Model Governance / Validation / Monitoring / MLOps / etc.] |
| **Poziom** | [Podstawowy / Średniozaawansowany / Zaawansowany] |
| **Status** | [Draft / Review / Approved / Archived] |
| **Wersja** | [X.Y] |

---

## 1. Źródła

### 1.1 Publikacja Główna

**Tytuł:**  
[Pełny tytuł publikacji]

**Autorzy:**  
[Lista autorów]

**Publikacja/Wydawca:**  
[Nazwa czasopisma/wydawcy, rok]

**DOI/Link:**  
[DOI lub link do publikacji]

**Typ źródła:**  
- [ ] Artykuł naukowy (peer-reviewed)
- [ ] Książka/Monografia
- [ ] Dokument regulacyjny
- [ ] White paper
- [ ] Raport branżowy
- [ ] Standard/Wytyczne
- [ ] Inne: ___________

### 1.2 Źródła Wspierające

1. [Tytuł 1] - [Autorzy] - [Rok] - [Link]
2. [Tytuł 2] - [Autorzy] - [Rok] - [Link]
3. ...

---

## 2. Streszczenie Wykonawcze

**Dla kogo:** [Docelowa grupa: model developers, validators, risk managers, etc.]

**Kluczowe przesłanie (3-5 zdań):**  
[Najważniejsze wnioski w skondensowanej formie]

**Praktyczne zastosowanie:**  
[W jakich sytuacjach ta wiedza jest przydatna]

**Quick wins:**  
- [Co można wdrożyć od razu]
- [Szybkie ulepszenia]

---

## 3. Szczegółowe Znaleziska

### 3.1 Problem/Kontekst

**Jaki problem rozwiązuje:**  
[Opis problemu biznesowego lub technicznego]

**Kontekst zastosowania:**  
[W jakich warunkach/sytuacjach ma zastosowanie]

**Założenia:**  
- [Założenie 1]
- [Założenie 2]
- ...

### 3.2 Proponowane Rozwiązanie

**Podejście/Metodologia:**  
[Opis proponowanego rozwiązania]

**Kluczowe komponenty:**  
1. [Komponent 1 - opis]
2. [Komponent 2 - opis]
3. ...

**Algorytm/Proces (jeśli dotyczy):**  
```
Krok 1: [Opis]
Krok 2: [Opis]
Krok 3: [Opis]
...
```

**Formuły matematyczne (jeśli dotyczy):**  
[Kluczowe wzory w LaTeX lub opis tekstowy]

### 3.3 Implementacja

**Wymagania techniczne:**  
- Narzędzia: [lista narzędzi]
- Dane: [wymagania dotyczące danych]
- Infrastruktura: [wymagania IT]
- Kompetencje: [wymagane umiejętności]

**Przykładowy kod (jeśli dotyczy):**  
```python
# Przykład implementacji
# (lub link do Jupyter Notebook)
```

**Parametry do konfiguracji:**  
| Parametr | Opis | Wartość domyślna | Zakres |
|----------|------|------------------|--------|
| param1   | ...  | ...              | ...    |
| param2   | ...  | ...              | ...    |

### 3.4 Wyniki i Metryki

**Metryki sukcesu:**  
- [Metryka 1: jak mierzyć]
- [Metryka 2: jak mierzyć]

**Oczekiwane rezultaty:**  
[Co osiągniemy po wdrożeniu]

**Benchmarki (jeśli dostępne):**  
[Wyniki z publikacji lub praktyki]

---

## 4. Analiza Krytyczna

### 4.1 Mocne Strony

- ✅ [Zaleta 1]
- ✅ [Zaleta 2]
- ✅ [Zaleta 3]

### 4.2 Ograniczenia

- ⚠️ [Ograniczenie 1]
- ⚠️ [Ograniczenie 2]
- ⚠️ [Ograniczenie 3]

### 4.3 Ryzyko i Challenges

**Potencjalne ryzyka:**  
1. [Ryzyko 1] - Mitygacja: [jak zarządzać]
2. [Ryzyko 2] - Mitygacja: [jak zarządzać]

**Wyzwania implementacyjne:**  
- [Challenge 1]
- [Challenge 2]

### 4.4 Porównanie z Alternatywami

**Alternatywne podejścia:**  
| Podejście | Zalety | Wady | Kiedy stosować |
|-----------|--------|------|----------------|
| To rozwiązanie | ... | ... | ... |
| Alternatywa 1 | ... | ... | ... |
| Alternatywa 2 | ... | ... | ... |

---

## 5. Kontekst Regulacyjny

### 5.1 Zgodność z Regulacjami

**Regulacje wspierane:**  
- [ ] SR 11-7 (USA)
- [ ] SS1/23 (UK)
- [ ] EBA Guidelines
- [ ] ECB TRIM
- [ ] KNF Recommendations
- [ ] IFRS 9
- [ ] RODO/GDPR
- [ ] Inne: ___________

**Jak wspiera compliance:**  
[Opis jak rozwiązanie pomaga w spełnieniu wymagań regulacyjnych]

### 5.2 Wymagania Dokumentacyjne

**Dokumentacja wymagana przez regulatory:**  
- [Dokument 1]
- [Dokument 2]

**Jak dokumentować:**  
[Wskazówki dotyczące dokumentacji dla audytorów/regulatorów]

---

## 6. Zastosowanie w Bankowości Polskiej

### 6.1 Specyfika Polska

**Kontekst polski:**  
[Jak zastosować w polskim środowisku bankowym]

**Uwagi dot. KNF:**  
[Dodatkowe wymagania lub uwagi dla polskich banków]

**Praktyki polskich banków:**  
[Jeśli znane - jak polskie banki podchodzą do tego tematu]

### 6.2 Case Study (jeśli dostępny)

**Instytucja:** [Zanonimizowana nazwa lub "Bank X"]  
**Kontekst:** [Opis sytuacji]  
**Wdrożenie:** [Jak wdrożono]  
**Wyniki:** [Co osiągnięto]  
**Lessons learned:** [Wnioski]

---

## 7. Praktyczne Wskazówki

### 7.1 Krok po Kroku - Jak Zastosować

**Faza 1: Przygotowanie**  
- [ ] [Zadanie 1]
- [ ] [Zadanie 2]
- [ ] ...

**Faza 2: Implementacja**  
- [ ] [Zadanie 1]
- [ ] [Zadanie 2]
- [ ] ...

**Faza 3: Walidacja**  
- [ ] [Zadanie 1]
- [ ] [Zadanie 2]
- [ ] ...

**Faza 4: Wdrożenie i Monitoring**  
- [ ] [Zadanie 1]
- [ ] [Zadanie 2]
- [ ] ...

### 7.2 Best Practices

**Do's:**  
- ✅ [Dobra praktyka 1]
- ✅ [Dobra praktyka 2]
- ✅ [Dobra praktyka 3]

**Don'ts:**  
- ❌ [Czego unikać 1]
- ❌ [Czego unikać 2]
- ❌ [Czego unikać 3]

### 7.3 Gotowe Artefakty

**Templates dostępne:**  
- [Link do template 1]
- [Link do template 2]

**Code snippets:**  
- [Link do przykładowego kodu]

**Dashboards/Wizualizacje:**  
- [Link do przykładowych dashboardów]

---

## 8. Dalsze Zasoby

### 8.1 Powiązane Znaleziska

**W tym repozytorium:**  
- [Link do powiązanego znaleziska 1]
- [Link do powiązanego znaleziska 2]

**Zależności:**  
- Wymaga znajomości: [temat 1], [temat 2]
- Naturalnie prowadzi do: [kolejny temat]

### 8.2 Rekomendowana Literatura

**Do dalszej eksploracji:**  
1. [Tytuł 1] - dla [pogłębienia aspektu X]
2. [Tytuł 2] - dla [praktycznych przykładów]
3. [Tytuł 3] - dla [teoretycznych podstaw]

### 8.3 Narzędzia i Zasoby Online

**Przydatne narzędzia:**  
- [Nazwa narzędzia 1] - [Link] - [Opis]
- [Nazwa narzędzia 2] - [Link] - [Opis]

**Kursy online/Webinary:**  
- [Tytuł kursu] - [Platforma] - [Link]

**Communities:**  
- [Nazwa community] - [Link] - [Focus]

---

## 9. FAQ

### Q1: [Często zadawane pytanie 1]?
**A:** [Odpowiedź]

### Q2: [Często zadawane pytanie 2]?
**A:** [Odpowiedź]

### Q3: [Często zadawane pytanie 3]?
**A:** [Odpowiedź]

---

## 10. Changelog

| Data | Wersja | Autor | Zmiany |
|------|--------|-------|--------|
| YYYY-MM-DD | 1.0 | [Imię] | Utworzenie dokumentu |
| YYYY-MM-DD | 1.1 | [Imię] | [Opis zmian] |

---

## 11. Review i Zatwierdzenie

| Rola | Imię | Data Review | Status | Komentarze |
|------|------|-------------|--------|------------|
| Technical Reviewer | [Imię] | YYYY-MM-DD | [Approved/Changes Requested] | [Komentarze] |
| Subject Matter Expert | [Imię] | YYYY-MM-DD | [Approved/Changes Requested] | [Komentarze] |
| Compliance Officer | [Imię] | YYYY-MM-DD | [Approved/Changes Requested] | [Komentarze] |

---

## 12. Załączniki

### A. Dodatkowe Diagramy
[Link lub embed]

### B. Detailed Calculations
[Link do spreadsheet lub notebook]

### C. Validation Results
[Link do wyników walidacji/testów]

---

## Notatki

[Miejsce na dodatkowe notatki, obserwacje, pytania do eksploracji]

---

**Template Version:** 1.0  
**Last Updated:** 2026-01-29  
**Maintained by:** Banking Models Knowledge Team
