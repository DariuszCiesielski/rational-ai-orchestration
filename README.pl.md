# Racjonalna orkiestracja AI

> Rama decyzyjna do korzystania z wielu modeli AI **bez przepłacania** — darmowe modele lokalne jako domyślne, płatne API wyłącznie wtedy, gdy konkretny powód uzasadnia koszt, oraz wzajemna weryfikacja między modelami jako mechanizm jakości.

[🇬🇧 English](./README.md) · **🇵🇱 Polski**

---

## Problem

Większość ludzi płaci za AI w sposób, w jakim płaciłaby za prąd, gdyby każde światło w domu było podpięte pod osobny, mierzony i opłacany z osobna obwód: domyślnie, bez systemu, sięgając po najpotężniejszy (i najdroższy) model do każdego zadania — włącznie z trywialnymi.

To działa. To też jest marnotrawstwo. Duża część codziennej pracy z AI — tłumaczenie, streszczanie, klasyfikacja, tworzenie szkiców, przegląd kodu — działa doskonale na darmowych modelach lokalnych. Drogie modele frontier opłacają się w *mniejszości* zadań. Problemem rzadko jest brak możliwości. Problemem jest brak reguły określającej, **kiedy** droższa opcja jest rzeczywiście uzasadniona.

## Założenia

To repozytorium nie jest narzędziem ani produktem. To **metodologia** — sposób myślenia o koszcie AI jako o kluczowym ograniczeniu projektowym, utrwalony w formie, którą możesz dostosować do własnego środowiska:

- **Filozofia local-first** — dlaczego „darmowe domyślnie, płatne z powodu” to właściwy domyślny wybór, a nie kompromis.
- **Mapa delegacji** — która *klasa* zadań przypada do której *klasy* modeli.
- **Reguły eskalacji** — rama decyzyjna określająca, kiedy płacenie za interfejs API najnowocześniejszego modelu lub modelu z długim kontekstem jest rzeczywiście opłacalne (z przykładowymi progami, które dostosowujesz do własnego kontekstu).
- **Wzajemna weryfikacja między modelami** — jak i po co konfrontować 2–3 niezależne modele oraz — co równie ważne — **ograniczenia** tej techniki.
- **Lekcje kosztowe** — powtarzające się klasy drogich błędów oraz reguły, które im zapobiegają.

## Dla kogo to jest

Praktycy, którzy poważnie korzystają z modeli AI i szukają dla nich *systemu*: niezależni konsultanci, programiści, techniczni założyciele startupów, inżynierowie AI. Jeśli kiedykolwiek spojrzałeś na rachunek za API i pomyślałeś „większość z tego nie wymagała modelu premium” — to jest dla Ciebie.

To **nie** jest poradnik dla początkujących „Wprowadzenie do LLM”, ani **nie** jest marketingiem dostawców. Nie ma tu linków partnerskich ani rankingów „najlepszego modelu”. Nazwy modeli i ceny zmieniają się co miesiąc; zasady pozostają niezmienne. Ten dokument celowo mówi o *klasach* modeli i *względnym* koszcie, a nie o konkretnych produktach.

## Jak czytać

Zacznij od filozofii, a następnie przejdź do mapy delegacji. Pozostałe części można czytać w dowolnej kolejności.

| # | Dokument | Co Ci daje |
|---|---|---|
| 01 | [Filozofia](./docs/pl/01-philosophy.md) | Dlaczego koszt jest kluczowym ograniczeniem projektowym; zasada „darmowe domyślnie” |
| 02 | [Mapa delegacji](./docs/pl/02-delegation-map.md) | Mapowanie klasy zadania na klasę modelu |
| 03 | [Reguły eskalacji](./docs/pl/03-escalation-rules.md) | Rama decyzyjna: kiedy warto płacić za API |
| 04 | [Przegląd międzymodelowy](./docs/pl/04-cross-model-review.md) | Wzorzec konfrontacji 2–3 modeli — i jego granice |
| 05 | [Lekcje kosztowe](./docs/pl/05-cost-lessons.md) | Klasy drogich błędów i reguły zapobiegawcze |

## Uwaga dotycząca uczciwości

Dwie zasady przewijają się przez cały ten dokument:

1. **Względnie, nie bezwzględnie.** Brak cen, brak liczb tokenów, brak stwierdzeń „ten model jest najlepszy”. Te dane szybko się starzeją. Proporcje i reguły ogólne — zostają.
2. **Bez hype'u.** Tam, gdzie technika ma granice — a wzajemna weryfikacja modeli ma realne — ten dokument mówi o tym wprost. Metoda, której można zaufać, to taka, która jasno wskazuje, gdzie się zawodzi.

## Licencja

Dokumentacja w tym repozytorium jest udostępniona na licencji
[CC BY 4.0](./LICENSE) — udostępniaj i adaptuj z podaniem autorstwa.

## Autor

Autor: **Dariusz Ciesielski**. To osobista, robocza metodologia udostępniona otwarcie. Używaj jej, adaptuj, kwestionuj — i dostosuj każdą przykładową wartość do własnego kontekstu.

---
