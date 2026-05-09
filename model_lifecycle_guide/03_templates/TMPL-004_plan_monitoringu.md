# TMPL-004: Plan Monitoringu Modelu

> **Kiedy używać:** Przed wdrożeniem do produkcji (Etap 6–9)  
> **Kto wypełnia:** Data Scientist (z akceptacją Model Ownera)  
> **Cel:** Zdefiniowanie jak model będzie monitorowany po wdrożeniu

---

# Plan Monitoringu Modelu

**Tytuł modelu:** `[Pełna nazwa]`  
**ID modelu:** `[ID]`  
**Data planu:** `[RRRR-MM-DD]`  
**Odpowiedzialny DS:** `[Imię i nazwisko]`  
**Model Owner:** `[Imię i nazwisko]`  
**Data akceptacji:** `[RRRR-MM-DD]`  
**Podpis Model Ownera:** `____________________`

---

## 1. Zakres Monitoringu

**Monitoring obejmuje:**
- [ ] Performance modelu
- [ ] Stabilność populacji (PSI)
- [ ] Jakość danych wejściowych
- [ ] Inne: `[wymień]`

**Monitoring nie obejmuje:** `[Wymień wyłączenia z uzasadnieniem, jeśli dotyczy]`

---

## 2. Metryki Monitoringowe

### Metryki Performance

> 📋 **[SUPERVISED]**

| Metryka | Baseline (development) | Próg ostrzeżenia | Próg krytyczny |
|---|---|---|---|
| GINI | `[wartość]` | < `[wartość]` | < `[wartość]` |
| AUC | `[wartość]` | < `[wartość]` | < `[wartość]` |
| Bad rate | `[wartość]` | Odchylenie > `[X]%` | Odchylenie > `[Y]%` |

> 🔬 **[UNSUPERVISED]**

| Metryka | Baseline | Próg ostrzeżenia | Próg krytyczny |
|---|---|---|---|
| Cluster size stability | `[wartości baseline]` | Zmiana > `[X]%` | Zmiana > `[Y]%` |
| Feature distribution per cluster | Baseline distributions | Znaczący drift | Bardzo duży drift |

### Metryki Stabilności

| Metryka | Baseline | Próg ostrzeżenia | Próg krytyczny |
|---|---|---|---|
| PSI (ogólny) | — | > 0.10 | > 0.25 |
| Odsetek braków (kluczowe zmienne) | `[wartość]` | > `[X]%` | > `[Y]%` |

---

## 3. Częstotliwość i Harmonogram

**Tier modelu:** `[1 / 2 / 3]`

| Aktywność | Częstotliwość | Odpowiedzialny | Raport do |
|---|---|---|---|
| Obliczenie metryk | `[Miesięcznie/Kwartalnie/...]` | DS | Model Owner |
| Raport monitoringowy | `[Miesięcznie/Kwartalnie/...]` | DS | Model Owner + MRM |
| Periodic review | `[Rocznie/Co 2 lata]` | DS + Model Owner | MRM |

---

## 4. Trigger Events

Zdarzenia wymagające natychmiastowej analizy (poza harmonogramem):

| Trigger | Akcja | Odpowiedzialny |
|---|---|---|
| PSI > próg krytyczny | Analiza + escalacja do MRM | DS → Model Owner |
| Degradacja performance > X% | Analiza przyczyn + plan działania | DS → Model Owner |
| Błąd produkcyjny | Incident management | IT → DS → Model Owner |
| Zmiana regulacyjna dot. modelu | Ocena wpływu | MRM + DS |
| Roczna rocznica wdrożenia | Annual Review | DS + Model Owner |

---

## 5. Rollback Criteria

**Model powinien być wyłączony gdy:**
`[Zdefiniuj kiedy model jest za niebezpieczny do użycia — np. PSI > X i brak decyzji o fix w ciągu Y dni]`

---

## 6. Sposób Raportowania

**Format raportu:** `[Plik Markdown / Jupyter / Dashboard / Inne]`

**Lokalizacja raportów:** `[link/ścieżka]`

---

*Szablon v0.5 | Powiązany standard: STD-004 | Powiązana procedura: PROC-005*
