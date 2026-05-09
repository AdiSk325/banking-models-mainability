# Standard Dokumentacji Modeli

> **Poziom w hierarchii:** 2 — Standard  
> **Dokument nadrzędny:** [../guide/MODEL_LIFECYCLE_GUIDE.md](../guide/MODEL_LIFECYCLE_GUIDE.md)  
> **Wersja:** 0.1-draft  
> **Status:** Do opracowania

---

## Cel

Standard określa minimalne wymagania dotyczące dokumentacji modeli na wszystkich etapach lifecycle, formatu dokumentów i archiwizacji.

---

## 1. Model Development Document (MDD) — Wymagana Struktura

<!-- PROMPT DLA AUTORA:
Opisz obowiązkową strukturę MDD przyjętą w organizacji.
Jaka jest docelowa objętość (strony)? Jakie sekcje są obowiązkowe, jakie opcjonalne?
-->

### Sekcje obowiązkowe dla wszystkich Tierów

| Sekcja | Zawartość | Strony (szacunek) |
|--------|-----------|------------------|
| **1. Executive Summary** | Cel, metodologia (1 akapit), wyniki, ograniczenia | 1-2 |
| **2. Cel i zakres** | Cel biznesowy, populacja docelowa, ograniczenia zastosowania | 1-2 |
| **3. Dane** | Źródła, opis, ocena jakości, window | 3-5 |
| **4. Metodologia** | Uzasadnienie wyboru, opis algorytmu, feature engineering | 5-10 |
| **5. Wyniki i performance** | Metryki, testy, OOT | 3-5 |
| **6. Założenia i ograniczenia** | Kluczowe założenia, known limitations | 2-3 |
| **7. Plan monitoringu** | Metryki, progi, częstotliwość | 1-2 |
| **8. Wersja i historia** | Versioning, change log | 1 |

### Sekcje dodatkowe — Kategoria A (Regulacyjny)

| Sekcja | Zawartość |
|--------|-----------|
| Regulatory Mapping | Mapowanie do artykułów regulacyjnych |
| Margin of Conservatism | Uzasadnienie MoC jeśli stosowany |
| Próba treningowa | Szczegółowa analiza reprezentatywności |
| Stress testing | Wyniki testów stresowych |

### Sekcje dodatkowe — Kategoria C (Supervised ML)

| Sekcja | Zawartość |
|--------|-----------|
| Feature Engineering Pipeline | Pełny opis transformacji |
| SHAP Analysis | Globalna i lokalna wyjaśnialność |
| Bias & Fairness Assessment | Wyniki testów dyskryminacji |
| Model Card | Oddzielny dokument lub załącznik |

### Sekcje dodatkowe — Kategoria D (Unsupervised)

| Sekcja | Zawartość |
|--------|-----------|
| Kryteria wyboru algorytmu | Uzasadnienie metodologiczne |
| Ocena jakości klastrów | Metryki wewnętrzne i biznesowe |
| Profil segmentów | Opis każdego segmentu |

---

## 2. Model Card — Standard

<!-- PROMPT DLA AUTORA:
Opisz standard Model Card stosowany w organizacji.
Wzorowany na Google Model Cards (Mitchell et al., 2019).
Jakie sekcje są obowiązkowe?
-->

Model Card jest krótkim (1-2 strony) dokumentem opisującym model dla użytkowników i decydentów.

**Obowiązkowa zawartość Model Card (Kategoria C, D):**
- Nazwa modelu i wersja
- Cel / zadanie modelu
- Populacja docelowa i ograniczenia zastosowania
- Metryki performance (uproszczone)
- Dane treningowe (ogólny opis)
- Wyniki bias assessment
- Znane ograniczenia
- Sposób interpretacji wyników
- Właściciel i kontakt

---

## 3. Standardy Języka i Formatu

<!-- PROMPT DLA AUTORA:
Opisz wymagania formalne dotyczące języka i formatu dokumentów.
Jaki język: angielski, polski? Jakie narzędzia (Word, Markdown, Confluence)?
-->

| Element | Wymaganie |
|---------|-----------|
| Język dokumentacji | [PLACEHOLDER: polski / angielski / obydwa] |
| Format | [PLACEHOLDER: Word/PDF, Markdown, Confluence] |
| Nazewnictwo plików | [PLACEHOLDER: schemat nazewnictwa] |
| Szablony | Obowiązkowe — patrz [../templates/](../templates/) |

---

## 4. Wersjonowanie Dokumentów

<!-- PROMPT DLA AUTORA:
Opisz schemat wersjonowania dokumentów.
Jak śledzone są zmiany w dokumentacji?
-->

| Wersja | Zmiana | Wymagana aktualizacja |
|--------|--------|----------------------|
| Major (v1.0 → v2.0) | Materialna zmiana modelu | Obowiązkowa |
| Minor (v1.0 → v1.1) | Niematerialna zmiana / korekta | Obowiązkowa |
| Patch (v1.0.0 → v1.0.1) | Drobna korekta redakcyjna | Zalecana |

---

## 5. Archiwizacja Dokumentacji

<!-- PROMPT DLA AUTORA:
Opisz wymagania archiwizacyjne dla dokumentacji modeli.
Gdzie przechowywana jest dokumentacja? Jak długo?
Jak zapewniona jest dostępność historycznych wersji?
-->

| Dokument | Czas archiwizacji | Lokalizacja |
|----------|-------------------|-------------|
| MDD (wszystkie wersje) | [PLACEHOLDER] | [PLACEHOLDER] |
| Validation Reports | [PLACEHOLDER] | [PLACEHOLDER] |
| Approval Records | [PLACEHOLDER] | [PLACEHOLDER] |
| Monitoring Reports | [PLACEHOLDER] | [PLACEHOLDER] |

---

## Powiązane Dokumenty

- [Guide — Rozdział 7: Wymagane Artefakty](../guide/07_wymagane_artefakty.md)
- [MDD Template](../templates/)
- [Model Card Template](../templates/)
