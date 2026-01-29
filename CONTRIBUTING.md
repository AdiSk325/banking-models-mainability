# Wytyczne dla Kontrybutorów

## Jak Wnieść Wkład do Repozytorium

Dziękujemy za zainteresowanie rozwijaniem tego repozytorium wiedzy!

## Proces Kontrybuowania

### 1. Fork i Clone
```bash
git clone https://github.com/AdiSk325/banking-models-mainability.git
cd banking-models-mainability
```

### 2. Wybierz Obszar
Wybierz jeden z katalogów głównych:
- `01_classic_models/` - Modele klasyczne
- `02_ml_models/` - Machine Learning
- `03_decision_support/` - Decision Support
- `04_CRM/` - Customer Relationship Management
- `05_model_lifecycle/` - Model Governance

### 3. Przeczytaj AGENT_PROMPT.md
W wybranym katalogu znajdź `AGENT_PROMPT.md` z instrukcjami.

### 4. Twórz Treść
Dodawaj pliki zgodnie ze standardami:

#### Struktura Plików
```
kategoria/
├── 01_theory/
│   └── concept.md
├── 02_implementation/
│   ├── example.py
│   └── example.ipynb
├── 03_examples/
│   └── use_case.md
├── 04_best_practices/
│   └── guidelines.md
├── 05_regulatory/
│   └── requirements.md
└── 06_case_studies/
    └── case_study.md
```

### 5. Standardy Kodu

#### Python
- PEP 8 style guide
- Type hints
- Docstrings (Google style)
- Unit tests (pytest)

```python
def calculate_pd(features: pd.DataFrame, model: Any) -> np.ndarray:
    """
    Oblicza prawdopodobieństwo defaultu.
    
    Args:
        features: DataFrame ze zmiennymi
        model: Wytrenowany model
        
    Returns:
        Array z prawdopodobieństwami PD
    """
    return model.predict_proba(features)[:, 1]
```

#### R
- tidyverse style guide
- roxygen2 documentation

### 6. Standardy Dokumentacji

#### Markdown
- Nagłówki hierarchiczne
- Code blocks z językiem
- Linki relative
- Spis treści dla długich dokumentów

#### Jupyter Notebooks
- Markdown cells dla wyjaśnień
- Clear outputs
- Linear flow
- Requirements na początku

### 7. Dane

**WAŻNE:** 
- ❌ NIE DODAWAJ prawdziwych danych bankowych
- ✅ Używaj syntetycznych danych
- ✅ Dokumentuj strukturę danych
- ✅ Przykłady realistyczne ale anonimowe

#### Generowanie Syntetycznych Danych
```python
from faker import Faker
import numpy as np

fake = Faker('pl_PL')

# Przykład syntetycznych danych
data = {
    'client_id': range(1000),
    'age': np.random.randint(18, 80, 1000),
    'income': np.random.lognormal(10, 1, 1000),
}
```

### 8. Git Workflow

```bash
# Stwórz branch dla swojej pracy
git checkout -b feature/pd-models-theory

# Dodaj zmiany
git add 01_classic_models/PD/01_theory/pd_basics.md

# Commit z opisowym message
git commit -m "Dodaj podstawy teoretyczne modeli PD"

# Push do swojego forka
git push origin feature/pd-models-theory
```

### 9. Pull Request
- Opisz dokładnie co dodajesz
- Linkuj do AGENT_PROMPT.md
- Dodaj screenshots jeśli applicable
- Zaznacz checklistę co zostało zrobione

## Co Dodawać

### Priorytetowe
✅ Dokumentacja teoretyczna  
✅ Working code examples  
✅ Regulatory guidelines  
✅ Best practices  
✅ Case studies (na syntetycznych danych)  
✅ Visualizations i diagrams  

### Pomocne
✅ Jupyter notebooks  
✅ Excel templates  
✅ SQL queries  
✅ API examples  
✅ Testing frameworks  

### Unikaj
❌ Prawdziwe dane klientów/banków  
❌ Proprietary code  
❌ Incomplete examples  
❌ Broken code  
❌ Nieudokumentowany kod  

## Quality Checklist

Przed Pull Request sprawdź:

- [ ] Kod działa (tested locally)
- [ ] Dokumentacja jest kompletna
- [ ] Brak prawdziwych danych
- [ ] Style guide przestrzegany
- [ ] Linki działają
- [ ] Spellcheck wykonany
- [ ] Code comments dodane
- [ ] README zaktualizowany jeśli potrzebne

## Kontekst Polski

Pamiętaj o:
- Terminologii w języku polskim
- Wymogach KNF
- Polskich regulacjach (RODO, etc.)
- Praktykach polskich banków
- Realiach polskiego rynku

## Licencja

Wnosząc wkład, zgadzasz się na udostępnienie treści na licencji projektu.

## Pytania?

Otwórz Issue z pytaniem lub propozycją.

## Code of Conduct

- Bądź profesjonalny
- Szanuj innych kontrybutorów
- Konstruktywna krytyka
- Fokus na jakości wiedzy

## Recenzje

Wszystkie Pull Requesty będą zrecenzowane pod kątem:
- Poprawności merytorycznej
- Jakości kodu
- Kompletności dokumentacji
- Zgodności ze standardami

Dziękujemy za wkład w rozwój wiedzy o modelach bankowych! 🚀
