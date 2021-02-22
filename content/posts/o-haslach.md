---
title: "O hasłach"
date: 2016-11-05T18:41:58+01:00
draft: false
category: pl
---

### tl:dr
![alt text][tldr]
###### Komiks pożyczony z xkcd.com


### Jednak nie jesteśmy kreatywni

Bez wątpienia tak jest, jeśli chodzi o wymyślanie haseł. Patrząc po statystykach z 2015 roku w czołówce najczęściej używanych haseł mamy tam takie perełki jak **123456**, **password**, **abc123** czy **1qaz2wsx**. Mogłoby się wydawać, że tego typu haseł używamy przy rejestracji do 1001 serwisu, do którego i tak już nigdy więcej nie zajrzymy, niestety prawda jest dużo bardziej przykra.
Skąd te dane? Pochodzą one z coraz to nowych wycieków, które dotykają często duże i wydawałoby się, przyzwoicie chronione serwisy. I mimo że hasła te nie są przechowywane w bazach danych jako "odkryty tekst" (ang. plain text), a w postaci haszy, to niepokojąco często używane są przestarzałe algorytmy haszujące, które nie zapewniają bezpieczeństwa. Lub też wykradzione hasła są tak słabe, że złamanie ich zajmuje chwile.

Wycieki te zdarzają się tak często, że w każdej chwili mogą dotknąć jeden z serwisów, których używasz!

Jeżeli Twoje hasło znajduje się w jakiejkolwiek statystyce haseł (wstydź się!), zawiera imię, tytuł filmu, datę urodzin, ... lub też jest krótsze niż 8 znaków to po przeczytaniu tego artykułu radzę jak najszybciej je zmienić!

Tylko na jakie? Odwołując się do powyższego komiksu - jesteśmy nauczeni, że im bardziej skomplikowane i pokręcone (a co za tym idzie trudne do zapamiętania) jest hasło tym jest ono lepsze. Czy aby na pewno tak jest?


### Typy ataków na hasła

Dwie podstawowe kategorie ataków na hasła to: **brute-force** oraz **atak słownikowy**. Stosowane są również pewne usprawnienia powyższych metod jak również ich kombinacje.

**Brute-force** polega na sprawdzaniu kombinacji znaków do momentu aż natrafimy na szukane hasło. A więc im większy jest zakres znaków jakie używamy w haśle oraz im dłuższe ono jest tym trudniej jest je złamać.

Dla przykładu, gdy nasze hasło składa się z 6 znaków i używamy w nim tylko małych liter, liczba kombinacji do sprawdzenia wynosi: 308 915 776 (zakładając 26 liter w alfabecie) - przy mocy obliczeniowej dzisiejszych komputerów, złamanie go zajmuje chwilę.

W przypadku użycia małych oraz wielkich liter mamy do dyspozycji 52 znaki (52^6 = 19 770 609 664). Dorzucając do tego parę znaków specjalnych (!@%-.,&*) oraz cyfry otrzymujemy około 70 znaków. Przy takiej liczbie znaków do wykorzystania nawet na szybkich komputerach czas łamania hasła o długości 8+ znaków niezwykle szybko się wydłuża.
Z powodu niskiej wydajności technika ta jest rzadko stosowana, można ją jednak wykorzystać do rozszerzenia metody słownikowej.

Do **metody słownikowej** wykorzystywane są listy najczęściej używanych haseł. Na takie listy składają się hasła z wyżej wspomnianych wycieków, najczęściej używane słowa w danym języku, imiona, tytuły filmów, nazwy zespołów itp.

Metoda ta zwykle jest rozszerzana o tzw. "zbiór reguł". Rozszerzenie to polega na modyfikacji każdego potencjalnego słowa w słowniku korzystając z wcześniej napisanych reguł.

Przykładami takich reguł są:

