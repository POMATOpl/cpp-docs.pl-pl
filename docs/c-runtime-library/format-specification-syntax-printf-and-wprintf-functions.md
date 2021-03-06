---
title: 'Składnia specyfikacji formatu: `printf` and `wprintf` Functions'
description: Opisuje składnię specyfikatora formatu dla środowiska uruchomieniowego `printf` i `wprintf` funkcji języka Microsoft C
ms.date: 10/26/2020
helpviewer_keywords:
- format specification fields for printf function
- printf function format specification fields
- flag directives, printf function
- type fields, printf function
- width fields, printf function
- precision fields, printf function
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
ms.openlocfilehash: 18642f650949e346fd3421b4a123acb4e84ed659
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907535"
---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>Składnia specyfikacji formatu: funkcje printf i wprintf

Różne `printf` i `wprintf` funkcje przyjmują ciąg formatu i opcjonalne argumenty i tworzą sformatowaną sekwencję znaków dla danych wyjściowych. Ciąg formatu zawiera zero lub więcej *dyrektyw* , które są znakami literału dla danych wyjściowych lub zakodowanych *specyfikacji konwersji* , które opisują sposób formatowania argumentu w danych wyjściowych. W tym artykule opisano składnię używaną do kodowania specyfikacji konwersji w ciągu formatu. Aby uzyskać listę tych funkcji, zobacz [przesyłanie strumieniowe we/wy](../c-runtime-library/stream-i-o.md).

Specyfikacja konwersji składa się z pól opcjonalnych i wymaganych w tej postaci:

