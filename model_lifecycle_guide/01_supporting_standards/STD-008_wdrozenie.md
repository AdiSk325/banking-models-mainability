# STD-008: Standard Wdrożenia i MLOps

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet  
> **Powiązany rozdział przewodnika:** Etap 9

---

## Cel standardu

Standard określa wymagania techniczne dla wdrożenia modeli do produkcji, w tym wymagania MLOps, środowiskowe, bezpieczeństwa i kontroli.

---

## 1. Zasada Zgodności Wersji

> 🔴 **OBOWIĄZKOWE** — Model wdrożony do produkcji musi być identyczny z wersją zatwierdzoną przez governance.  
> Żadne modyfikacje kodu po zatwierdzeniu i przed wdrożeniem nie są dopuszczalne bez ponownego review.

---

## 2. Wymagania Środowiskowe

> ✍️ **[DO UZUPEŁNIENIA]** Opisać:
> - Wymagania dotyczące separacji środowisk (dev / staging / prod)
> - Wymagania dotyczące reprodukowalności środowiska (Docker, conda, requirements)
> - Politykę zarządzania sekretami i credentialami
> - Wymagania dostępności i SLA

---

## 3. Wymagania Przed Wdrożeniem

Przed każdym wdrożeniem do produkcji wymagane jest:
- [ ] Governance approval (BG-07)
- [ ] Testy UAT zakończone pozytywnie
- [ ] Performance test (latency, throughput) spełniony
- [ ] Security review (dla modeli przetwarzających dane osobowe)
- [ ] Rollback plan przygotowany i przetestowany
- [ ] Plan monitoringu zatwierdzony
- [ ] Dokumentacja operacyjna dla IT/MLOps gotowa
- [ ] Go-live checklist wypełniony

---

## 4. Wymagania Deployment Pipeline

> ✍️ **[DO UZUPEŁNIENIA]** Opisać:
> - CI/CD pipeline wymagania
> - Model registry
> - Deployment strategies (blue-green, canary, shadow)
> - Wersjonowanie modelu w produkcji

---

## 5. Wymagania Kontroli

| Kontrola | Opis | Obowiązkowe? |
|---|---|---|
| Version control | Kod w Git z tagiem wersji produkcyjnej | Tak |
| Access control | Dostęp do produkcji ograniczony rolami | Tak |
| Audit trail | Logi każdego wywołania modelu (sample) | Tak (Tier 1/2) |
| Rollback capability | Możliwość powrotu do poprzedniej wersji | Tak |
| Parallel run | Jednoczesne działanie starego i nowego modelu | Zalecane (Tier 1/2) |

---

## 6. Specyfika per Typ Modelu

> ⚠️ **[REGULACYJNE]** Dla modeli regulacyjnych: wdrożenie musi być spójne z wersją przedstawioną do zatwierdzenia/notyfikacji nadzorczej. Jakiekolwiek rozbieżności mogą być uznane za nieautoryzowaną zmianę.

> 📋 **[SUPERVISED]** Dla modeli scoring w czasie rzeczywistym — latency jest kluczowym parametrem. Wymaganie < [X ms] per scoring request musi być zdefiniowane i testowane.

> 🔬 **[UNSUPERVISED]** Dla modeli segmentacji — wdrożenie może być batch (nie real-time). Określ cykl aktualizacji segmentacji i proces komunikacji zmian segmentów do użytkowników.

---

## Powiązania

- [PROC-004: Procedura Wdrożenia](../02_procedures/PROC-004_wdrozenie.md)
- [Rozdział 5: Etap 9 — Wdrożenie](../00_guide/05_etapy_cyklu_zycia.md#59-etap-9-wdrożenie)
