# STD-007: Standard Explainability Modeli

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet  
> **Powiązany rozdział przewodnika:** Etapy 5, 6, 7

---

## Cel standardu

Standard określa wymagania dotyczące interpretowalności i wyjaśnialności modeli, ze szczególnym uwzględnieniem obowiązków regulacyjnych i potrzeby wyjaśnienia decyzji klientom.

---

## 1. Wymagania Ogólne

> 🔴 **OBOWIĄZKOWE** — Każdy model Tier 1 i Tier 2 musi mieć przygotowaną dokumentację explainability.  
> Dla modeli podejmujących decyzje wobec klientów (scoring, credit decisioning) — wyjaśnialność jest koniecznością regulacyjną i prawną.

---

## 2. Poziomy Wyjaśnialności

| Poziom | Dla kogo | Co musi być wyjaśnione |
|---|---|---|
| **Globalna** | DS, Validator, MRM | Ogólne zachowanie modelu, feature importance |
| **Lokalna** | Model User, Compliance, Klient | Dlaczego konkretna decyzja dla konkretnej osoby |
| **Regulacyjna** | Nadzorca, Compliance | Zgodność z wymogami non-discrimination, fair lending |

---

## 3. Techniki Explainability

> ✍️ **[DO UZUPEŁNIENIA]** Opisać standardowe techniki stosowane w organizacji.

### Zalecane techniki

**Modele supervised:**
> 📋 **[SUPERVISED]**
> - **SHAP (SHapley Additive Explanations)** — zalecane jako standard dla explainability globalnej i lokalnej
> - **LIME** — jako uzupełnienie dla wyjaśnień lokalnych
> - **Feature Importance** (tree-based) — dla modeli drzewiastych
> - **Partial Dependence Plots (PDP)** — dla analizy wpływu zmiennych
> - **Individual Conditional Expectation (ICE)** — dla heterogenicznych efektów

**Modele unsupervised:**
> 🔬 **[UNSUPERVISED]**
> - **Profiling segmentów** — statystyki deskryptywne per klaster
> - **Feature importances dla separacji klastrów** — które cechy najlepiej różnicują segmenty?
> - **Radar charts / heatmaps** — wizualizacja profili segmentów dla biznesu
> - **Exemplar analysis** — reprezentatywne przykłady z każdego klastra

---

## 4. Obowiązki DS w zakresie Explainability

- [ ] Przygotować raport SHAP lub równorzędny przed walidacją
- [ ] Udokumentować top-N najważniejszych zmiennych i kierunek wpływu
- [ ] Przygotować interpretację zrozumiałą dla Model Ownera (nie tylko techniczną)
- [ ] Zidentyfikować potencjalne źródła bias lub fair lending issues

---

## 5. Specyfika per Typ Modelu

> ⚠️ **[REGULACYJNE]** Dla modeli regulacyjnych wymagania explainability wynikają z regulacji (np. RODO — prawo do wyjaśnienia automatycznej decyzji, EBA Guidelines). Explainability musi być uwzględniona w walidacji.

---

## Powiązania

- [STD-003: Standard Walidacji](./STD-003_walidacja.md)
- [Rozdział 2: Zasady Nadrzędne — Reproducibility](../00_guide/02_zasady_nadrzedne.md)
- [04_references/](../04_references/) — literatura o SHAP, LIME i fair lending
