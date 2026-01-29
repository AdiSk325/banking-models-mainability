# Przewodnik dla Agentów AI

## Wprowadzenie

Ten dokument stanowi przewodnik dla agentów AI, którzy będą rozwijać wiedzę w poszczególnych obszarach repozytorium.

## Struktura Repozytorium

Repozytorium jest zorganizowane tematycznie według głównych obszarów modelowania w bankowości:

```
01_classic_models/      → Modele klasyczne (PD, LGD, Kapitał, IFRS9)
02_ml_models/           → Modele Machine Learning (Supervised, Unsupervised)
03_decision_support/    → Systemy wspierania decyzji
04_CRM/                 → Customer Relationship Management
05_model_lifecycle/     → Zarządzanie cyklem życia modeli
```

## Jak Korzystać z Agent Prompts

### Krok 1: Wybierz Obszar
Zidentyfikuj obszar, w którym chcesz pogłębić wiedzę.

### Krok 2: Przeczytaj AGENT_PROMPT.md
W każdym katalogu znajdziesz plik `AGENT_PROMPT.md` zawierający:
- Definicję roli agenta
- Szczegółowe zadania do wykonania
- Kontekst polski i regulacyjny
- Oczekiwane deliverables
- Format dostarczenia wiedzy

### Krok 3: Rozwijaj Wiedzę
Agent powinien stworzyć kompletną dokumentację obejmującą wszystkie punkty z prompta:
- Dokumentację teoretyczną
- Przykłady kodu (Python/R)
- Case studies
- Best practices
- Regulatory guidelines

### Krok 4: Organizuj Treść
Twórz podkatalogi i pliki zgodnie z tematyką:
```
katalog_glowny/
├── AGENT_PROMPT.md          (instrukcje dla agenta)
├── README.md                (opis obszaru)
├── 01_theory/               (teoria i podstawy)
├── 02_implementation/       (implementacje)
├── 03_examples/             (przykłady)
├── 04_best_practices/       (dobre praktyki)
├── 05_regulatory/           (wymagania regulacyjne)
└── 06_case_studies/         (case studies)
```

## Standardy Dokumentacji

### Markdown Files
- Używaj nagłówków hierarchicznie (H1 → H2 → H3)
- Dodawaj spis treści dla długich dokumentów
- Stosuj code blocks z określeniem języka
- Dodawaj diagramy (Mermaid) gdzie możliwe

### Code Examples
- **Python**: Jupyter Notebooks (.ipynb) lub skrypty (.py)
- **R**: R Markdown (.Rmd) lub skrypty (.R)
- Komentarze w języku polskim lub angielskim
- Docstrings dla funkcji
- Type hints w Pythonie

### Data
- Używaj syntetycznych danych
- NIE WŁĄCZAJ prawdziwych danych bankowych
- Dokumentuj strukturę danych (data dictionary)
- Przykłady powinny być realistyczne ale anonimowe

## Kontekst Regulacyjny Polski

### Kluczowe Instytucje
- **KNF** (Komisja Nadzoru Finansowego) - nadzór bankowy
- **NBP** (Narodowy Bank Polski) - bank centralny
- **UOKiK** - ochrona konkurencji i konsumentów

### Kluczowe Regulacje
- **RODO/GDPR** - ochrona danych osobowych
- **Rekomendacje KNF** - zarządzanie ryzykiem
- **CRR/CRD IV** - wymogi kapitałowe
- **IFRS9** - sprawozdawczość finansowa

## Narzędzia i Biblioteki

### Python
- **pandas, numpy** - manipulacja danymi
- **scikit-learn** - machine learning
- **xgboost, lightgbm** - gradient boosting
- **shap, lime** - explainability
- **matplotlib, seaborn, plotly** - wizualizacje
- **statsmodels** - statystyka
- **scipy** - funkcje naukowe

### R
- **tidyverse** - manipulacja danymi
- **caret, mlr3** - machine learning
- **ggplot2** - wizualizacje
- **survival** - survival analysis

### Inne
- **Jupyter** - interactive notebooks
- **Git** - version control
- **Docker** - containerization

## Best Practices dla Agentów

### 1. Kompleksowość
Omawiaj tematy dogłębnie, nie powierzchownie.

### 2. Praktyczność
Zawsze dostarczaj working code examples, nie tylko teorię.

### 3. Aktualność
Uwzględniaj najnowsze regulacje i praktyki rynkowe.

### 4. Kontekst Polski
Adaptuj wiedzę międzynarodową do realiów polskiego rynku.

### 5. Wyjaśnialność
Tłumacz złożone koncepcje prostym językiem.

### 6. Struktura
Organizuj wiedzę logicznie i hierarchicznie.

### 7. Referencje
Cytuj źródła, regulacje, i literaturę akademicką.

### 8. Przykłady
Dostarczaj konkretne przykłady z bankowości.

## Współpraca Między Agentami

Agenci mogą odnosić się do wiedzy z innych obszarów:
- PD models mogą być wykorzystane w IFRS9
- ML models mogą wspierać Credit Scoring
- CRM models korzystają z segmentacji
- Wszystkie modele podlegają governance

## Glossary

Stwórz glossary terminów technicznych i regulacyjnych w języku polskim i angielskim.

## Changelog

Dokumentuj zmiany i aktualizacje w poszczególnych obszarach.

## Kontakt i Feedback

Zachęcamy do iteracyjnego rozwoju i ulepszania dokumentacji na podstawie feedbacku użytkowników.