* Zamiana pierwszej litery na wielką (w przypadku, gdy jakaś strona wymaga użycia wielkich i małych liter prawie zawsze zamieniamy pierwszą literę na wielką)
* Naprzemienne użycie małych i wielkich liter (MoCnEhAsLo)
* Zamiana 'A' na @, 'E' na 3, 'S' na 5 itd. (a.k.a. [leet speak][leet_link])
* Dopisanie paru cyfr na koniec (XXX123, XXX1234)
* Dopisanie znaku specjalnego na koniec (XXX!, XXX$)

Pod [tym linkiem][rules_link] znajduje się więcej zasad używanych podczas łamania haseł.


### Wybór hasła

Jakie więc hasło wybrać?

Z charakterystyki pierwszego ataku wiemy, że musi ono mieć co najmniej 10 znaków, inaczej będzie je łatwo złamać metodą **brute-force**.

Aby zapewnić sobie ochronę przed **atakami słownikowymi** trzeba cóż... mieć pewność, że nasze hasło nie znajdzie w żadnym ze słowników (zakładamy również użycie "reguł").
W tym miejscu skorzystamy z definicji **entropii**. Jest to miara średniej ilości informacji. Im jest większa tym więcej informacji niesie ze sobą dana wiadomość. Im hasło ma większą entropię tym trudniej jest je zgadnąć korzystając z metody słownikowej.
Jak więc wybrać hasło, które niełatwo będzie "zgadnąć"? Logika podpowiada, że im bardziej nieprzewidywalne (losowe) ono będzie, tym lepiej!
Jednakże, gdy wybierzemy losowe znaki i wyjdzie nam np. *"P)fQtEd_7H&ny,4G"* nie będzie to łatwe do zapamiętania hasło.


### Diceware

Z pomocą przychodzi nam technika o nazwie **Diceware!**

Działa ona w następujący sposób. Bierzemy słownik, który zawiera przynajmniej 70'000 ponumerowanych słów. Następnie pięciokrotnie rzucamy kostką do gry i zapisujemy wylosowane liczby. Składamy je w jedną pięciocyfrową liczbę i zapisujemy słowo o otrzymanym numerze. Wybieramy tak minimum 6 słów (przy mocy obliczeniowej dzisiejszych komputerów próg sześciu słów jest uważany za bezpieczny).

Do użytku "domowego" można skorzystać z bezpiecznego generatora liczb (jednego z generatorów używanych w kryptografii) zamiast rzucać prawdziwą kostką.

