# Procedury — Poziom 3 Hierarchii Dokumentów

> **Poziom w hierarchii:** 3 — Procedury  
> **Dokument nadrzędny:** [../guide/MODEL_LIFECYCLE_GUIDE.md](../guide/MODEL_LIFECYCLE_GUIDE.md)  
> **Status:** Struktura zdefiniowana — treść do opracowania

---

## Czym Są Procedury?

Procedury opisują krok po kroku jak wykonać konkretne działania zdefiniowane w standardach i guide.

**Relacja do Guide i Standardów:**
- Guide mówi: *"Każdy model musi być zarejestrowany w Model Inventory"*
- Standard wyjaśnia: *"Co powinien zawierać wpis w Model Inventory"*
- Procedura wyjaśnia: *"Jak krok po kroku dodać model do systemu, jakie pola uzupełnić, kto zatwierdza"*

---

## Lista Procedur

| Procedura | Plik | Status | Priorytet |
|-----------|------|--------|-----------|
| Procedura Niezależnej Walidacji | [validation_procedure.md](./validation_procedure.md) | Do opracowania | 🔴 Wysoki |
| Procedura Rejestracji w Model Inventory | [model_inventory_procedure.md](./model_inventory_procedure.md) | Do opracowania | 🔴 Wysoki |
| Procedura Zarządzania Zmianą | [change_management_procedure.md](./change_management_procedure.md) | Do opracowania | 🔴 Wysoki |
| Procedura Wycofania Modelu | [model_retirement_procedure.md](./model_retirement_procedure.md) | Do opracowania | 🟡 Średni |
| Procedura Awaryjna (Emergency Change) | [emergency_procedure.md](./emergency_procedure.md) | Do opracowania | 🟡 Średni |
| Procedura Vendor Model Assessment | [vendor_model_procedure.md](./vendor_model_procedure.md) | Do opracowania | 🟢 Niski |
| Procedura Exception Management | [exception_procedure.md](./exception_procedure.md) | Do opracowania | 🟡 Średni |

---

## Przewodnik dla Autora Procedury

Każda procedura powinna zawierać:

1. **Cel** — co procedura opisuje
2. **Zakres** — kogo i czego dotyczy
3. **Role** — kto uczestniczy, kto jest responsible/accountable
4. **Wejścia** — co jest potrzebne do start procedury
5. **Kroki** — numerowana lista kroków z opisem
6. **Wyjścia** — co jest efektem procedury
7. **Czas realizacji** — oczekiwany czas per etap
8. **Eskalacja** — co robić jeśli coś nie działa
9. **Powiązane dokumenty** — formularze, szablony

---

## Przykładowa Struktura Procedury

```markdown
# Procedura: [Nazwa]

## Cel
...

## Zakres
...

## Kroki

### Krok 1: [Nazwa]
**Kto:** [Rola]
**Czas:** [X dni/godzin]
**Jak:**
1. ...
2. ...

**Wynik:** [Artefakt / decyzja]

### Krok 2: ...

## Eskalacja
...
```
