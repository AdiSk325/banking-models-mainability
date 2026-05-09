# Etap 5.7: Wdrożenie i Implementacja

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Akceptacja](./06_akceptacja_governance.md) | [Następny: Monitoring →](./08_monitoring_przeglad.md)

---

## Cel Etapu

Bezpieczne, kontrolowane wdrożenie zatwierdzonej wersji modelu do środowiska produkcyjnego. Celem jest zapewnienie, że model produkcyjny jest identyczny z modelem zatwierdzonym, a infrastruktura jest gotowa do jego obsługi.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **IT / MLOps Engineer** | Wdrożenie techniczne, konfiguracja infrastruktury |
| **Data Scientist** | Weryfikacja techniczna, wsparcie |
| **Model Owner** | Akceptacja UAT, finalna weryfikacja biznesowa |
| **IT Security** | Kontrola dostępu i bezpieczeństwa |
| **MRM** | Weryfikacja że wdrożona wersja = zatwierdzona wersja |

---

## Wymagania przed Wdrożeniem

<!-- PROMPT DLA AUTORA:
Opisz wymagania środowiskowe i techniczne przed wdrożeniem.
Jakie jest podejście do środowisk (dev/test/prod)?
Jak wygląda UAT?
-->

Przed wdrożeniem muszą być spełnione:

- [ ] Akceptacja komitetu (Gate 6) udzielona
- [ ] Środowisko produkcyjne przygotowane i zweryfikowane
- [ ] Test środowiskowy (SIT — System Integration Test) zakończony
- [ ] UAT (User Acceptance Test) przez Model Ownera / użytkowników zaliczony
- [ ] Rollback plan udokumentowany i przetestowany
- [ ] Access control skonfigurowany zgodnie z wymaganiami
- [ ] Monitoring pipeline skonfigurowany (metryki zdefiniowane w Monitoring Plan)
- [ ] IT deployment checklist podpisany

---

## Wymagania Techniczne dla Wdrożenia

### Wersjonowanie i odtwarzalność

- [ ] Wersja modelu (kod + parametry) zidentyfikowana jednoznacznie (tag lub hash)
- [ ] Model identyczny z wersją zaakceptowaną przez komitet — weryfikacja kryptograficzna lub równoważna
- [ ] Kod i konfiguracja zdeponowane w repozytorium przed wdrożeniem
- [ ] Środowisko wykonawcze udokumentowane (kontener lub specyfikacja)

### Segregacja środowisk

| Środowisko | Cel | Wymagania dostępu |
|-----------|-----|-------------------|
| Develop (DEV) | Budowa i eksperymenty | DS Team |
| Test (TEST/UAT) | Testy integracyjne, UAT | DS + IT + Model Owner |
| Production (PROD) | Wdrożenie produkcyjne | IT / MLOps (ograniczony) |

### Monitoring "od pierwszego dnia"

- [ ] Monitoring pipeline aktywny od momentu uruchomienia w produkcji
- [ ] Alerty skonfigurowane zgodnie z Monitoring Plan
- [ ] Dashboard dostępny dla Model Ownera

---

## Specyfika dla Modeli ML (Kategoria C/D)

<!-- PROMPT DLA AUTORA:
Opisz specyficzne wymagania MLOps dla modeli ML.
Jaką infrastrukturę stosuje organizacja (MLflow, Azure ML, custom)?
Jak wygląda model serving (batch vs real-time)?
-->

- Model zarejestrowany w Model Registry (MLflow lub równoważny)
- Wersja modelu oznaczona tagiem "production" w rejestrze
- Pipeline inferencing przetestowany na danych produkcyjnych (shadow mode jeśli możliwe)
- Feature store skonfigurowany (jeśli stosowany)
- Model serving architektura udokumentowana
- Latency i throughput zweryfikowane dla SLA

---

## Dokumentacja Wdrożenia (Deployment Evidence)

| Dokument | Opis | Wystawia |
|----------|------|---------|
| **Deployment Evidence** | Potwierdzenie wdrożenia: wersja, data, środowisko | IT / MLOps |
| **IT Deployment Checklist** | Podpisana checklista techniczna | IT Lead |
| **UAT Sign-off** | Akceptacja przez Model Ownera / użytkowników | Model Owner |
| **Rollback Plan** | Udokumentowany plan powrotu do poprzedniej wersji | IT |
| **Model Inventory Update** | Aktualizacja rejestru o datę wdrożenia, wersję | MRM |
| **Approval Record (Gate 7)** | IT / MLOps sign-off | IT Lead |

---

## Kryteria Wyjścia — Stage Gate 7

- [ ] Model wdrożony w produkcji — wersja zgodna z zatwierdzoną
- [ ] SIT i UAT zaliczone
- [ ] Monitoring aktywny
- [ ] Deployment Evidence kompletne
- [ ] IT / MLOps sign-off
- [ ] Model Inventory zaktualizowany (status: "Active / Production")

---

## Parallel Run (jeśli dotyczy)

Dla modeli Tier 1 zastępujących istniejący model zalecany jest Parallel Run — przez określony czas oba modele działają równolegle, wyniki są porównywane:

- Czas trwania Parallel Run: [PLACEHOLDER: np. 1–3 miesiące]
- Kryterium zakończenia: zgodność wyników w zdefiniowanym zakresie
- Decyzja o pełnym przejściu: Model Owner + MRM

---

*Szablony: [Deployment Checklist Template](../../templates/), [UAT Plan Template](../../templates/)*
