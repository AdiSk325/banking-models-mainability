# Standardy — Poziom 2 Hierarchii Dokumentów

> **Poziom w hierarchii:** 2 — Standardy  
> **Dokument nadrzędny:** [../guide/MODEL_LIFECYCLE_GUIDE.md](../guide/MODEL_LIFECYCLE_GUIDE.md)  
> **Status:** Struktura zdefiniowana — treść do opracowania

---

## Czym Są Standardy?

Standardy definiują szczegółowe wymagania metodologiczne i procesowe w konkretnych obszarach.

**Relacja do Guide:**
- Guide mówi: *"Każdy model musi przejść niezależną walidację"*
- Standard Walidacji wyjaśnia: *"Jak walidacja przebiega krok po kroku, jakie testy są obowiązkowe, jakie metryki muszą być osiągnięte"*

---

## Lista Standardów

| Standard | Plik | Status | Priorytet |
|----------|------|--------|-----------|
| Standard Developmentu Modeli | [development_standard.md](./development_standard.md) | Do opracowania | 🔴 Wysoki |
| Standard Dokumentacji Modeli | [documentation_standard.md](./documentation_standard.md) | Do opracowania | 🔴 Wysoki |
| Standard Walidacji Modeli | [validation_standard.md](./validation_standard.md) | Do opracowania | 🔴 Wysoki |
| Standard Monitoringu Modeli | [monitoring_standard.md](./monitoring_standard.md) | Do opracowania | 🔴 Wysoki |
| Standard Zarządzania Zmianą | [change_management_standard.md](./change_management_standard.md) | Do opracowania | 🟡 Średni |
| Standard MLOps / Wdrożeń | [mlops_standard.md](./mlops_standard.md) | Do opracowania | 🟡 Średni |
| Standard Explainability (AI/ML) | [explainability_standard.md](./explainability_standard.md) | Do opracowania | 🟡 Średni |
| Standard Jakości Danych | [data_quality_standard.md](./data_quality_standard.md) | Do opracowania | 🟡 Średni |
| Standard Fairness i Etyki AI | [fairness_standard.md](./fairness_standard.md) | Do opracowania | 🟢 Niski (na teraz) |

---

## Kolejność Opracowania (Priorytetyzacja)

**Faza 1 — Krytyczne (pierwsze do opracowania):**
1. Standard Dokumentacji Modeli — fundament wszystkich innych
2. Standard Walidacji Modeli — wymagany dla procesu walidacji
3. Standard Monitoringu Modeli — wymagany dla każdego modelu w produkcji
4. Standard Developmentu Modeli — wymagany dla Data Scientist

**Faza 2 — Ważne:**
5. Standard Zarządzania Zmianą — wymagany dla modeli w produkcji
6. Standard MLOps / Wdrożeń — wymagany dla IT/MLOps

**Faza 3 — Uzupełniające:**
7. Standard Explainability
8. Standard Jakości Danych
9. Standard Fairness

---

## Przewodnik dla Autora Standardu

Każdy standard powinien zawierać:

1. **Cel** — dlaczego ten standard istnieje
2. **Zakres** — których modeli / ról dotyczy
3. **Definicje** — kluczowe pojęcia
4. **Wymagania** — szczegółowe wymagania (co musi być spełnione)
5. **Metodologia** (jeśli dotyczy) — jak spełnić wymagania
6. **Metryki / Kryteria** — jak mierzyć zgodność
7. **Role i odpowiedzialności** — kto za co odpowiada
8. **Powiązane dokumenty** — guide, procedury, szablony
9. **Historia zmian** — versioning standardu
