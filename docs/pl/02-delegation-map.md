# 02 · Mapa delegacji: klasa zadania → klasa modelu

[🇬🇧 English](../en/02-delegation-map.md) · [↑ README](../../README.pl.md)

---

To jest operacyjne serce metodyki: mapowanie **klas zadań** na **klasy modeli**. Zostało ono celowo sformułowane w kategoriach klas, a nie nazw produktów. Konkretne modele zmieniają się co kilka miesięcy; *kształt* mapy pozostaje stabilny.

## Klasy modeli

Myśl w kategoriach czterech lub pięciu warstw, zdefiniowanych przez to, ile kosztują i co oferują unikalnie — a nie przez markę:

| Klasa | Koszt krańcowy | Cecha definiująca | Gdzie działa |
|-------|--|------|------------|
| **Local-small** | Zero | Szybki, wystarczający do większości rutynowych prac tekstowych | Twoja własna maszyna |
| **Local-large** | Zero | Większa zdolność wnioskowania, multimodalność, dłuższy (choć ograniczony) kontekst | Twoja własna maszyna, jeśli ma odpowiednią pamięć |
| **Paid-frontier** | Wysoki | Najlepsze wnioskowanie, agenty/użycie narzędzi, najtrudniejsze problemy | API hostowane |
| **Paid-long-context** | Średni–wysoki | Bardzo duże okno kontekstowe, którego modele lokalne nie są w stanie pomieścić | API hostowane |
| **Paid-grounded** | Średni | Dostęp do internetu na żywo / aktualne źródła | API hostowane |

Dwie klasy lokalne dzielą jedną decydującą cechę: **zerowy koszt krańcowy**. Gdy sprzęt zostanie zakupiony, ponowne uruchomienie modeli jest darmowe. Ta jedna okoliczność czyni możliwym podejście „domyślnie darmowe” — zakłada ono, że masz skonfigurowane modele lokalne. Jeśli ich nie masz, jest to pierwsza inwestycja, która szybko się zwraca.

## Mapa delegacji

Traktuj to jako „dla tego rodzaju pracy zacznij tutaj”. To punkt wyjścia, który dostosowujesz, a nie prawo niezmienne.

| Klasa zadania | Domyślna klasa modelu | Eskaluj tylko jeśli… |
|------|------|---------------|
| Codzienne tłumaczenie | Local | …jest to deliverable skierowany do klienta, gdzie jakość językowa jest krytyczna |
| Podsumowanie dokumentu mieszczącego się w lokalnym kontekście | Local | …dokument przekracza pojemność lokalnego kontekstu → paid-long-context |
| Klasyfikacja / ekstrakcja danych | Local | …rzadko; modele lokalne radzą sobie z tym dobrze |
| Tworzenie szablonów, wewnętrznych tekstów | Local | …jest to deliverable zewnętrzny o wysokim ryzyku |
| Izolowana poprawka błędu / refaktoryzacja pojedynczego pliku (jasny spec) | Local-large lub lokalny model do kodowania | …zmiana obejmuje wiele plików o głębokiej zależności |
| Testy dla istniejącej funkcji | Local | …rzadko |
| Przegląd planu, decyzji lub diffa | Local (×2 perspektywy) | …decyzja jest nieodwracalna/kosztowna → dodaj trzecią opinię z płatnego modelu |
| Wizja / OCR / opis obrazu | Local multimodal | …produkcyjna dokładność na trudnych danych wejściowych → najlepszy dostępny model multimodalny |
| Badania wymagające aktualnych, online’owych źródeł | **Paid-grounded** | To jest *możliwość*, której brakuje modelom lokalnym — nie eskalacja, lecz inne narzędzie |
| Podsumowywanie/praca nad bardzo dużym korpus | **Paid-long-context** | To jest *bariera* możliwości — lokalny kontekst nie jest w stanie tego pomieścić |
| Najtrudniejsze wnioskowanie, złożona, wieloetapowa praca agentowa | **Paid-frontier** | Gdy zadanie naprawdę przekracza zdolności wnioskowania modeli lokalnych |

Dwa wiersze zachowują się inaczej niż pozostałe. **Badania online** i **bardzo duży kontekst** nie są „eskalacjami” w sensie kosztowym — to zadania, których modele lokalne *nie są w stanie wykonać w ogóle*. Płacenie za nie nie jest porażką dyscypliny; to używanie właściwego narzędzia. Dyscyplina eskalacji dotyczy wierszy, w których tanie i drogie opcje *mogą wykonać zadanie*, a ty i tak skuszasz się na tę droższą.

## Dlaczego klasy wygrywają z nazwami

Trzy powody, dla których ta mapa nie wymienia modeli:

1. **Nazwy się starzeją.** Każda konkretna rekomendacja traci ważność w ciągu kilku cykli wydawniczych. Mapa oparta na klasach, którą uzupełniasz sam, pozostaje aktualna.
2. **Twój sprzęt jest inny.** To, co wchodzi w kategorię „local-large”, zależy od pamięci Twojej maszyny. Klasa jest przenośna; model, który ją wypełnia, należy do Ciebie.
3. **Zmusza do zadawania właściwych pytań.** „Jaką *klasę* wymaga to zadanie?” to pytanie, które generuje dyscyplinę kosztową. „Jaki model jest najlepszy?” to pytanie, które prowadzi do nadmiernych wydatków.

## Wypełnianie mapy dla siebie

Aby przekształcić to w swoją własną tabelę routingu:

1. **Wypisz swój mix zadań.** Czego faktycznie prosisz AI o wykonanie w typowym tygodniu?
2. **Przypisz każde zadanie do klasy**, domyślnie wybierając niższą. Bądź szczery co do tego, które zadania naprawdę wymagają mocy wnioskowania, a które tylko wydają się bezpieczniejsze na dużym modelu.
3. **Wybierz jeden model na klasę** spośród tego, co jest aktualne i dostępne — jeden local-small, jeden local-large, wybrane przez Ciebie opcje płatne.
4. **Zapisz to** i traktuj jako domyślne. Odchylenia powinny być świadome, zgodnie z [regułami eskalacji](./03-escalation-rules.md).

## Gdzie iść dalej

- [Reguły eskalacji](./03-escalation-rules.md) — wyraźne powody, które przesuwają zadanie wyżej w hierarchii.
- [Przegląd międzymodelowy](./04-cross-model-review.md) — wzorzec „×2 perspektywy” do przeglądania planów i kodu.

---
