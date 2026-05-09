# Standard Developmentu Modeli

> **Poziom w hierarchii:** 2 — Standard  
> **Dokument nadrzędny:** [../guide/MODEL_LIFECYCLE_GUIDE.md](../guide/MODEL_LIFECYCLE_GUIDE.md)  
> **Wersja:** 0.1-draft  
> **Status:** Do opracowania — poniżej struktura i prompty dla autora

---

## Cel

Niniejszy standard określa minimalne wymagania dotyczące procesu budowy modeli, standardów kodowania, reproducibility i dokumentacji na etapie developmentu.

---

## Zakres

Dotyczy wszystkich modeli we wszystkich kategoriach (A, B, C, D) opracowywanych w organizacji.

---

## 1. Środowisko Deweloperskie

<!-- PROMPT DLA AUTORA:
Opisz standardowe środowisko deweloperskie przyjęte w organizacji.
Jakie narzędzia są standardowe (IDE, Jupyter, VS Code)?
Jak wygląda zarządzanie środowiskami (conda, pip, Docker)?
Jakie języki programowania są dozwolone/standardowe?
-->

### 1.1 Wymagania techniczne

| Element | Wymaganie | Uwagi |
|---------|-----------|-------|
| Kontrola wersji | Git — obowiązkowy | [PLACEHOLDER: nazwa platformy] |
| Python version | [PLACEHOLDER] | Standardowa wersja organizacji |
| R version | [PLACEHOLDER] | Jeśli stosowany |
| Environment management | [PLACEHOLDER: conda/pip/poetry] | |
| Experiment tracking | [PLACEHOLDER: MLflow/inne] | Obowiązkowy dla Kat. C/D |

---

## 2. Standardy Kodowania

<!-- PROMPT DLA AUTORA:
Opisz standardy kodowania: linting (flake8, black, pylint), naming conventions, structure.
Jakie testy jednostkowe są wymagane?
Jak wygląda dokumentacja kodu (docstrings, type hints)?
-->

### 2.1 Python — minimalne wymagania

- [ ] Formatowanie: [PLACEHOLDER: black/autopep8]
- [ ] Linting: [PLACEHOLDER: flake8/pylint]
- [ ] Type hints: zalecane dla funkcji publicznych
- [ ] Docstrings: obowiązkowe dla publicznych funkcji i klas
- [ ] Testy jednostkowe: [PLACEHOLDER: wymagane / zalecane]

### 2.2 Struktura projektu

<!-- PROMPT DLA AUTORA:
Opisz standardową strukturę projektu modelowego w organizacji.
-->

```
project_name/
├── data/               # Dane (nie commitowane do Git)
├── notebooks/          # Jupyter notebooks (eksperymenty)
├── src/               # Kod produkcyjny
│   ├── features/      # Feature engineering
│   ├── models/        # Definicje modeli
│   ├── evaluation/    # Metryki i ewaluacja
│   └── utils/         # Narzędzia pomocnicze
├── tests/             # Testy jednostkowe
├── docs/              # Dokumentacja (MDD)
├── configs/           # Konfiguracja modeli
├── requirements.txt   # Zależności
└── README.md          # Opis projektu
```

---

## 3. Reproducibility — Odtwarzalność

<!-- PROMPT DLA AUTORA:
Opisz szczegółowe wymagania dotyczące reproducibility.
Jak wygląda zarządzanie seedami, zamrażanie zależności, konteneryzacja?
-->

### Minimalne wymagania

- [ ] Seed losowości ustawiony dla wszystkich procedur stochastycznych
- [ ] Zależności zamrożone (`requirements.txt` z pin-owanymi wersjami)
- [ ] Dane treningowe udokumentowane (snapshot lub detailed description)
- [ ] Parametry modelu zapisane (config file lub Model Registry)
- [ ] Środowisko dokumentowane (Dockerfile lub environment.yml)

---

## 4. Data Split Strategy

<!-- PROMPT DLA AUTORA:
Opisz obowiązującą strategię podziału danych.
Kiedy stosować time-split vs random split? Jak definiować OOT?
-->

### Zasady podziału danych

| Typ podziału | Kiedy stosować | Minimum OOT |
|-------------|----------------|-------------|
| Time-based split | Zawsze dla modeli credit risk | [PLACEHOLDER: N miesięcy] |
| Random split | Tylko gdy dane nie są time-series | — |
| Cross-validation | Jako uzupełnienie (nie zastąpienie holdout) | — |

**Wymagany podział dla modeli produkcyjnych:**
- Train: [PLACEHOLDER: np. 60-70%]
- Validation: [PLACEHOLDER: np. 15-20%]
- Test (hold-out): [PLACEHOLDER: np. 15-20%]
- OOT (Out-of-Time): obowiązkowy — ostatnie [PLACEHOLDER: N] miesięcy danych

---

## 5. Experiment Tracking

<!-- PROMPT DLA AUTORA:
Opisz wymagania dotyczące experiment tracking.
Jaką platformę stosuje organizacja?
Co musi być logowane?
-->

Dla modeli Kategorii C i D (ML), obowiązkowe jest śledzenie eksperymentów:

Każdy eksperyment musi rejestrować:
- [ ] Parametry modelu i konfigurację
- [ ] Metryki performance (train, val, test)
- [ ] Informacje o danych (wersja, split)
- [ ] Seed i informacje o środowisku
- [ ] Artefakty (model, feature importance)

---

## 6. Code Review — Wymagania

<!-- PROMPT DLA AUTORA:
Opisz proces code review obowiązujący w organizacji.
Kto może być recenzentem? Jakie są kryteria akceptacji?
-->

Każdy model produkcyjny musi przejść code review przez co najmniej jedną osobę inną niż autor.

**Minimalne kryteria akceptacji code review:**
- [ ] Kod działa i jest możliwy do odtworzenia
- [ ] Brak oczywistych błędów logicznych
- [ ] Dokumentacja kodu jest kompletna
- [ ] Brak hardcoded credentials
- [ ] Obsługiwanie edge cases
- [ ] Testy jednostkowe (jeśli wymagane)

---

## Powiązane Dokumenty

- [Guide — Etap 5.3: Budowa Modelu](../guide/05_etapy/03_projektowanie_rozwoj.md)
- [Standard Dokumentacji](./documentation_standard.md)
- [Standard MLOps](./mlops_standard.md)
- [MDD Template](../templates/)
