# 04 · Przegląd międzymodelowy: wzorzec i jego ograniczenia

[🇬🇧 English](../en/04-cross-model-review.md) · [↑ README](../../README.pl.md)

---

Przegląd międzymodelowy to mechanizm jakościowy uzupełniający dyscyplinę kosztów: skoro domyślnie korzystasz z tańszych modeli, potrzebujesz taniego sposobu na wykrywanie ich błędów — a najtańszym jest poproszenie *innego* modelu. Niniejszy dokument wyjaśnia ten wzorzec, a następnie poświęca równie dużo miejsca na obszary, w których **nie działa**, ponieważ technika, której ufasz ślepo, jest bardziej niebezpieczna niż taka, z której nie korzystasz.

## Wzorzec

> Postaw **2–3 niezależne modele** przed tym samym planem, decyzją lub różnicą (diff). Zachowaj tylko to, co przetrwa konfrontację.

Konkretnie:

1. **Wyprodukuj artefakt** — plan, decyzję architektoniczną, zmianę w kodzie.
2. **Prześlij go do dwóch niezależnych recenzentów** — domyślnie do dwóch *darmowych lokalnych* modeli o różnych charakterystykach (np. jeden nastawiony na rozumowanie, drugi zoptymalizowany pod kod). Dwie darmowe perspektywy nie kosztują nic poza odrobiną czasu.
3. **Czytaj niezgody, a nie zgody.** Tam, gdzie recenzenci się zgadzają, uczysz się niewiele. Tam, gdzie *konfliktują*, znajdujesz nośne założenia.
4. **Eskaluj tylko w przypadku prawdziwego impasu** — jeśli oba modele faktycznie konfliktują lub oba są niepewne, *wtedy* płatna trzecia opinia usprawiedliwia swój koszt (zob. [reguły eskalacji](./03-escalation-rules.md)).
5. **Zachowaj tylko to, co przetrwa.** Zgłoszenie, które podnosi jeden model, a artefakt nie jest w stanie obronić, to wniosek wymagający działania.

### Dlaczego niezależność ma znaczenie

Wartość płynie z tego, że recenzenci są *różni* — różny trening, różna charakterystyka, różne tryby błędów. Dwa uruchomienia tego samego modelu przy tych samych ustawieniach głównie zgadzają się same ze sobą; to potwierdzenie, a nie recenzja. Różnorodność recenzentów jest całym źródłem sygnału.

### Przydatny wariant: recenzja adwersarialna

Zamiast „przejrzyj to”, poproś recenzenta o *atak* na artefakt: „znajdź najsilniejszy argument, dla którego ten plan się nie sprawdzi”. Domyślnie nastaw recenzenta na obalenie tezy. O wiele trudniej planowi zawierającemu błędy przetrwać trzy niezależne próby jego obalenia niż trzy uprzejme „wygląda dobrze”. Gdy stawki tego wymagają, nadaj każdemu adwersarzowi inną perspektywę — poprawność, bezpieczeństwo, „czy to w ogóle się odtwarza” — aby atakowały artefakt na różne sposoby, a nie redundancyjnie.

## Ograniczenia — przeczytaj tę część dwa razy

Przegląd międzymodelowy to mechanizm **jakościowy**. Nie jest to mechanizm **bezpieczeństwa**, a traktowanie go jako takiego to poważny błąd. Trzy twarde ograniczenia:

### 1. Wspólne ślepe plamy

Modele trenowane na nakładających się danych mają wspólne ślepe plamy. Jeśli błąd jest powszechny w rozkładzie treningowym — popularny, ale błędny idiom, szeroko rozpowszechniony mit — *każdy* model może go powtarzać pewnie. Trzej recenzenci, którzy odziedziczyli tę samą ślepą plamę, przeoczą tę samą rzecz i nazwą to konsensusem. **Zgoda nie oznacza poprawności.** Może to być po prostu wspólna niewiedza.

### 2. Nie wykryje tego, czego nie widzi

Przegląd międzymodelowy czyta to, co mu pokażesz. Nie wykrywa on:

- **Sekretów / wyciekających poświadczeń** — model przeglądający Twój tekst nie będzie wiarygodnie oznaczał wyciekającego klucza, a nigdy nie powinieneś na nim polegać. To zadanie narzędzi deterministycznych (skanery sekretów), a nie osądu LLM.
- **Narażenia na dane wrażliwe** — czy „lekcja” deanonimizuje prawdziwą osobę, to pytanie ludzkie i polityczne, a nie coś, co rozstrzyga konsensus recenzji.

Jeśli potrzebujesz gwarancji, potrzebujesz **deterministycznej bramy** — skanera, wyrażenia regularnego, checklisty — a nie probabilistycznej opinii. Recenzja LLM jest co najwyżej miękkim drugim okiem *po przejściu twardych bram*, nigdy ich zamiennikiem.

### 3. Pewna błędność

Model może w przekonujący sposób obalić *poprawny* wniosek tak samo skutecznie, jak potwierdza błędny. Recenzja adwersarialna zmniejsza liczby fałszywie dodatnie, ale wprowadza liczby fałszywie ujemne: czasem plan był dobry, a zastrzeżenie adwersarza było błędne. Wynik recenzji to *dane wejściowe do Twojego osądu*, a nie werdykt go zastępujący.

## Uczciwe podsumowanie

Przegląd międzymodelowy jest doskonały w tym, w czym jest dobry: ujawnianiu założeń, łapaniu luk w rozumowaniu, tanim testowaniu planów pod kątem wytrzymałości przed ich zatwierdzeniem. Jest bezwartościowy — a nawet niebezpieczny — gdy żąda się od niego gwarancji właściwości bezpieczeństwa, których strukturalnie nie jest w stanie zapewnić. Używaj go do jakości. Używaj deterministycznych bram do bezpieczeństwa. Zachowuj wyraźną granicę między nimi.

Powód, dla którego niniejszy dokument poświęca tyle miejsca ograniczeniom, co wzorcowi, sam w sobie jest punktem: **metoda jest godna zaufania wprost proporcjonalnie do tego, jak jasno informuje Cię, gdzie się zawodzi.** Każdy, kto sprzedaje Ci przegląd międzymodelowy jako siatkę bezpieczeństwa, sprzedaje teatr.

## Gdzie iść dalej

- [Lekcje kosztowe](./05-cost-lessons.md) — powtarzające się błędy, w tym takie, których recenzja *nie* wykryłaby.
- [Reguły eskalacji](./03-escalation-rules.md) — kiedy trzecia opinia jest warta zapłacenia za nią.

---
