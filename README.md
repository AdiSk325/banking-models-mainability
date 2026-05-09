# Zarządzanie Procesem Wytwórczym Modeli w Bankowości

Repository dedykowane gromadzeniu wiedzy specjalistycznej dotyczącej zarządzania procesem wytwórczym modeli w bankowości w Polsce.

## 📋 Zakres Tematyczny

Repozytorium obejmuje kompleksową wiedzę na temat:

### ★ Model Lifecycle Guide (główny framework — po polsku)
Nadrzędny przewodnik dla Data Scientistów opisujący pełny cykl życia modelu:
- **Zakres:** Modele regulacyjne · Modele supervised · Modele unsupervised
- **Przeznaczenie:** Codzienny przewodnik nawigacyjny dla DS oraz framework governance
- **Język treści:** Polski
- **Start:** [model_lifecycle_guide/README.md](./model_lifecycle_guide/README.md)

### 1. Modele Klasyczne (Classic Banking Models)
- **PD** - Probability of Default (Prawdopodobieństwo Niewykonania Zobowiązania)
- **LGD** - Loss Given Default (Strata w Przypadku Niewykonania Zobowiązania)
- **Kapitał Regulacyjny** - Regulatory Capital
- **IFRS9** - Modele zgodne z Międzynarodowym Standardem Sprawozdawczości Finansowej 9

### 2. Modele Machine Learning
- **Supervised Learning** - Modele nadzorowane dla ryzyka kredytowego
- **Unsupervised Learning** - Modele nienadzorowane dla ryzyka kredytowego

### 3. Modele Wspierające Procesy Decyzyjne
- Decision Support Systems w bankowości
- Modele scoringowe i aplikacyjne

### 4. Customer Relationship Management (CRM)
- Modele do zarządzania relacjami z klientami
- Modele predykcyjne dla segmentacji i retencji

### 5. Cykl Życia Modelu
- Zarządzanie cyklem życia modeli
- Model Governance i walidacja

## 🗂️ Struktura Projektu

```
banking-models-mainability/
├── model_lifecycle_guide/      # ★ Model Lifecycle Guide — framework dla Data Scientistów
│   ├── README.md               #   → Zacznij tutaj — nawigacja i opis frameworku
│   ├── STATUS.md               #   → Roadmap, postęp prac, ton i zakres
│   ├── 00_guide/               #   Główne rozdziały (11 rozdziałów, po polsku)
│   ├── 01_supporting_standards/#   Standardy Poziomu 2 (STD-001 do STD-008)
│   ├── 02_procedures/          #   Procedury Poziomu 3 (PROC-001 do PROC-006)
│   ├── 03_templates/           #   Szablony Poziomu 4 (TMPL-001 do TMPL-006)
│   ├── 04_references/          #   Źródła i inspiracje (regulacyjne, akademickie, branżowe)
│   └── 05_working_notes/       #   Notatki robocze i pytania otwarte
├── 01_classic_models/          # Modele klasyczne
│   ├── PD/                     # Probability of Default
│   ├── LGD/                    # Loss Given Default
│   ├── regulatory_capital/     # Kapitał regulacyjny
│   └── IFRS9/                  # IFRS9
├── 02_ml_models/               # Modele Machine Learning
│   ├── supervised/             # Uczenie nadzorowane
│   └── unsupervised/           # Uczenie nienadzorowane
├── 03_decision_support/        # Modele decyzyjne
├── 04_CRM/                     # Customer Relationship Management
└── 05_model_lifecycle/         # Zasoby i wiedza specjalistyczna o lifecycle
```

## 🤖 Agent Prompts

W każdym katalogu znajduje się plik `AGENT_PROMPT.md` zawierający szczegółowe instrukcje dla agenta AI, który będzie pogłębiał wiedzę w danym obszarze.

## 🎯 Cel Projektu

Celem projektu jest stworzenie centralnego repozytorium wiedzy, które:
- Standaryzuje podejście do modelowania w bankowości
- Dokumentuje najlepsze praktyki branżowe
- Wspiera rozwój zespołów analitycznych
- Zapewnia zgodność z regulacjami polskimi i międzynarodowymi

## 📚 Dla Kogo?

- Analitycy ryzyka kredytowego
- Data Scientists w sektorze finansowym
- Zespoły zarządzania modelami
- Audytorzy i walidatorzy modeli
- Specjaliści ds. zgodności z regulacjami

## 🚀 Jak Zacząć?

### Dla Data Scientistów (Model Lifecycle Guide)
1. Otwórz [model_lifecycle_guide/README.md](./model_lifecycle_guide/README.md)
2. Znajdź swój scenariusz w tabeli nawigacyjnej ("co muszę zrobić")
3. Przejdź do odpowiedniego rozdziału lub procedury
4. Skorzystaj z szablonów w `model_lifecycle_guide/03_templates/`

### Dla wiedzy specjalistycznej o modelach
1. Wybierz interesujący Cię obszar z struktury katalogów
2. Przeczytaj `AGENT_PROMPT.md` w danym katalogu
3. Zapoznaj się z dokumentacją i przykładami
4. Rozwijaj wiedzę w danym obszarze

## 📖 Licencja

Ten projekt ma charakter edukacyjny i informacyjny.

## 🤝 Współpraca

Zachęcamy do współpracy i rozwijania tego repozytorium wiedzy.