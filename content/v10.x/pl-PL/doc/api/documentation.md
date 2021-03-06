# O dokumentacji

<!--introduced_in=v0.10.0-->

<!-- type=misc -->

Celem tej dokumentacji jest wyczerpujące wyjaśnienie Node.js API, zarówno z definicji jak i koncepcyjnego punktu widzenia. Each section describes a built-in module or high-level concept.

W razie potrzeby typy właściwości, argumenty metody i argumenty dostarczone do programów obsługujących zdarzenia, które są szczegółowo opisane na liście pod tematem nagłówek.

## Współtworzenie

Jeżeli znajdziesz błąd w tej dokumentacji, proszę [wyślij zgłoszenie](https://github.com/nodejs/node/issues/new) lub przeczytaj [instrukcję współtworzenia](https://github.com/nodejs/node/blob/master/CONTRIBUTING.md), która opisuje wskazówki oraz sposób dodawania poprawek.

Każdy plik jest generowany na podstawie odpowiadającego pliku `.md` w folderze `doc/api/` w drzewie źródłowym Node.js. Dokumentacja jest generowana przy użyciu programu `tools/doc/generate.js`. Szablon HTML znajduje się na `doc/template.html`.

## Stability Index

<!--type=misc-->

Throughout the documentation are indications of a section's stability. Interfejs API Node.js wciąż nieco się zmienia i w ten sposób dojrzewa, niektóre części są bardziej niezawodne niż inne. Niektóre są tak wypróbowane, że można polegać na tym, że prawdopodobnie wcale się nie zmienią. Inne są zupełnie nowe i eksperymentalne lub znane jako ryzykowne i w trakcie przeprojektowywania.

Wskaźniki stabilności są następujące:

```txt
Stabilność: 0 - Przestarzałe. Ta funkcja jest znana jako problematyczna i mogą być
planowane zmiany. Nie polegaj na niej. Użycie tej funkcji może spowodować pojawienie się
ostrzeżeń. Nie należy się spodziewać wstecznej kompatybilności z podstawowymi wersjami.
```

```txt
Stabilność: 1 - Eksperymentalne. Ta funkcja wciąż znajduje się w aktywnym rozwoju i
podlega zmianom, które nie są kompatybilne wstecznie, a nawet usunięte, w jakiejkolwiek przyszłej
wersji. Korzystanie z tej funkcji nie jest zalecane w środowiskach produkcyjnych.
Funkcje eksperymentalne nie podlegają modelowi Semantic Versioning Node.js.
```

```txt
Stabilność: 2 - Stabilne. API zostało zadowalająco sprawdzone. Kompatybilność z
Ekosystemem npm ma wysoki priorytet i nie zostanie złamana, chyba że to absolutnie
niezbędne.
```

Podczas korzystania z funkcji `Eksperymentalne` należy zachować ostrożność, w szczególności wewnątrz modułów, które mogą być używane jako zależności (lub zależności zależności) wewnątrz aplikacji Node.js. Końcowi odbiorcy mogą nie być tego świadomi, że używane są funkcje eksperymentalne, dlatego mogą wystąpić nieoczekiwane awarie lub zmiany zachowań po wystąpieniu modyfikacji interfejsu API. Aby tego uniknąć tego typu niespodzianki, funkcje `Eksperymentalne` mogą wymagać użycia wiersza polecenia flagi do jawnego ich uruchomienia, lub mogą powodować wyświetlenia ostrzeżenia o procesie. Domyślnie, takie ostrzeżenia są wywoływane jako [`stderr`][] i mogą być obsługiwane przez dołączanie odbiornika do zdarzenia [`'warning'`][].

## Dane wyjściowe JSON

<!-- YAML
added: v0.6.12
-->

> Stabilność: 1 - Eksperymentalne

Każdy dokument `.html` zawiera odpowiedni dokument `.json` przedstawiający te same informacje w uporządkowany sposób. This feature is experimental, and added for the benefit of IDEs and other utilities that wish to do programmatic things with the documentation.

## Funkcje systemowe i strony podręcznika systemowego

Funkcje systemowe, takie jak open(2) i read(2), definiują interfejs między programami użytkownika i bazowym systemem operacyjnym. Funkcje Node.js które po prostu zawijają funkcje systemowe jak [`fs.open()`][], będzie je dokumentował. Dokumenty prowadzą do odpowiedniej strony podręcznika, które opisują sposób działania funkcji systemowych.

Niektóre funkcje systemowe, takie jak Ichown(2), są specyficzne dla BSD. Oznacza to, na przykład, że [`fs.lchown()`][] działa tylko na MacOS i innych pochodnych systemów BSD i nie jest dostępny w systemie Linux.

Większość uniksowych funkcji systemowych ma odpowiedniki Windowsa, ale zachowanie może się różnić w Windowsie względem systemu Linux i macOS. Jednym z przykładów subtelnych sposobów, w jaki to jest czasami niemożliwe do zastąpienia semantyki systemu Unix w systemie Windows, patrz [Problem Node nr 4760](https://github.com/nodejs/node/issues/4760).