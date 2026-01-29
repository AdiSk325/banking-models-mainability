
## Faza 5: Ewaluacja Modelu i Iteracja

### 5.1 Cele Fazy
- Trening i testowanie różnych modeli
- Porównanie performance różnych algorytmów
- Tuning hiperparametrów
- Iteracyjne doskonalenie modelu

### 5.2 Model Development Process

#### Train/Test/Validation Split

```python
from sklearn.model_selection import train_test_split

# Split strategy
X_train, X_temp, y_train, y_temp = train_test_split(
    X, y, test_size=0.4, random_state=42, stratify=y
)

X_val, X_test, y_val, y_test = train_test_split(
    X_temp, y_temp, test_size=0.5, random_state=42, stratify=y_temp
)

# Result: 60% train, 20% validation, 20% test
```

#### Model Selection

```python
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier
import xgboost as xgb

models = {
    'Logistic': LogisticRegression(max_iter=1000),
    'RandomForest': RandomForestClassifier(n_estimators=100),
    'XGBoost': xgb.XGBClassifier(n_estimators=100)
}

results = {}
for name, model in models.items():
    model.fit(X_train, y_train)
    y_pred = model.predict_proba(X_test)[:, 1]
    results[name] = evaluate_model(y_test, y_pred)
```

#### Hyperparameter Tuning

```python
from sklearn.model_selection import GridSearchCV

param_grid = {
    'max_depth': [3, 5, 7],
    'learning_rate': [0.01, 0.1, 0.3],
    'n_estimators': [100, 200, 300]
}

grid_search = GridSearchCV(
    xgb.XGBClassifier(),
    param_grid,
    cv=5,
    scoring='roc_auc',
    n_jobs=-1
)

grid_search.fit(X_train, y_train)
best_model = grid_search.best_estimator_
```

### 5.3 Deliverables
- [x] Model comparison report
- [x] Best model selection
- [x] Hyperparameter tuning results

---

## Faza 6: Weryfikacja na Podpopulacjach

### 6.1 Cele Fazy
- Weryfikacja stabilności modelu
- Test na różnych segmentach
- Identyfikacja bias

### 6.2 Subpopulation Analysis

```python
# Test on different segments
segments = ['retail', 'corporate', 'region_A', 'region_B']

for segment in segments:
    segment_mask = df['segment'] == segment
    X_seg = X_test[segment_mask]
    y_seg = y_test[segment_mask]
    
    performance = evaluate_model(y_seg, model.predict_proba(X_seg)[:, 1])
    print(f"{segment}: GINI={performance['gini']:.3f}")
```

### 6.3 Out-of-Time Validation

```python
# Validation on future time period
oot_data = load_data(start_date='2024-01-01', end_date='2024-12-31')
oot_performance = evaluate_model(oot_data['y'], model.predict_proba(oot_data['X'])[:, 1])
```

### 6.4 Deliverables
- [x] Subpopulation validation report
- [x] Out-of-time validation results
- [x] Stability analysis

---

## Faza 7: Wdrożenie Modelu

### 7.1 Cele Fazy
- Implementacja modelu w środowisku produkcyjnym
- Integracja z systemami bankowymi
- UAT (User Acceptance Testing)

### 7.2 Implementation Checklist

- [ ] Model serialization (pickle/joblib)
- [ ] API development for scoring
- [ ] Integration with core banking system
- [ ] Performance testing (latency < 100ms)
- [ ] Security review
- [ ] UAT with business users
- [ ] Parallel run (old vs new model)
- [ ] Go-live approval

### 7.3 Deployment Code

```python
import joblib

# Save model
joblib.dump(best_model, 'model_v1.pkl')

# Load and score
model = joblib.load('model_v1.pkl')
score = model.predict_proba(new_data)[:, 1]
```

### 7.4 Deliverables
- [x] Production-ready model
- [x] Deployment documentation
- [x] UAT sign-off
- [x] Go-live checklist

---

## Faza 8: Utrzymanie i Monitoring

### 8.1 Cele Fazy
- Ciągły monitoring performance
- Wykrywanie drift
- Regularne review
- Model updates

### 8.2 Monitoring Metrics

```python
# Monthly monitoring
def monitor_model(month_data):
    # Performance monitoring
    actual_default_rate = month_data['actual_default'].mean()
    predicted_default_rate = month_data['predicted_prob'].mean()
    
    # Stability monitoring (PSI)
    psi = calculate_psi(development_scores, month_data['predicted_prob'])
    
    # Data quality
    missing_rate = month_data.isnull().sum() / len(month_data)
    
    return {
        'actual_rate': actual_default_rate,
        'predicted_rate': predicted_default_rate,
        'psi': psi,
        'data_quality': missing_rate
    }
```

### 8.3 Trigger Events for Review
- PSI > 0.25
- Performance degradation > 10%
- Regulatory changes
- Business process changes
- Annual review

