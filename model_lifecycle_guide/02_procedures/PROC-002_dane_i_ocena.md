# PROC-002: Procedura Oceny Danych

> **Typ dokumentu:** Procedura (Poziom 3)  
> **Status:** 🔄 Szkielet  
> **Powiązany etap:** Etap 3

---

## Cel procedury

Opisuje działania wymagane do oceny dostępności, jakości i adekwatności danych dla projektu modelarskiego.

---

## Krok 1: Identyfikacja źródeł danych

**Działania:**
- [ ] Zidentyfikuj potencjalne źródła danych (wewnętrzne i zewnętrzne)
- [ ] Określ zakres czasowy wymaganych danych
- [ ] Zidentyfikuj Data Ownerów dla każdego źródła
- [ ] Sprawdź wymagania dostępowe i procesu uzyskania danych

> 📋 **[SUPERVISED]** Zidentyfikuj gdzie będzie dostępna target variable (label) — nie zakładaj jej dostępności bez weryfikacji.

> 🔬 **[UNSUPERVISED]** Zidentyfikuj jakie cechy będą podstawą klasteryzacji — czy są dostępne z wymaganym zakresem historycznym?

---

## Krok 2: Ocena jakości danych

**Działania:**
- [ ] Przeprowadź wstępną EDA (Exploratory Data Analysis)
- [ ] Oceń kompletność danych (odsetek braków per zmienna)
- [ ] Oceń spójność danych w czasie
- [ ] Zidentyfikuj outliers i potencjalne błędy
- [ ] Oceń representatywność próbki

---

## Krok 3: Ocena wymogów privacy i zgód

**Działania:**
- [ ] Zidentyfikuj czy dane zawierają dane osobowe (RODO/GDPR scope)
- [ ] Sprawdź podstawę prawną przetwarzania danych
- [ ] Zaangażuj Compliance jeśli dane osobowe wrażliwe
- [ ] Udokumentuj wymagania pseudonimizacji/anonimizacji (jeśli dotyczy)

---

## Krok 4: Przygotowanie Data Assessment Report

**Działania:**
- [ ] Udokumentuj wyniki oceny danych
- [ ] Opisz ograniczenia i braki danych
- [ ] Przygotuj wstępny Data Dictionary
- [ ] Udokumentuj data lineage (skąd dane, jak przetworzone)
- [ ] Opisz plan obsługi brakujących danych i outlierów

---

## Krok 5: Zatwierdzenie przez Data Owner i MRM

**Działania:**
- [ ] Prześlij Data Assessment Report do Data Ownera i MRM
- [ ] Uzyskaj potwierdzenie adekwatności danych
- [ ] Udokumentuj zatwierdzenie (bramka BG-02)

---

## Bramka BG-02

> ✅ **Warunki zaliczenia bramki BG-02:**
> - [ ] Data Assessment Report kompletny
> - [ ] Data Owner potwierdził dostępność i jakość
> - [ ] Wymagania privacy spełnione lub plan spełnienia uzgodniony
> - [ ] MRM zaakceptował podejście do danych

---

## Powiązania

- [STD-001: Standard Rozwoju](../01_supporting_standards/STD-001_rozwoj_modeli.md)
- [Rozdział 5: Etap 3](../00_guide/05_etapy_cyklu_zycia.md#53-etap-3-dane-i-ocena)
