# 01 · Filozofia: darmowe domyślnie, płatne z konkretnego powodu

[🇬🇧 English](../en/01-philosophy.md) · [↑ README](../../README.pl.md)

---

## Zasada fundamentalna

> **Domyślnie wybieraj darmowe modele lokalne. Przechodź do płatnych interfejsów API tylko w przypadku istnienia konkretnego, mierzalnego powodu.**

To cała filozofia zawarta w jednym zdaniu. Wszystko inne w tym repozytorium to mechanizmy, które sprawiają, że to zdanie staje się operacyjne: jak decydować, co oznacza „konkretny powód”, jak kierować zadania i jak zachować uczciwość wobec siebie, rozróżniając *rzeczywistą potrzebę* drogiego modelu od jego *wygodnego sięgnięcia*.

## Dlaczego koszt jest pierwszoplanowym ograniczeniem projektowym

W konwencjonalnym oprogramowaniu optymalizuje się najpierw pod kątem poprawności, a kosztu — jeśli w ogóle — później; wywołanie funkcji jest efektywnie darmowe. Wnioskowanie AI (inference) łamie tę intuicję. Każde wywołanie modelu wiodącego (frontier) wiąże się z istotnym kosztem krańcowym, który waha się o **jeden do dwóch rzędów wielkości** w zależności od wybranej klasy modelu do tego samego zadania.

Gdy różnica kosztów między dwiema metodami wykonania tego samego zadania jest tak duża, koszt przestaje być postrzegany jako dodatek, a staje się **osią projektowania** — czymś, co decydujesz świadomie w momencie kierowania zadania, a nie czymś, co rozliczasz na miesięcznej fakturze. Traktowanie kosztu jako elementu pierwszoplanowego nie oznacza bycia skąpym. Oznacza wydawanie pieniędzy *z intencją*.

## Dlaczego „darmowe domyślnie” to domyślność, a nie kompromis

Instynkt sięgania po najbardziej zdolny model „dla pewności” opiera się na ukrytym założeniu: że najtrudniejszą częścią większości zadań jest sama zdolność modelu. W przypadku dużej codziennej pracy z AI nie jest to prawda.

Rozważ, co tak naprawdę zawiera typowy dzień praktycznego korzystania z AI: tłumaczenie wiadomości, streszczenie dokumentu, klasyfikacja danych wejściowych, wyodrębnianie danych strukturalnych, przygotowanie szablonów, przeglądanie niewielkich zmian w kodzie, odpowiadanie na pytanie faktograficzne, którego kształt już znasz. Żadne z tych zadań nie obciążają szczytowych możliwości modeli wiodących. Kompetentny model lokalny — działający na sprzęcie, który już posiadasz, przy zerowym koszcie krańcowym — radzi sobie z nimi z jakością **nierozróżnialną w rezultacie, który ma znaczenie**.

Zatem „darmowe domyślnie” nie jest opcją budżetową, na którą się godzisz. To *właściwa* opcja dla danej klasy zadań, a drogi model byłby tym, który musiałbyś *usprawiedliwić*. Ciężar dowodu spoczywa w odwrotnej kolejności niż w sposób, w jaki większość ludzi to konfiguruje.

### Pułapka „czuję się lepiej”

Najdroższym nawykiem w korzystaniu z AI nie jest poziom cenowy. To cicha wiara, że potężniejszy model daje lepszy wynik *nawet wtedy, gdy nie potrafisz wskazać, dlaczego*. To jedyny tryb awarii, przeciwko któremu istnieje cała ta metodologia.

Przydatny test pięciu sekund przed eskalacją:

> *„Czy to zadanie jest naprawdę trudne lub strategiczne — czy model premium jest po prostu bardziej komfortowy?”*

Jeśli nie potrafisz wskazać konkretnej rzeczy, którą tańszy model mógłby źle zrozumieć, płacisz za komfort, a nie za możliwości. Komfort jest realną potrzebą człowieka. Nie jest to powód do eskalacji.

## Kształt reguły

Filozofia sprowadza się do prostej, asymetrycznej domyślności:

- **Tani/lokalny to domyślna odpowiedź.** Nie wymaga usprawiedliwienia.
- **Drogi/płatny to wyjątek.** Wymaga podania powodu z krótkiej, jawnej listy (zob. [reguły eskalacji](./03-escalation-rules.md)).
- **W razie wątpliwości, wybieraj tańszy.** Wątpliwość nie jest powodem do eskalacji; jest powodem, by najpierw spróbować ścieżki taniej i *obserwować, czy faktycznie zawodzi*.

Ta asymetria to cała gra. Większość dyscypliny kosztowej sprowadza się po prostu do odmowy uznania frazy „może być lepiej” za wystarczający powód.

## Czym ta filozofia nie jest

- **Nie jest anty-frontier.** Modele wiodące są wyjątkowe i warte każdej ceny — w zadaniach, które ich wymagają. Chodzi o to, by *wydawać premię tam, gdzie przynosi ona wartość*, co wymaga znajomości miejsc, gdzie jej nie przynosi.
- **Nie chodzi o wyciskanie grosza.** Oszczędności wynikające z tej dyscypliny są realne, ale to efekt uboczny. Głębszą korzyścią jest *intencjonalność*: zawsze wiesz, dlaczego użyłeś danego modelu.
- **Nie jest stałą konfiguracją.** Twój sprzęt, mieszanka Twoich zadań i krajobraz modeli różnią się od czyichkolwiek innych i zmieniają się w czasie. To sposób *decydowania*, a nie ustawienie do skopiowania.

## Gdzie iść dalej

- [Mapa delegacji](./02-delegation-map.md) — przekształć tę filozofię w konkretną tabelę kierowania klasa zadania → klasa modelu.
- [Reguły eskalacji](./03-escalation-rules.md) — jawna lista powodów usprawiedliwiających płacenie.

---