**%** [ [*flagi*](#flags)] [ [*Szerokość*](#width)] [. [*precyzja*](#precision)] [ [*rozmiar*](#size)] [*Typ*](#type)

Każde pole specyfikacji konwersji jest znakiem lub cyfrą, która oznacza określoną opcję formatu lub specyfikator konwersji. Pole wymagany *Typ* określa rodzaj konwersji, która ma zostać zastosowana do argumentu. Opcjonalne *flagi* , *Szerokość* i *precyzja* kontrolują dodatkowe aspekty formatowania, takie jak spacje wiodące lub zera, uzasadnienie i wyświetlana dokładność. Pole *rozmiar* określa rozmiar zużytego i przekonwertowanego argumentu.

Podstawowa specyfikacja konwersji zawiera tylko znak procentu i *Typ* . Na przykład `%s` określa konwersję ciągu. Aby znak procentu był wyświetlany, należy użyć składni `%%`. Jeśli po znaku procentu następuje znak, który nie ma znaczenia jako pola formatu, zostanie wywołana procedura obsługi nieprawidłowego parametru. Aby uzyskać więcej informacji, zobacz [Walidacja parametrów](../c-runtime-library/parameter-validation.md).

> [!IMPORTANT]
> W celu zapewnienia bezpieczeństwa i stabilności upewnij się, że ciągi specyfikacji konwersji nie są zdefiniowane przez użytkownika. Rozważmy na przykład program, który monituje użytkownika o wprowadzenie nazwy, a dane wejściowe przechowuje w zmiennej o nazwie `user_name` będącej ciągiem tekstowym. W celu wyświetlenia wartości zmiennej `user_name` nie należy robić tak:
>
> `printf( user_name ); /* Danger!  If user_name contains "%s", program will crash */`
>
> Zamiast tego należy zrobić tak:
>
> `printf( "%s", user_name );`

<a name="type"></a>

> [!NOTE]
> W programie Visual Studio 2015 `printf` i `scanf` Rodzina funkcji zostały zadeklarowane jako **`inline`** i przenoszone do `<stdio.h>` `<conio.h>` nagłówków i. W przypadku migrowania starszego kodu w połączeniu z tymi funkcjami może być widoczny *LNK2019* . Aby uzyskać więcej informacji, zobacz [Visual C++ historię zmian 2003-2015](../porting/visual-cpp-change-history-2003-2015.md#stdio_and_conio).

## <a name="type-conversion-specifier"></a>Specyfikator konwersji typów

Znak specyfikatora konwersji *typu* określa, czy odpowiedni argument ma być interpretowany jako znak, ciąg, wskaźnik, liczba całkowita, czy liczba zmiennoprzecinkowa. Znak *typu* jest jedynym wymaganym polem specyfikacji konwersji i pojawia się po dowolnych opcjonalnych polach.

Argumenty występujące po ciągu formatu są interpretowane według odpowiedniego znaku *typu* i opcjonalnego prefiksu [rozmiaru](#size) . Konwersje dla typów znaków `char` i `wchar_t` są określone za pomocą znaków **`c`** lub **`C`** , oraz ciągów z pojedynczym bajtem lub szeroką literą, w zależności od tego, **`s`** **`S`** która funkcja formatowania jest używana. Argumenty znaków i ciągów, które są określone za pomocą **`c`** i **`s`** są interpretowane jako `char` i `char*` przez `printf` funkcje rodzinne lub jako `wchar_t` i `wchar_t*` przez `wprintf` funkcje rodzinne. Argumenty znaków i ciągów, które są określone za pomocą **`C`** i **`S`** są interpretowane jako `wchar_t` i `wchar_t*` przez `printf` funkcje rodzinne lub jako `char` i `char*` przez `wprintf` funkcje rodzinne. To zachowanie jest zależne od firmy Microsoft.

Typy całkowite, takie jak `short` , `int` ,, `long` `long long` i ich `unsigned` warianty, są określane przy użyciu **`d`** , **`i`** ,,, **`o`** **`u`** **`x`** i **`X`** . Typy zmiennoprzecinkowe, takie jak `float` , `double` , i **`long double`** , są określane przy użyciu **`a`** , **`A`** , **`e`** ,, **`E`** ,, **`f`** **`F`** **`g`** i **`G`** . Domyślnie, chyba że są modyfikowane przez prefiks *rozmiaru* , argumenty całkowite są przekształcane na `int` Typ, a argumenty zmiennoprzecinkowe są przekształcane na `double` . W systemach 64-bitowych `int` jest wartością 32-bitową, dlatego 64-bitowe liczby całkowite będą obcinane, gdy są formatowane do danych wyjściowych, chyba że jest używany **ll** prefiks *size* **I64** . Typy wskaźników, które są określone przy **`p`** użyciu domyślnego rozmiaru wskaźnika dla platformy.

> [!NOTE]
> **Specyficzne dla firmy Microsoft:**\
> **`Z`** Typ znaku oraz zachowanie **`c`** **`C`** znaków,, i, gdy są **`s`** **`S`** używane razem z `printf` `wprintf` funkcjami i są rozszerzeniami firmy Microsoft. Standard ISO C używa **`c`** i **`s`** konsekwentnie w przypadku wąskich znaków i ciągów **`C`** oraz **`S`** dla szerokich znaków i ciągów, we wszystkich funkcjach formatowania.

### <a name="type-field-characters"></a>Znaki pola typu

|Znak typu|Argument|Format danych wyjściowych|
|--------------------|--------------|-------------------|
|**`c`**|Znak|Gdy jest używany z `printf` funkcjami, określa znak jednobajtowy; gdy jest używany z `wprintf` funkcjami, określa szeroki znak.|
|**`C`**|Znak|Gdy jest używany z `printf` funkcjami, określa znak `wprintf` dwubajtowy; gdy jest używany z funkcjami, określa znak pojedynczy.|
|**`d`**|Liczba całkowita|Cyfra dziesiętna ze znakiem.|
|**`i`**|Liczba całkowita|Cyfra dziesiętna ze znakiem.|
|**`o`**|Liczba całkowita|Liczba całkowita bez znaku.|
|**`u`**|Liczba całkowita|Liczba całkowita dziesiętna bez znaku.|
|**`x`**|Liczba całkowita|Szesnastkowa liczba całkowita bez znaku; używa " `abcdef` ".|
|**`X`**|Liczba całkowita|Szesnastkowa liczba całkowita bez znaku; używa " `ABCDEF` ".|
|**`e`**|Liczba zmiennoprzecinkowa|Podpisana wartość, która ma postać [-] *`d.dddd`* __e ±__ *`dd`* \[ *`d`* ], gdzie *`d`* jest jedną cyfrą dziesiętną, *`dddd`* jest co najmniej jedną cyfrą dziesiętną, w zależności od określonej precyzji lub sześć domyślnie, i *`dd`* \[ *`d`* ] ma dwie lub trzy cyfry dziesiętne, w zależności od [formatu danych wyjściowych](../c-runtime-library/set-output-format.md) i rozmiaru wykładnika.|
|**`E`**|Liczba zmiennoprzecinkowa|Identyczny z **`e`** formatem, z wyjątkiem tego, że **`E`** nie **`e`** wprowadza wykładnika.|
|**`f`**|Liczba zmiennoprzecinkowa|Podpisana wartość, która ma postać [-] *`dddd`* __.__ *`dddd`* , gdzie *`dddd`* jest co najmniej jedną cyfrą dziesiętną. Liczba cyfr przed punktem dziesiętnym zależy od wielkości liczby, a liczba cyfr po przecinku jest zależna od wymaganej precyzji lub sześciu domyślnie.|
|**`F`**|Liczba zmiennoprzecinkowa|Identyczny z **`f`** formatem, z wyjątkiem tego, że nieskończoność i Nan dane wyjściowe są pisane wielkimi literami.|
|**`g`**|Liczba zmiennoprzecinkowa|Wartości podpisane są wyświetlane w **`f`** **`e`** formacie lub, w zależności od tego, który jest bardziej zwarty dla danej wartości i dokładności. **`e`** Format jest używany tylko wtedy, gdy wykładnik wartości jest mniejszy niż-4 lub większy lub równy argumentowi *precyzji* . Końcowe zera są obcinane, a punkt dziesiętny pojawia się tylko wtedy, gdy jedna lub więcej cyfr należy do niego.|
|**`G`**|Liczba zmiennoprzecinkowa|Identyczny z **`g`** formatem, z tą różnicą, że **`E`** zamiast **`e`** , wprowadza wykładnik (tam, gdzie to konieczne).|
|**`a`**|Liczba zmiennoprzecinkowa|Podpisana szesnastkowa wartość zmiennoprzecinkowa o podwójnej precyzji, która ma postać *[-] 0xh. hhhh*__p ±__ *`dd`* , gdzie *h. hhhh* to cyfry szesnastkowe (przy użyciu małych liter) mantysy i *`dd`* są jedną lub większą cyfrą wykładnika. Precyzja określa liczbę cyfr po punkcie.|
|**`A`**|Liczba zmiennoprzecinkowa|Podpisana szesnastkowa wartość zmiennoprzecinkowa o podwójnej precyzji, która ma postać *[-] 0Xh. hhhh*__P ±__ *`dd`* , gdzie *h. hhhh* to cyfry szesnastkowe (przy użyciu wielkich liter) mantysy, a *DD* to jedna lub więcej cyfr dla wykładnika. Precyzja określa liczbę cyfr po punkcie.|
|**`n`**|Wskaźnik na liczbę całkowitą|Liczba znaków, które zostały pomyślnie wpisane do strumienia lub buforu. Ta wartość jest przechowywana w postaci liczby całkowitej, której adres jest podawany jako argument. Rozmiar liczby całkowitej wskazywanej w można kontrolować przy użyciu prefiksu specyfikacji rozmiaru argumentu. **`n`** Specyfikator jest domyślnie wyłączony. Aby uzyskać więcej informacji, zobacz ważne uwagi dotyczące zabezpieczeń.|
|**`p`**|Typ wskaźnika|Wyświetlaj argument jako adres w cyfrach szesnastkowych.|
|**`s`**|String|Gdy jest używany z `printf` funkcjami, określa dwubajtowy lub wielobajtowy ciąg znaków; gdy jest używany z `wprintf` funkcjami, określa ciąg znaków szerokich. Znaki są wyświetlane do pierwszego znaku null lub do czasu osiągnięcia wartości *precyzji* .|
|**`S`**|String|Gdy jest używany z `printf` funkcjami, określa ciąg znaków dwubajtowych; gdy jest używany z `wprintf` funkcjami, określa ciąg znaków o pojedynczym bajcie lub wielobajtowym. Znaki są wyświetlane do pierwszego znaku null lub do czasu osiągnięcia wartości *precyzji* .|
|**`Z`**|`ANSI_STRING` lub `UNICODE_STRING` Struktura|Gdy [`ANSI_STRING`](/windows/win32/api/ntdef/ns-ntdef-string) [`UNICODE_STRING`](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) jako argument jest przekazanie adresu lub struktury, Wyświetl ciąg zawarty w buforze wskazywanym przez `Buffer` pole struktury. Użyj prefiksu modyfikatora *rozmiaru* , **`w`** Aby określić `UNICODE_STRING` argument — na przykład `%wZ` . `Length`W polu struktury musi być ustawiona Długość (w bajtach) ciągu. `MaximumLength`W polu struktury musi być ustawiona Długość (w bajtach) buforu.<br /><br />Zazwyczaj **`Z`** znak typu jest używany tylko w funkcjach debugowania sterowników, które używają specyfikacji konwersji, takich jak `dbgPrint` i `kdPrint` .|

Począwszy od programu Visual Studio 2015, jeśli argument, który odpowiada specyfikatorowi konwersji zmiennoprzecinkowej (,,,,,, **`a`** **`A`** **`e`** **`E`** **`f`** **`F`** **`g`** **`G`** ) jest nieskończony, nieokreślony lub NaN, sformatowane dane wyjściowe są zgodne ze standardem C99. W tej tabeli wymieniono sformatowane dane wyjściowe:

|Wartość|Dane wyjściowe|
|-----------|------------|
|nieskończoność|`inf`|
|Cichy NaN|`nan`|
|Sygnalizowanie NaN|`nan(snan)`|
|Nieokreślony NaN|`nan(ind)`|

Wszystkie te wartości mogą być poprzedzone znakiem. Jeśli znak specyfikatora konwersji *typu* zmiennoprzecinkowego jest wielką literą, dane wyjściowe są również formatowane wielkimi literami. Na przykład jeśli specyfikator formatu jest `%F` zamiast `%f` , nieskończoność jest formatowana jako `INF` zamiast `inf` . `scanf`Funkcje te mogą również analizować te ciągi, dzięki czemu te wartości mogą przekonywać rundy `printf` i `scanf` funkcje.

Przed uruchomieniem programu Visual Studio 2015 CRT użył innego niestandardowego formatu dla danych wyjściowych nieskończonych, nieokreślonych i NaN:

|Wartość|Dane wyjściowe|
|-----------|------------|
|+ nieskończoność|`1.#INF`*cyfry losowe*|
|-nieskończoność|`-1.#INF`*cyfry losowe*|
|Nieokreślony (taki sam jak cichy NaN)|*cyfra* `.#IND` *cyfry losowe*|
|NaN|*cyfra* `.#NAN` *cyfry losowe*|

Dowolne z tych elementów mogło zostać poprzedzone znakiem i być sformatowane w różny sposób w zależności od szerokości pola i precyzji, czasami z nietypowymi skutkami. Na przykład `printf("%.2f\n", INFINITY)` drukuje, `1.#J` ponieważ *#INF* będzie "zaokrąglona" do dwóch cyfr precyzji.

> [!NOTE]
> Jeśli argument, który odnosi się do `%s` lub `%S` lub `Buffer` pola argumentu, który odpowiada `%Z` , jest wskaźnikiem typu null, zostanie wyświetlony komunikat "(null)".

> [!NOTE]
> We wszystkich formatach wykładniczych minimalna liczba cyfr do wyświetlenia jest równa 2, przy użyciu trzech tylko w razie potrzeby. Korzystając z [`_set_output_format`](../c-runtime-library/set-output-format.md) funkcji, można ustawić liczbę wyświetlanych cyfr na trzy w celu zapewnienia zgodności z kodem zapisanym dla Visual Studio 2013 i przed.

> [!IMPORTANT]
> Ponieważ `%n` Format jest z natury niezabezpieczony, jest domyślnie wyłączony. Jeśli `%n` wystąpi w ciągu formatu, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../c-runtime-library/parameter-validation.md). Aby włączyć `%n` obsługę, zobacz [`_set_printf_count_output`](../c-runtime-library/reference/set-printf-count-output.md) .

<a name="flags"></a>

## <a name="flag-directives"></a>Dyrektywy flag

Pierwsze opcjonalne pole w specyfikacji konwersji zawiera *dyrektywy flag* , zero lub więcej znaków flagi, które określają Justowanie danych wyjściowych i kontrolowanie danych wyjściowych znaków, pustych, wiodących zer, punktów dziesiętnych i szesnastkowych prefiksów. W specyfikacji konwersji może pojawić się więcej niż jedna dyrektywa flag, a znaki flagi mogą pojawiać się w dowolnej kolejności.

### <a name="flag-characters"></a>Znaki flagi

|Flaga|Znaczenie|Domyślne|
|----------|-------------|-------------|
|**`-`**|Wyrównaj wynik z lewej strony do pola.|Wyrównaj do prawej.|
|**`+`**|Użyj znaku (+ lub-), aby utworzyć prefiks wartości wyjściowej, jeśli jest ona typu ze znakiem.|Znak jest wyświetlany tylko w przypadku ujemnych wartości podpisanych (-).|
|**`0`**|Jeśli *Szerokość* jest poprzedzona znakiem **`0`** , zera wiodące są dodawane do momentu osiągnięcia minimalnej szerokości. Jeśli oba **`0`** i **`-`** pojawiają się, **`0`** jest ignorowany. Jeśli **`0`** jest określony dla formatu liczb całkowitych ( **`i`** ,,,, **`u`** **`x`** **`X`** **`o`** , **`d`** ) i specyfikacji precyzji, na przykład `%04.d` — **`0`** jest ignorowany. Jeśli **`0`** jest określony dla **`a`** formatu lub **`A`** zmiennoprzecinkowego, zera wiodące są poprzedzone mantysy po `0x` `0X` prefiksie lub.|Brak dopełnienia.|
|**puste (' ')**|Użyj pustej wartości, aby prefiksować wartość wyjściową, jeśli jest ona podpisana i dodatnia. Wartość pusta jest ignorowana, jeśli są wyświetlane flagi puste i +.|Nie pojawia się żadne puste.|
|**`#`**|Gdy jest używany z **`o`** , **`x`** , lub w **`X`** formacie, **`#`** Flaga używa `0` `0x` odpowiednio,, lub `0X` , aby prefiksować dowolną wartość wyjściową różną od zera.|Nie pojawia się żadne puste.|
||Gdy jest używany z **`e`** , **`E`** ,,,, lub w **`f`** **`F`** **`a`** **`A`** formacie, **`#`** flaga wymusza wartość wyjściową, aby zawierała separator dziesiętny.|Punkt dziesiętny jest wyświetlany tylko wtedy, gdy cyfry są zgodne.|
||Gdy jest używany z **`g`** **`G`** formatem lub, **`#`** flaga wymusza wartość wyjściową, aby zawierała przecinek dziesiętny i uniemożliwia obcinanie końcowych zer.<br /><br /> Ignorowane, gdy jest używany z **`c`** , **`d`** , **`i`** ,, **`u`** lub **`s`** .|Punkt dziesiętny jest wyświetlany tylko wtedy, gdy cyfry są zgodne. Końcowe zera są obcinane.|

<a name="width"></a>

## <a name="width-specification"></a>Specyfikacja szerokości

W specyfikacji konwersji pole opcjonalnej specyfikacji szerokości pojawia się po każdym z *flag* znaków. Argument *Width* jest nieujemną liczbą całkowitą dziesiętną, która określa minimalną liczbę znaków, które są wyprowadzane. Jeśli liczba znaków w wartości wyjściowej jest mniejsza niż określona szerokość, puste wartości są dodawane do lewej lub prawej strony z wartościami — w zależności od tego, czy jest określona flaga wyrównania w lewo ( **`-`** ), aż do osiągnięcia minimalnej szerokości. Jeśli *Szerokość* jest poprzedzona przez 0, zera wiodące są dodawane do liczby całkowitej lub konwersji zmiennoprzecinkowej do momentu osiągnięcia minimalnej szerokości, z wyjątkiem sytuacji, gdy konwersja jest nieskończona lub NaN.

Specyfikacja szerokości nigdy nie powoduje obcięcia wartości. Jeśli liczba znaków w wartości wyjściowej jest większa niż określona szerokość lub jeśli nie podano *szerokości* , wszystkie znaki wartości są wyprowadzane zgodnie ze specyfikacją *precyzji* .

Jeśli Specyfikacja szerokości jest gwiazdką ( `*` ), `int` argument z listy argumentów dostarcza wartość. Argument *Width* musi poprzedzać wartość, która jest formatowana na liście argumentów, jak pokazano w poniższym przykładzie:

`printf("%0*d", 5, 3);  /* 00003 is output */`

Brakująca lub niewielka wartość *szerokości* w specyfikacji konwersji nie powoduje obcięcia wartości wyjściowej. Jeśli wynik konwersji jest szerszy niż wartość *szerokości* , pole zostanie rozwinięte, aby zawierało wynik konwersji.

<a name="precision"></a>

## <a name="precision-specification"></a>Specyfikacja dokładności

W specyfikacji konwersji trzecie pole opcjonalne jest specyfikacją precyzji. Składa się z kropki ( `.` ), po której następuje nieujemna liczba całkowita dziesiętna, która w zależności od typu konwersji określa liczbę znaków ciągu, liczbę miejsc dziesiętnych lub liczbę cyfr znaczących, które mają być wyprowadzane.

W przeciwieństwie do specyfikacji szerokości, Specyfikacja dokładności może spowodować Obcinanie wartości wyjściowej lub zaokrąglenie wartości zmiennoprzecinkowej. Jeśli *precyzja* jest określona jako 0, a wartość do przekonwertowania to 0, wynik nie ma znaków wyjściowych, jak pokazano w tym przykładzie:

`printf( "%.0d", 0 );      /* No characters output */`

Jeśli Specyfikacja dokładności jest gwiazdką ( `*` ), `int` argument z listy argumentów dostarcza wartość. Na liście argumentów argument *dokładności* musi poprzedzać wartość, która jest formatowana, jak pokazano w poniższym przykładzie:

`printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`

Znak *typu* określa interpretację *dokładności* lub precyzję domyślną, gdy *precyzja* zostanie pominięta, jak pokazano w poniższej tabeli.

### <a name="how-precision-values-affect-type"></a>Jak wartości dokładności mają wpływ na typ

|Typ|Znaczenie|Domyślne|
|----------|-------------|-------------|
|**`a`** , **`A`**|Precyzja określa liczbę cyfr po punkcie.|Domyślna precyzja to 13. Jeśli precyzja to 0, nie jest drukowany punkt dziesiętny, chyba że **`#`** flaga jest używana.|
|**`c`** , **`C`**|Precyzja nie ma żadnego wpływu.|Znak jest drukowany.|
|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** , **`X`**|Precyzja określa minimalną liczbę cyfr do wydrukowania. Jeśli liczba cyfr w argumencie jest mniejsza niż *precyzja* , wartość wyjściowa zostanie uzupełniona o zero. Wartość nie jest obcinana, gdy liczba cyfr przekracza *precyzję* .|Domyślna precyzja to 1.|
|**`e`** , **`E`**|Precyzja określa liczbę cyfr do wydrukowania po przecinku dziesiętnym. Ostatnia wydrukowana cyfra jest zaokrąglana.|Domyślna precyzja to 6. Jeśli *precyzja* to 0 lub kropka ( `.` ) pojawia się bez cyfry po niej, nie jest drukowany żaden punkt dziesiętny.|
|**`f`** , **`F`**|Wartość precyzji określa liczbę cyfr po przecinku dziesiętnym. Jeśli zostanie wyświetlony punkt dziesiętny, przed nim zostanie wyświetlona co najmniej jedna cyfra. Wartość jest zaokrąglana do odpowiedniej liczby cyfr.|Domyślna precyzja to 6. Jeśli *precyzja* to 0, lub jeśli kropka ( `.` ) zostanie wyświetlona bez cyfry po niej, nie jest drukowany żaden punkt dziesiętny.|
|**`g`** , **`G`**|Precyzja określa maksymalną liczbę cyfr znaczących.|Drukowane są sześć cyfr znaczących, a końcowe zera są obcinane.|
|**`s`** , **`S`**|Precyzja określa maksymalną liczbę znaków do wydrukowania. Nie są drukowane znaki o przekroczeniu *precyzji* .|Znaki są drukowane, dopóki nie zostanie znaleziony znak o wartości null.|

<a name="size"></a>

## <a name="argument-size-specification"></a>Specyfikacja rozmiaru argumentu

W specyfikacji konwersji pole *size* jest modyfikatorem długości argumentów dla specyfikatora konwersji *typu* . Pola *rozmiar* prefiksy pola *Typ* —,,, **`hh`** **`h`** **`j`** **`l`** (małe litery L),,,,,,, **`L`** **`ll`** **`t`** **`w`** **`z`** **`I`** (wielkie i), **`I32`** i **`I64`** — określają "rozmiar" odpowiadającego argumentu — Long lub Short, 32-bitowy lub 64-bitowy, znak jednobajtowy lub szeroki, w zależności od specyfikatora konwersji, który modyfikuje. Te prefiksy rozmiarów są używane z znakami *typu* w `printf` i `wprintf` rodzinach funkcji, aby określić interpretację rozmiarów argumentów, jak pokazano w poniższej tabeli. Pole *size* jest opcjonalne dla niektórych typów argumentów. Gdy nie określono prefiksu rozmiaru, program formatujący zużywa argumenty całkowite — na przykład, podpisane lub niepodpisane `char` , `short` ,, `int` `long` i typy wyliczeniowe — jako 32-bitowe typy `int` , i, `float` `double` i `long double` argumenty zmiennoprzecinkowe są używane jako 64-bitowe `double` typy. To zachowanie jest zgodne z domyślnymi regułami podwyższania poziomu argumentów dla list argumentów zmiennych. Aby uzyskać więcej informacji na temat promocji argumentów, zobacz wielokropek i argumenty domyślne w [wyrażeniach przyrostkowych](../cpp/postfix-expressions.md). W systemach 32-bitowych i 64-bitowych specyfikacja konwersji argumentu 64-bit Integer musi zawierać prefiks size **`ll`** lub **`I64`** . W przeciwnym razie zachowanie programu formatującego nie jest zdefiniowane.

Niektóre typy mają różne rozmiary w 32-bitowym i 64-bitowym kodzie. Na przykład `size_t` jest 32 bitów Long w kodzie skompilowanym dla x86 i 64 bitów w kodzie skompilowanym dla x64. Aby utworzyć kod formatowania niezależny od na platformie dla typów o zmiennej szerokości, można użyć modyfikatora rozmiaru argumentu o zmiennej szerokości. Zamiast tego należy użyć modyfikatora rozmiaru argumentu 64-bitowego i jawnie podnieść typ argumentu o zmiennej szerokości do 64 bitów. Modyfikator rozmiaru argumentu specyficzny dla firmy Microsoft **`I`** obsługuje argumenty całkowite o zmiennej szerokości, ale zalecamy użycie **`j`** modyfikatorów specyficznych dla typu **`t`** i **`z`** dla przenośności.

### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>Prefiksy rozmiarów dla specyfikatorów printf i wprintf Format-Type

|Aby określić|Użyj prefiksu|Ze specyfikatorem typu|
|----------------|----------------|-------------------------|
|`char`<br />`unsigned char`|**`hh`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|`short int`<br />`short unsigned int`|**`h`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|`__int32`<br />`unsigned __int32`|**`I32`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|`__int64`<br />`unsigned __int64`|**`I64`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|`intmax_t`<br />`uintmax_t`|**`j`** oraz **`I64`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|`long double`|**`l`** (mała litera L) lub **`L`**|**`a`** , **`A`** ,,,,, **`e`** **`E`** **`f`** **`F`** **`g`** lub **`G`**|
|`long int`<br />`long unsigned int`|**`l`** (mała litera L) |**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`** |
|`long long int`<br />`unsigned long long int`|**`ll`**  (małe litery)|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|`ptrdiff_t`|**`t`** lub **`I`** (wielkie litery i)|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|`size_t`|**`z`** lub **`I`** (wielkie litery i)|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** lub **`X`**|
|Znak jednobajtowy|**`h`**|**`c`** oraz **`C`**|
|Znak dwubajtowy|**`l`** (mała litera L) lub **`w`**|**`c`** oraz **`C`**|
|Jednobajtowy ciąg znaków|**`h`**|**`s`** , **`S`** lub **`Z`**|
|Ciąg znaków dwubajtowych|**`l`** (mała litera L) lub **`w`**|**`s`** , **`S`** lub **`Z`**|

`ptrdiff_t`Typy i `size_t` są `__int32` `unsigned __int32` na platformach 32-bitowych i `__int64` lub `unsigned __int64` na platformach 64-bitowych. **`I`** Prefiksy (wielką literą i),, **`j`** **`t`** i **`z`** rozmiary, przyjmują poprawną szerokość argumentu dla danej platformy.

W Visual C++, chociaż `long double` jest typem odrębnym, ma tę samą reprezentację wewnętrzną co `double` .

**`hc`** **`hC`** Specyfikator typu or jest synonimem **`c`** w `printf` funkcjach Functions i with **`C`** in `wprintf` Functions. **`lc`** **`lC`** **`wc`** Specyfikator typu,,, lub **`wC`** jest równoznaczny z **`C`** w `printf` funkcjach Functions i with **`c`** in `wprintf` Functions. **`hs`** **`hS`** Specyfikator typu or jest synonimem **`s`** w `printf` funkcjach Functions i with **`S`** in `wprintf` Functions. **`ls`** **`lS`** **`ws`** Specyfikator typu,,, lub **`wS`** jest równoznaczny z **`S`** w `printf` funkcjach Functions i with **`s`** in `wprintf` Functions.

> [!NOTE]
> **Specyficzne dla firmy Microsoft:**\
> **`I`** Prefiksy modyfikatorów rozmiaru (Wielka litera i),, **`I32`** **`I64`** i **`w`** argumentu są rozszerzeniami firmy Microsoft i nie są zgodne ze standardem ISO C. **`h`** Prefiks, gdy jest używany z danymi typu `char` i **`l`** prefiksem (małymi literami L), gdy jest używany z danymi typu `double` są rozszerzeniami firmy Microsoft.

## <a name="see-also"></a>Zobacz także

[`printf, _printf_l, wprintf, _wprintf_l`](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\
[`printf_s, _printf_s_l, wprintf_s, _wprintf_s_l`](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)\
[`printf_p` Parametry pozycyjne](../c-runtime-library/printf-p-positional-parameters.md)
