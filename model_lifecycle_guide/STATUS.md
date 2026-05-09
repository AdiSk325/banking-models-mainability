# STATUS — Roadmap i Status Prac nad Model Lifecycle Guide

> **Cel tego pliku:** Śledzenie postępu prac, zamierzony ton i zakres dokumentu, wskazówki dla przyszłych współtwórców.

---

## Zamierzony ton i zakres dokumentu

### Ton i styl
- **Praktyczny dla Data Scientistów** — przewodnik odpowiada na pytanie "co muszę zrobić", nie tylko "co wymaga regulacja"
- **Normatywny, ale czytelny** — zasady są jasne, lecz język jest zrozumiały dla praktyków
- **Nawigacyjny** — każdy etap wskazuje co zrobić, jakie artefakty wytworzyć, kiedy zaangażować innych
- **Referencyjny** — odsyła do procedur i standardów zamiast je duplikować
- **Po polsku** — cała treść merytoryczna w języku polskim; nazwy plików pozostają angielskie dla skalowalności

### Zakres modeli
Przewodnik obejmuje trzy główne kategorie modeli:

| Kategoria | Przykłady | Uwagi governance |
|---|---|---|
| **Modele regulacyjne** | PD, LGD, EAD, IFRS 9 ECL, stres-testy | Wyższe wymagania walidacji, dokumentacji, change management i zatwierdzenia nadzorczego |
| **Modele supervised** | Scoring, fraud detection, klasyfikacja, regresja | Szczególna uwaga na data split, leakage, backtesting, explainability |
| **Modele unsupervised** | Segmentacja, anomalie, clustering, embeddings | Walidacja business sense, stabilność segmentów, interpretacja bez ground truth |

---

## Roadmap prac

### ✅ Zakończone
- [x] Struktura repozytorium (`model_lifecycle_guide/` z podkatalogami)
- [x] Główny README z nawigacją i zakresem
- [x] STATUS.md (ten plik)
- [x] Szkielet 00_guide/ (wszystkie 11 rozdziałów)
- [x] Szkielet 01_supporting_standards/ (8 standardów)
- [x] Szkielet 02_procedures/ (6 procedur)
- [x] Szkielet 03_templates/ (6 szablonów)
- [x] Szkielet 04_references/ (6 plików referencji)
- [x] Szkielet 05_working_notes/

### 🔄 W trakcie — priorytety na najbliższe sesje

#### Priorytet 1: Rdzeń przewodnika (00_guide/)
- [ ] **01_cel_i_zakres.md** — uzupełnić sekcję definicji i wyjątków
- [ ] **02_zasady_nadrzedne.md** — rozwinąć każdą zasadę z przykładem praktycznym
- [ ] **03_klasyfikacja_modeli.md** — dodać macierz tiering z wymaganiami per tier
- [ ] **04_przeglad_cyklu_zycia.md** — dodać diagram flowchart w Mermaid lub ASCII
- [ ] **05_etapy_cyklu_zycia.md** — uzupełnić wszystkie 13 etapów w pełnym układzie

#### Priorytet 2: Narzędzia dla Data Scientistów
- [ ] **07_wymagane_artefakty.md** — macierz artefaktów per etap i typ modelu
- [ ] **TMPL-001** do **TMPL-006** — wypełnić wszystkie szablony treścią
- [ ] **PROC-001** do **PROC-006** — wypełnić kroki operacyjne

#### Priorytet 3: Standards i governance
- [ ] **06_role_i_odpowiedzialnosci.md** — pełna macierz RACI
- [ ] **STD-001** do **STD-008** — rozwinąć każdy standard
- [ ] **08_kontrole_wyjatki.md** — opisać governance forums i exception management

#### Priorytet 4: Referencje i apendyksy
- [ ] **04_references/** — uzupełnić o polskie regulacje KNF
- [ ] **11_dodatki.md** — glosariusz terminów PL/EN
- [ ] **05_working_notes/** — zebrać pytania otwarte z całego projektu

### 📅 Harmonogram prac

| Tydzień | Cel |
|---|---|
| **2026-05-12 (pon)** | Ukończenie rozdziałów 01–05 (rdzeń przewodnika) |
| **2026-05-19 (pon)** | Ukończenie rozdziałów 06–09 + RACI + artefakty |
| **2026-05-26 (pon)** | Uzupełnienie standardów STD-001–008 |
| **2026-06-02 (pon)** | Uzupełnienie procedur PROC-001–006 + szablonów |
| **2026-06-09 (pon)** | Review + spójność + finalny draft v1.0 |

---

## Wskazówki dla przyszłych współtwórców

### Co pisać
- Treść merytoryczną pisz **po polsku**
- Zachowaj **strukturę sekcji** każdego rozdziału (cel → treść → praktyczne wskazówki DS)
- Każde wymaganie powinno być napisane jako **"co musi się wydarzyć"**, nie jako instrukcja krok po kroku
- Dla różnych typów modeli (regulacyjne / supervised / unsupervised) dodawaj **oznaczone bloki informacyjne**

### Oznaczenia typów modeli
Używaj następującego formatu dla specyficznych uwag:

```markdown
> ⚠️ **[REGULACYJNE]** Treść specyficzna dla modeli regulacyjnych.

> 📋 **[SUPERVISED]** Treść specyficzna dla modeli supervised.

> 🔬 **[UNSUPERVISED]** Treść specyficzna dla modeli unsupervised.
```

### Oznaczenia ważności
```markdown
> 🔴 **OBOWIĄZKOWE** — wymaganie bezwzględne, bez wyjątków
> 🟡 **ZALECANE** — best practice, z możliwością uzasadnionego odstępstwa
> 🟢 **OPCJONALNE** — przydatne, ale zależne od kontekstu
```

### Co nie należy do tego dokumentu
- Szczegółowe kroki techniczne (→ do procedur PROC-xxx)
- Szablony dokumentów (→ do szablonów TMPL-xxx)
- Szczegółowe wymagania metodyczne (→ do standardów STD-xxx)
- Implementacje kodu i narzędzia (→ do specialized_knowledge)

---

## Historia wersji

| Wersja | Data | Zmiana | Autor |
|---|---|---|---|
| 0.1 | 2026-05-09 | Inicjalna struktura repozytorium | Copilot |
| 0.5 | 2026-05-09 | Szkielety wszystkich sekcji, treść startowa | Copilot |
| 1.0 | TBD | Pełna treść merytoryczna, review | TBD |

---

*Wersja: 0.5 | Data: 2026-05-09*
