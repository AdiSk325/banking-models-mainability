# Rozdział 8: Kontrole, Wyjątki i Eskalacja

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## 8.1 Kluczowe Kontrole w Procesie

<!-- PROMPT DLA AUTORA:
Opisz system kontroli w organizacji.
Jakie kontrole są zautomatyzowane, a jakie manualne?
Jak są dokumentowane wyniki kontroli?
-->

Następujące kontrole są wbudowane w process lifecycle modeli:

| Kontrola | Etap | Typ | Właściciel |
|----------|------|-----|-----------|
| Klasyfikacja Tier przez MRM | Inicjacja | Manualna | MRM |
| Data Owner sign-off na dane | Dane | Manualna | Data Owner |
| Code Review | Budowa | Manualna | DS Lead / Tech Lead |
| Internal QA | Testowanie | Manualna | DS Lead |
| Niezależna walidacja | Walidacja | Manualna | Walidator |
| Komitet akceptacji | Akceptacja | Manualna | Komitet |
| IT deployment checklist | Wdrożenie | Manualna | IT Lead |
| UAT | Wdrożenie | Manualna | Model Owner |
| Automatyczny monitoring | Monitoring | Automatyczna | MLOps / IT |
| Monitoring review (eskalacja) | Monitoring | Manualna | Model Owner |
| Change Request classification | Zmiana | Manualna | MRM |
| Retirement approval | Wycofanie | Manualna | Model Owner + MRM |

---

## 8.2 Zarządzanie Wyjątkami

<!-- PROMPT DLA AUTORA:
Opisz zasady zarządzania wyjątkami w organizacji.
Kto może udzielić wyjątku i dla którego wymagania?
Jak długo obowiązuje wyjątek?
Jak wyjątki są śledzone i raportowane?
-->

### Definicja Wyjątku

Wyjątek (exception) to formalne odstępstwo od wymagania określonego w tym przewodniku lub powiązanych standardach, zaakceptowane przez właściwy organ.

### Kiedy Wyjątek jest Dopuszczalny

Wyjątki mogą być udzielane jedynie gdy:
- Wypełnienie wymagania jest niemożliwe lub powoduje nieproporcjonalne koszty
- Zastosowane są kompensujące kontrole (compensating controls) ograniczające ryzyko
- Właściwy organ zaakceptował uzasadnienie i kontrole kompensujące

### Proces Udzielania Wyjątku

1. Model Owner / DS składa wniosek o wyjątek do MRM
2. MRM ocenia zasadność, ryzyko i adekwatność kontroli kompensujących
3. Właściwy organ akceptuje lub odrzuca wyjątek
4. Wyjątek jest rejestrowany w Exception Register
5. Wyjątek jest raportowany do Komitetu Akceptacji Modeli

### Ograniczenia Wyjątków

| Parametr | Wymaganie |
|----------|-----------|
| Maksymalny czas obowiązywania | [PLACEHOLDER: np. 12 miesięcy] |
| Zakres | Wyjątek dotyczy konkretnego modelu, nie generalizuje |
| Organ akceptujący (Tier 1) | [PLACEHOLDER: wyższy komitet] |
| Organ akceptujący (Tier 2/3) | [PLACEHOLDER: MRM] |
| Raportowanie | Do Komitetu co [PLACEHOLDER: kwartał] |

---

## 8.3 Procedury Eskalacji

### Eskalacja w Procesie Walidacji

| Sytuacja | Eskalacja do | Czas na eskalację |
|----------|-------------|-------------------|
| Finding klasy Critical nierozwiązany | Komitet Akceptacji Modeli | Natychmiastowa |
| Spór DS vs Validator co do findings | MRM jako arbitraż | 5 dni roboczych |
| Walidator odmawia sign-off | Komitet Akceptacji Modeli | 10 dni roboczych |

### Eskalacja w Monitoringu

| Trigger | Eskalacja do | Czas |
|---------|-------------|------|
| PSI > 0.25 lub inny próg krytyczny | MRM → Komitet | Natychmiastowa |
| PSI 0.1–0.25 | MRM | 5 dni roboczych |
| Brak raportu monitoringowego w terminie | MRM → Model Owner | +5 dni po terminie |
| Trwała degradacja performance | MRM ocenia potrzebę re-walidacji | 30 dni |

### Eskalacja Awaryjna

<!-- PROMPT DLA AUTORA:
Opisz procedurę awaryjną dla sytuacji kryzysowych z modelem produkcyjnym.
Np. błąd w modelu powodujący błędne decyzje klientowskie.
-->

W przypadku krytycznego błędu modelu produkcyjnego:
1. Natychmiastowe zawiadomienie Model Ownera i MRM
2. Decyzja o wstrzymaniu modelu vs. kontynuacji z nadzorem
3. Procedura awaryjna (Emergency Change Process)
4. Retroaktywna dokumentacja i post-mortem

---

## 8.4 Exception Register

<!-- PROMPT DLA AUTORA:
Opisz format i lokalizację Exception Register w organizacji.
Kto jest odpowiedzialny za prowadzenie rejestru?
-->

Exception Register jest prowadzony przez MRM i zawiera dla każdego wyjątku:
- Identyfikator wyjątku
- Model ID i opis
- Naruszone wymaganie
- Uzasadnienie wyjątku
- Kontrole kompensujące
- Organ akceptujący i data akceptacji
- Data ważności wyjątku
- Status (aktywny / zamknięty)

---

## 8.5 Raportowanie Governance

<!-- PROMPT DLA AUTORA:
Opisz schemat raportowania governance w organizacji.
Co jest raportowane do komitetu? Jak często? W jakiej formie?
-->

### Raportowanie do Komitetu Akceptacji Modeli

| Element | Częstotliwość |
|---------|--------------|
| Nowe modele do akceptacji | Ad-hoc (per spotkanie komitetu) |
| Status monitoringu portfolio modeli | [PLACEHOLDER: kwartalnie] |
| Exception Register — status | [PLACEHOLDER: kwartalnie] |
| Findings tracking — status remediation | [PLACEHOLDER: kwartalnie] |
| Model Inventory — zmiany | [PLACEHOLDER: kwartalnie] |

### Raportowanie do Zarządu / CRO

| Element | Częstotliwość |
|---------|--------------|
| Model Risk Dashboard | [PLACEHOLDER: kwartalnie] |
| Materialne incidents | Ad-hoc |
| Annual Review portfolio | Rocznie |

---

*Następny rozdział: [09_powiazane_dokumenty.md — Powiązane Standardy i Dokumenty](./09_powiazane_dokumenty.md)*
