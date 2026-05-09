# STD-002: Standard Dokumentacji Modeli

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet  
> **Powiązany rozdział przewodnika:** Etap 6, Rozdział 7

---

## Cel standardu

Standard określa minimalną treść wymaganej dokumentacji dla każdego modelu oraz wymagania dotyczące jakości, wersjonowania i archiwizacji dokumentów.

---

## Minimalna Struktura Model Development Document (MDD)

> ✍️ **[DO UZUPEŁNIENIA]** Rozbudować każdą sekcję o szczegółowe wymagania treści.

### Obowiązkowe sekcje MDD

1. **Streszczenie wykonawcze**
   - Cel modelu
   - Zastosowanie i populacja
   - Metodologia (1 akapit)
   - Kluczowe wyniki performance
   - Znane ograniczenia i ryzyka

2. **Kontekst biznesowy i regulacyjny**
   - Problem biznesowy
   - Uzasadnienie modelarskie (dlaczego model?)
   - Powiązania regulacyjne (jeśli dotyczy)
   - Zastosowanie modelu (decyzje, procesy)

3. **Dokumentacja danych**
   - Źródła danych (z data lineage)
   - Zakres czasowy i populacyjny
   - Jakość danych i braki
   - Transformacje i preprocessing
   - Data dictionary (słownik zmiennych)

4. **Metodologia**
   - Wybrany algorytm i uzasadnienie
   - Alternatywy rozważone i odrzucone (z uzasadnieniem)
   - Inżynieria cech
   - Kalibracja

5. **Trening i selekcja modelu**
   - Procedura walidacji krzyżowej
   - Wyniki porównawcze algorytmów
   - Hiperparametry i tuning
   - Finalna konfiguracja

6. **Wyniki performance**
   - Metryki na zbiorze testowym
   - Backtesting / out-of-time
   - Subpopulation analysis
   - Porównanie z benchmarkiem

7. **Explainability i interpretacja**
   - Feature importance
   - SHAP values (lub inne)
   - Interpretacja dla użytkownika biznesowego

8. **Założenia i ograniczenia**
   - Lista założeń modelu
   - Znane ograniczenia
   - Warunki stosowania (kiedy model działa / nie działa)

9. **Plan monitoringu**
   - Metryki do monitorowania
   - Triggery dla review/recalibration
   - Częstotliwość monitoringu

10. **Historia zmian**
    - Wersja dokumentu
    - Data i opis zmian
    - Autor zmian

---

## Specyfika Dokumentacji per Typ Modelu

> ⚠️ **[REGULACYJNE]** Dodatkowe sekcje obowiązkowe:
> - Mapping wymagań regulacyjnych (jakie regulacje spełnia model)
> - Use test documentation
> - Stress testing results (jeśli dotyczy)

> 📋 **[SUPERVISED]** Dodatkowe sekcje zalecane:
> - Label definition document (jako aneks lub oddzielny dokument)
> - Data leakage assessment
> - Fairness/bias assessment (dla modeli decyzji klientowskich)

> 🔬 **[UNSUPERVISED]** Dodatkowe sekcje zalecane:
> - Cluster interpretation document (opis każdego segmentu)
> - Business validation sign-off (podpis eksperta domenowego)
> - Stability testing results

---

## Wymagania Jakości Dokumentacji

> ✍️ **[DO UZUPEŁNIENIA]** Opisać wymagania dotyczące:
> - Minimalnej szczegółowości (np. każde założenie musi być uzasadnione)
> - Języka i stylu
> - Wersjonowania dokumentu
> - Procesu review dokumentacji

---

## Powiązania

- [Rozdział 7: Wymagane Artefakty](../00_guide/07_wymagane_artefakty.md)
- [TMPL-002: Szablon MDD](../03_templates/TMPL-002_dokumentacja_modelu.md)
- [STD-003: Standard Walidacji](./STD-003_walidacja.md)