### 8.4 Deliverables
- [x] Monitoring dashboard
- [x] Monthly monitoring reports
- [x] Annual review documentation
- [x] Model update log

---

## Faza 9: Sprawdzanie Wartości Biznesowej

### 9.1 Cele Fazy
- Ocena realnego wpływu modelu
- Porównanie z założeniami biznesowymi
- ROI analysis

### 9.2 Business Value Metrics

```markdown
## Business Impact Assessment

### Financial Impact
- Reduced credit losses: PLN 5M annually
- Improved approval rate: +3% (additional PLN 2M revenue)
- Operational efficiency: -20% manual reviews (PLN 1M savings)
- Total NPV: PLN 8M annually

### Non-Financial Impact
- Faster decision time: 5 min → 30 sec
- Improved customer satisfaction: +15%
- Reduced manual workload: 200h/month
```

### 9.3 Performance vs Baseline

| Metric | Baseline | Current Model | Improvement |
|--------|----------|---------------|-------------|
| GINI | 0.38 | 0.47 | +24% |
| Bad Rate | 4.2% | 3.1% | -26% |
| Approval Rate | 72% | 74% | +2pp |

### 9.4 Deliverables
- [x] Business value report
- [x] ROI analysis
- [x] Performance comparison
- [x] Stakeholder presentation

---

## Faza 10: Wyjście z Modelu i Exit Plan

### 10.1 Cele Fazy
- Planowane wycofanie modelu
- Transition do nowego modelu
- Archiwizacja dokumentacji

### 10.2 Exit Criteria

Model powinien być wycofany gdy:
- [ ] Performance degradation nie do naprawienia
- [ ] Nowy, lepszy model dostępny
- [ ] Zmiana regulacyjna wymusza wycofanie
- [ ] Business process fundamentally changed
- [ ] Cost of maintenance > value

### 10.3 Exit Plan Process

**Krok 1: Decision to retire**
- Business case dla wycofania
- Approval od governance committee

**Krok 2: Transition plan**
- Identyfikacja replacement model
- Parallel run period (3-6 miesięcy)
- Gradual transition strategy

**Krok 3: Decommissioning**
- Remove from production
- Archive code and documentation
- Data retention per policy
- Communication to stakeholders

**Krok 4: Post-implementation review**
- Lessons learned
- Knowledge transfer
- Documentation archiving

### 10.4 Documentation Archival

```markdown
## Model Archive Checklist

- [ ] Model code (versioned)
- [ ] Training data (anonymized sample)
- [ ] Development documentation
- [ ] Validation reports
- [ ] Monitoring history
- [ ] Business case and approvals
- [ ] Exit decision documentation
- [ ] Lessons learned

Archive location: [path/to/archive]
Retention period: 10 years (regulatory requirement)
```

### 10.5 Deliverables
- [x] Exit decision document
- [x] Transition plan
- [x] Archived documentation
- [x] Lessons learned report
- [x] Post-implementation review

---

## Podsumowanie Całego Cyklu

### Timeline Overview

| Faza | Typowy Czas | Kluczowe Milestone |
|------|-------------|-------------------|
| 1. Business Definition | 2-4 tygodnie | Go/No-Go decision |
| 2. Data Preparation | 4-8 tygodni | Development dataset ready |
| 3. Target Definition | 1-2 tygodnie | Metrics approved |
| 4. Feature Engineering | 4-8 tygodni | Final feature set |
| 5. Model Development | 4-12 tygodni | Champion model selected |
| 6. Validation | 4-6 tygodni | Validation approved |
| 7. Deployment | 4-8 tygodni | Go-live |
| 8. Monitoring | Ongoing | Monthly reviews |
| 9. Value Assessment | Quarterly | Business value confirmed |
| 10. Exit | When needed | Model retired |

**Total Development Time: 6-12 miesięcy**
**Total Model Lifetime: 3-7 lat typically**

### Critical Success Factors

✅ **Strong business sponsorship**
✅ **Clear problem definition**
✅ **High-quality data**
✅ **Cross-functional collaboration**
✅ **Regulatory compliance from day 1**
✅ **Robust monitoring framework**
✅ **Continuous improvement mindset**

### Common Failure Patterns

❌ Solution looking for problem
❌ Poor data quality
❌ Lack of domain expertise
❌ Insufficient validation
❌ No monitoring post-deployment
❌ Ignoring regulatory requirements

---

## Appendix: Templates i Checklists

### A. Project Charter Template
### B. Data Dictionary Template
### C. Model Development Document Template
### D. Validation Report Template
### E. Monitoring Dashboard Specification
### F. Exit Plan Template

---

**Document Version:** 1.0
**Last Updated:** 2026-01-29
**Author:** Banking Models Knowledge Team
**Status:** Complete