Można również wykorzystać poniższy projekt, który wygeneruje hasło za nas techniką **diceware**.
[https://www.rempe.us/diceware/#polish][diceware_link]

Po wejściu na stronę klikamy w odpowiedni przycisk - w zależności ilu słów chcemy użyć. (cały proces generowania hasła odbywa się po stronie przeglądarki więc hasło widzimy tylko my)

![][diceware_screenshot]

Hasło wygenerowane za pomocą **diceware** dużo łatwiej jest zapamiętać (na przykład tworząc sobie jakąś historyjkę złożoną z tych słów) niż losowe 16 znaków.


### Teoria

Okej. Mamy już nasz hasło. Teraz pytanie, jak trudno je złamać?

Zacznijmy od ataku **brute-force**.
Porównajmy nasze hasło z dosyć bezpiecznym, ale trudnym do zapamiętania losowo wygenerowanym hasłem *"D%^9%Pq2v^M=8G"*.

Załóżmy, że mamy do dyspozycji 24 litery alfabetu (małe i wielkie), 10 cyfr oraz 10 znaków specjalnych. Na każdej z 14 pozycji może stać jeden z 68 znaków. Mamy więc 45198578652761699462938624 różnych możliwości.

W przypadku **diceware** obliczenia wyglądają nieco inaczej.
Mamy do wyboru jedno z 70 000 słów na każdą z 6 pozycji. W tym przypadku jest to 117649000000000000000000000000 możliwości.

Jak widać pomimo tego, że w naszym haśle używamy tylko małych liter to liczba możliwości przewyższa wcześniej wygenerowane 14-znakowe hasło.

Liczba kombinacji jest tak duża, że spokojnie możemy uznać nasz hasło za odporne na **brute-force**.


### Praktyka

Przetestujmy jak hasło wygenerowane przez **diceware** sprawdzi się wobec ataku słownikowego.

Wybierzmy najpierw kilka haseł podatnych na ataki słownikowe i policzmy z nich hasz (SHA-256):

1. haslo123 - *a15f8ae07675bfb96e084bfb4f52fb2c22091061aae86e0eb76a55f4e52dd74e*
2. PaSsWoRd - *8ca8e5726d7ebff4d521a6194e51223398c4d74329512504f8a4ea3a0dc73487*
3. nirvana12345 - *957cf452da2542857e3977ea2345c45ab57b0174a8ab3f8060616d4299e97c26*
4. harrypotter123 - *b079508661b8f93b1e32492e2ac619f2f60975704b1dbb993e171437aeaf51a4*

Policzmy też hasz z hasła wygenerowanego przez **diceware**:
"wycisk-chwyt-marka-czep-zimno-knajpa" - *8d6d1a0c5ae4d2c80cc04ee2a2ba1ca44a12768e5b9db7ac0d0366e36239a977*

Do ataku wykorzystamy darmowy i łatwy w obsłudze portal [Crackstation][crackstation_link]. (warto wspomnieć tutaj o bardziej zaawansowanym narzędziu jakim jest [hashcat][hashcat_link]) Wystarczy wkleić hasze, przepisać captchę i wcisnąć przycisk.

![][crackstation_cracked]

Po chwili strona wyrzuca nam wynik. Wszystkie 4 hasła udało się odzyskać z haszy bez żadnego problemu.

Hasła wygenerowanego przez **diceware** nie udało się jej jednak złamać:

![][crackstation_failed]


### Menadżery haseł

A co jeśli nasze hasło nie było przechowywane w formie haszu a w formie zwykłego tekstu? Nieważne wtedy jak silne było nasze hasło, w przypadku wycieku danych i tak wszyscy mają dostęp do jawnej postaci tego hasła.

Jak się przed tym zabezpieczyć? Korzystać z któregoś z **menadżerów haseł**. Mamy więc jedno mocne i łatwo do zapamiętania hasło, którym logujemy się do menadżera haseł. Następnie taki menadżer generuje nam losowe hasła (nie muszą być łatwe do zapamiętania, robi to za nas menadżer) oraz pilnuje abyśmy nie używali tego samego hasła w różnych serwisach.

W ten sposób, nawet jeśli nasze hasło wycieknie w czystej postaci z któregoś z serwisów to będzie to hasło używane tylko w tym serwisie i nie zagrozi to bezpieczeństwu innych naszych kont.

Od siebie polecę darmową usługę [LastPass][lastpass_link], gdyż jako jedyna posiada w swojej ofercie bezpłatną aplikację mobilną.


### Podsumowanie

W dobie coraz to częstszych ataków na serwisy internetowe, a co z tym idzie wycieków baz danych coraz większą rolę odgrywa siła hasła. Jeśli więc zależy Ci na bezpieczeństwie Twoich kont, rozważ zmianę haseł na nieco mocniejsze!





[tldr]: https://matishadow.files.wordpress.com/2016/07/password_strength.png
[diceware_screenshot]: https://matishadow.files.wordpress.com/2016/10/chrome_2016-10-12_19-38-25.png
[crackstation_cracked]: https://matishadow.files.wordpress.com/2016/11/chrome_2016-11-04_20-20-53.png
[crackstation_failed]: https://matishadow.files.wordpress.com/2016/11/chrome_2016-11-04_21-05-39.png

[leet_link]: https://en.wikipedia.org/wiki/Leet
[rules_link]: http://contest-2010.korelogic.com/rules.html
[diceware_link]: https://www.rempe.us/diceware/#polish
[crackstation_link]: https://crackstation.net/
[hashcat_link]: https://hashcat.net/hashcat/
[lastpass_link]: https://www.lastpass.com/