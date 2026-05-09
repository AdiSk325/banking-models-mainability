# Quick Reference - Repozytorium Modeli Bankowych

## 🎯 Co to Jest?

Repozytorium wiedzy specjalistycznej o zarządzaniu procesem wytwórczym modeli w bankowości w Polsce.

## 📁 Struktura (Quick View)

| Katalog | Opis | Agent Prompt |
|---------|------|--------------|
| **model_lifecycle_guide/** | ★ Model Lifecycle Guide — framework dla DS (po polsku) | — |
| ├─ 00_guide/ | Główne rozdziały przewodnika (01–11) | — |
| ├─ 01_supporting_standards/ | Standardy STD-001 do STD-008 | — |
| ├─ 02_procedures/ | Procedury PROC-001 do PROC-006 | — |
| ├─ 03_templates/ | Szablony TMPL-001 do TMPL-006 | — |
| ├─ 04_references/ | Referencje regulacyjne i branżowe | — |
| └─ 05_working_notes/ | Notatki robocze | — |
| **01_classic_models/** | Modele klasyczne | |
| ├─ PD/ | Probability of Default | ✅ |
| ├─ LGD/ | Loss Given Default | ✅ |
| ├─ regulatory_capital/ | Kapitał regulacyjny (Basel II/III) | ✅ |
| └─ IFRS9/ | Expected Credit Loss | ✅ |
| **02_ml_models/** | Machine Learning | |
| ├─ supervised/ | Modele nadzorowane (XGBoost, etc.) | ✅ |
| └─ unsupervised/ | Modele nienadzorowane (clustering, etc.) | ✅ |
| **03_decision_support/** | Systemy wspomagania decyzji | ✅ |
| **04_CRM/** | Customer Relationship Management | ✅ |
| **05_model_lifecycle/** | Zasoby i wiedza specjalistyczna o lifecycle | ✅ |

## 📚 Kluczowe Dokumenty

| Dokument | Cel |
|----------|-----|
| `README.md` | Główny opis projektu |
| `GUIDE_FOR_AGENTS.md` | Przewodnik dla agentów AI |
| `CONTRIBUTING.md` | Jak kontrybuować |
| `AGENT_PROMPT.md` | Instrukcje dla agenta w każdym katalogu |

## 🔑 Kluczowe Tematy

### Modele Klasyczne
- **PD**: Modele prawdopodobieństwa defaultu (logit, probit, ML)
- **LGD**: Modele straty (recovery, downturn LGD, workout)
- **Kapitał**: RWA, Basel II/III, IRB, SA
- **IFRS9**: ECL, staging, forward-looking, scenarios

### Machine Learning
- **Supervised**: XGBoost, Random Forest, Neural Nets, SHAP
- **Unsupervised**: Clustering, PCA, Anomaly Detection

### Decision Support
- Scorecards, Business Rules, Optimization, A/B Testing

### CRM
- CLV, Churn, Cross-sell, Segmentation, NBA

### Governance
- Model Risk, Validation, Monitoring, Documentation

## 🇵🇱 Kontekst Polski

### Regulatorzy
- **KNF** - Komisja Nadzoru Finansowego
- **NBP** - Narodowy Bank Polski
- **EBA** - European Banking Authority (wytyczne)

### Kluczowe Regulacje
- RODO/GDPR
- CRR/CRD IV
- IFRS9
- Rekomendacje KNF

## 🛠️ Tech Stack

### Python
```python
# Core
pandas, numpy, scipy

# ML
scikit-learn, xgboost, lightgbm, catboost

# Explainability
shap, lime

# Viz
matplotlib, seaborn, plotly
```

### R
```r
# Core
tidyverse, data.table

# ML
caret, mlr3, ranger

# Survival
survival, survminer
```

## 🚀 Jak Zacząć dla Agenta?

### Dla Model Lifecycle Guide (Data Scientist)
1. **Otwórz** [`model_lifecycle_guide/README.md`](./model_lifecycle_guide/README.md)
2. **Przejrzyj STATUS.md** — znajdziesz tam intended scope i ton dokumentu
3. **Uzupełnij treść** w sekcjach oznaczonych `✍️ [DO UZUPEŁNIENIA]`
4. **Zachowaj język** — treść po polsku, nazwy plików angielskie

### Dla innych obszarów wiedzy
1. **Wybierz obszar** (np. `01_classic_models/PD/`)
2. **Przeczytaj** `AGENT_PROMPT.md`
3. **Stwórz strukturę**:
   ```
   PD/
   ├── 01_theory/
   ├── 02_implementation/
   ├── 03_examples/
   ├── 04_best_practices/
   ├── 05_regulatory/
   └── 06_case_studies/
   ```
4. **Wypełnij treścią** (MD + code + notebooks)
5. **Commit** i push

## ✅ Quality Checklist

- [ ] Dokumentacja teoretyczna kompletna
- [ ] Code examples działają
- [ ] Syntetyczne dane (NIE prawdziwe!)
- [ ] Regulatory context uwzględniony
- [ ] Polski kontekst zawarty
- [ ] Best practices opisane
- [ ] Case studies dodane

## 📊 Przykładowa Treść

### Theory Document
```markdown
# Podstawy PD

## Definicja
PD (Probability of Default) to...

## Metodologie
1. Logistic Regression
2. Machine Learning
3. ...

## Kod
[Python example]

## Regulacje
KNF wymaga...
```

### Code Example
```python
# pd_model.py
import pandas as pd
from sklearn.linear_model import LogisticRegression

def train_pd_model(X_train, y_train):
    """Trenuje model PD."""
    model = LogisticRegression()
    model.fit(X_train, y_train)
    return model
```

## 🎓 Zasoby

### Regulacyjne
- Basel Committee on Banking Supervision
- EBA Guidelines
- KNF Rekomendacje

### Akademickie
- Journal of Banking & Finance
- Risk.net
- Credit Research Foundation

### Tools
- GitHub - version control
- Jupyter - notebooks
- Python/R - implementacje

## 🤝 Współpraca

Otwórz Pull Request z:
1. Opisem co dodajesz
2. Referencją do AGENT_PROMPT.md
3. Checklist co zostało zrobione

## 📞 Support

Pytania? Otwórz Issue w repo.

---

**Wersja:** 1.0  
**Data:** 2026-01-29  
**Status:** Initial Structure Complete ✅
