# Zmiany do wdrożenia: report_data_tables_processing

Dokument zmian na podstawie wzorców z szablonu `copier-agentic-app`.

---

## Kontekst

Szablon `copier-agentic-app` to generyczny szablon dla dowolnych projektów agentowych przetwarzających dokumenty. Nie chodzi o kopiowanie konkretnych faz czy agentów, ale o **wzorce organizacyjne** które mogą ulepszyć obecny projekt.

---

## Wzorzec 1: GOAL.md - pojedyncze źródło prawdy dla celów

**Co**: Dedykowany plik z celami projektu, produktami końcowymi, odbiorcami i ograniczeniami.

**Dlaczego**: Cel projektu jest obecnie rozproszony między README.md i INSTRUCTIONS.md. Jeden plik ułatwia orientację.

**Akcja**: Utworzyć `/GOAL.md`

---

## Wzorzec 2: CHECKLIST.md - śledzenie postępu

**Co**: Plik w `/2-work-in-progress/` śledzący status zadań (pending/in-progress/completed).

**Dlaczego**:
- Umożliwia wznowienie przetwarzania po przerwaniu
- Daje widoczność postępu podczas długiego przetwarzania
- Działa jak tablica kanban dla agentów

**Akcja**: Dodać instrukcję generowania CHECKLIST.md do workflow i /process command

---

## Wzorzec 3: source-summaries.md - współdzielony kontekst

**Co**: Plik z podsumowaniami wszystkich źródeł tworzony na początku przetwarzania.

**Dlaczego**:
- Agenci mogą przeglądać kontekst bez ponownego czytania pełnych źródeł
- Zapewnia spójność terminologii między agentami
- Redukuje zużycie tokenów

**Akcja**: Dodać produkcję source-summaries.md do Kroku 1

---

## Wzorzec 4: Feedback do szablonu

**Co**: Obecny projekt ma ulepszenia które powinny wrócić do szablonu.

**Ulepszenia do backportu**:
- Persony agentów z PERSONA/STAKES/METODOLOGIA
- Artykuł wiedzy o metodologii (weryfikacja-wsteczna.md)
- terminologia.md jako wzorzec

**Akcja**: Zaktualizować copier-agentic-app o te wzorce

---

## Podsumowanie

| Wzorzec | Kierunek | Priorytet |
|---------|----------|-----------|
| GOAL.md | szablon → projekt | Wysoki |
| CHECKLIST.md | szablon → projekt | Wysoki |
| source-summaries.md | szablon → projekt | Średni |
| Persony agentów | projekt → szablon | - |
| Artykuły wiedzy | projekt → szablon | - |

---

## Instrukcje dla agenta

Implementuj wzorce 1-3 w kolejności priorytetu:

1. **GOAL.md** - skonsoliduj cele z README.md i INSTRUCTIONS.md do pojedynczego pliku w katalogu głównym
2. **CHECKLIST.md** - zaktualizuj workflow aby generował plik śledzenia postępu w `/2-work-in-progress/`
3. **source-summaries.md** - dodaj krok produkcji podsumowań źródeł do Kroku 1 przetwarzania

Wzorzec 4 (feedback do szablonu) wymaga osobnej sesji w projekcie `copier-agentic-app`.
