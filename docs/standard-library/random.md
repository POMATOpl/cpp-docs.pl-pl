---
description: 'Dowiedz się więcej o: &lt; losowo&gt;'
title: '&lt;wybranych&gt;'
ms.date: 08/24/2017
f1_keywords:
- <random>
helpviewer_keywords:
- random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
ms.openlocfilehash: 4080e305620dbe4b8fa1674762c27ece4eccd0a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337965"
---
# <a name="ltrandomgt"></a>&lt;wybranych&gt;

Definiuje obiekty do losowego generowania liczb, umożliwiając tworzenie równomiernie rozłożonych liczb losowych.

## <a name="requirements"></a>Wymagania

**Nagłówek**: \<random>

**Przestrzeń nazw:** std

> [!NOTE]
> \<random>Biblioteka używa instrukcji "#include <initializer_list>".

## <a name="summary"></a>Podsumowanie

*Generator liczb losowych* jest obiektem, który tworzy sekwencję wartości pseudolosowych. Generator, który tworzy wartości, które są równomiernie dystrybuowane w określonym zakresie, jest *jednolite generator liczb losowych* (URNG). Szablon klasy zaprojektowany do działania jako URNG jest określany jako *aparat* , jeśli ta klasa ma pewne wspólne cechy, które zostały omówione w dalszej części tego artykułu. URNG może być — i zazwyczaj jest — połączony z *dystrybucją* , przekazując URNG jako argument do dystrybucji w `operator()` celu utworzenia wartości dystrybuowanych w sposób zdefiniowany przez rozkład.

Te linki przeskoczą do najważniejszych sekcji tego artykułu:

- [Przykłady](#code)

- [Lista z kategoryzacją](#listing)

- [Aparaty i dystrybucje](#engdist)

- [Uwagi](#comments)

### <a name="quick-tips"></a>Szybkie porady

Poniżej przedstawiono kilka porad, które należy wziąć pod uwagę podczas korzystania z programu \<random> :

- W większości zastosowań URNGs tworzy niesformatowane bity, które muszą mieć kształt dystrybucji. (Istotny wyjątek dla tego elementu to [std:: losowo ()](../standard-library/algorithm-functions.md#shuffle) , ponieważ używa on URNG bezpośrednio).

- Nie można bezpiecznie wywołać pojedynczego wystąpienia URNG lub dystrybucji, ponieważ jest uruchomiona URNG lub dystrybucja jest operacją modyfikującą. Aby uzyskać więcej informacji, zobacz [bezpieczeństwo wątków w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md).

- Dostępne są [wstępnie zdefiniowane elementy typedef](#typedefs) kilku aparatów; jest to preferowany sposób utworzenia elementu URNG, jeśli jest używany aparat.

- Najbardziej przydatnym parowaniem dla większości aplikacji jest `mt19937` aparat z `uniform_int_distribution` , jak pokazano w [przykładzie kodu](#code) w dalszej części tego artykułu.

Istnieje wiele opcji, które można wybrać w \<random> nagłówku, a każda z nich jest preferowana przez nieaktualną funkcję środowiska uruchomieniowego C `rand()` . Aby uzyskać informacje o błędach `rand()` i sposobach \<random> ich działania, zobacz [ten klip wideo](https://go.microsoft.com/fwlink/p/?linkid=397615).

## <a name="examples"></a><a name="code"></a> Pokazują

Poniższy przykład kodu pokazuje, jak generować liczby losowe w tym przypadku pięć z nich przy użyciu generatora utworzonego z niedeterministycznym inicjatorem.

```cpp
#include <random>
#include <iostream>

using namespace std;

int main()
{
    random_device rd;   // non-deterministic generator
    mt19937 gen(rd());  // to seed mersenne twister.
                        // replace the call to rd() with a
                        // constant value to get repeatable
                        // results.

    for (int i = 0; i < 5; ++i) {
        cout << gen() << " "; // print the raw output of the generator.
    }
    cout << endl;
}
```

```Output
2430338871 3531691818 2723770500 3252414483 3632920437
```

Chociaż są to liczby losowe o wysokiej jakości i są różne za każdym razem, gdy ten program jest uruchamiany, nie musi to być użyteczny zakres. Aby sterować zakresem, użyj jednorodnej dystrybucji, jak pokazano w poniższym kodzie:

```cpp
#include <random>
#include <iostream>

using namespace std;

int main()
{
    random_device rd;   // non-deterministic generator
    mt19937 gen(rd());  // to seed mersenne twister.
    uniform_int_distribution<> dist(1,6); // distribute results between 1 and 6 inclusive.

    for (int i = 0; i < 5; ++i) {
        cout << dist(gen) << " "; // pass the generator to the distribution.
    }
    cout << endl;
}
```

```Output
5 1 6 1 2
```

Następny przykład kodu przedstawia bardziej realistyczny zestaw przypadków użycia z równomiernie dystrybuowanymi generatorami liczb losowych Shuffling zawartość wektora i tablicy.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <array>
#include <iostream>
#include <random>
#include <string>
#include <vector>
#include <functional> // ref()

using namespace std;

template <typename C> void print(const C& c) {
    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

template <class URNG>
void test(URNG& urng) {

    // Uniform distribution used with a vector
    // Distribution is [-5, 5] inclusive
    uniform_int_distribution<int> dist(-5, 5);
    vector<int> v;

    for (int i = 0; i < 20; ++i) {
        v.push_back(dist(urng));
    }

    cout << "Randomized vector: ";
    print(v);

    // Shuffle an array
    // (Notice that shuffle() takes a URNG, not a distribution)
    array<string, 26> arr = { { "H", "He", "Li", "Be", "B", "C", "N", "O", "F",
        "Ne", "Na", "Mg", "Al", "Si", "P", "S", "Cl", "Ar", "K", "Ca", "Sc",
        "Ti", "V", "Cr", "Mn", "Fe" } };

    shuffle(arr.begin(), arr.end(), urng);

    cout << "Randomized array: ";
    print(arr);
    cout << "--" << endl;
}

int main()
{
    // First run: non-seedable, non-deterministic URNG random_device
    // Slower but crypto-secure and non-repeatable.
    random_device rd;
    cout << "Using random_device URNG:" << endl;
    test(rd);

    // Second run: simple integer seed, repeatable results
    cout << "Using constant-seed mersenne twister URNG:" << endl;
    mt19937 engine1(12345);
    test(engine1);

    // Third run: random_device as a seed, different each run
    // (Desirable for most purposes)
    cout << "Using non-deterministic-seed mersenne twister URNG:" << endl;
    mt19937 engine2(rd());
    test(engine2);

    // Fourth run: "warm-up" sequence as a seed, different each run
    // (Advanced uses, allows more than 32 bits of randomness)
    cout << "Using non-deterministic-seed \"warm-up\" sequence mersenne twister URNG:" << endl;
    array<unsigned int, mt19937::state_size> seed_data;
    generate_n(seed_data.begin(), seed_data.size(), ref(rd));
    seed_seq seq(begin(seed_data), end(seed_data));
    mt19937 engine3(seq);
    test(engine3);
}
```

```Output
Using random_device URNG:
Randomized vector: 5 -4 2 3 0 5 -2 0 4 2 -1 2 -4 -3 1 4 4 1 2 -2
Randomized array: O Li V K C Ti N Mg Ne Sc Cl B Cr Mn Ca Al F P Na Be Si Ar Fe S He H
--
Using constant-seed mersenne twister URNG:
Randomized vector: 3 -1 -5 0 0 5 3 -4 -3 -4 1 -3 0 -3 -2 -4 5 1 -1 -1
Randomized array: Al O Ne Si Na Be C N Cr Mn H V F Sc Mg Fe K Ca S Ti B P Ar Cl Li He
--
Using non-deterministic-seed mersenne twister URNG:
Randomized vector: 5 -4 0 2 1 -2 4 4 -4 0 0 4 -5 4 -5 -1 -3 0 0 3
Randomized array: Si Fe Al Ar Na P B Sc H F Mg Li C Ti He N Mn Be O Ca Cr V K Ne Cl S
--
Using non-deterministic-seed "warm-up" sequence mersenne twister URNG:
Randomized vector: -1 3 -2 4 1 3 0 -5 5 -5 0 0 5 0 -3 3 -4 2 5 0
Randomized array: Si C Sc H Na O S Cr K Li Al Ti Cl B Mn He Fe Ne Be Ar V P Ca N Mg F
--
```

Ten kod ilustruje dwa różne losowości — losowo wektora liczb całkowitych i losowo tablicę indeksowanych danych — z funkcją szablonu testowego. Pierwsze wywołanie funkcji testowej używa kryptograficznego, niepowtarzalnego, nieURNGego, niedozwolonego do użycia `random_device` . Drugi przebieg testu jest używany `mersenne_twister_engine` jako URNG z deterministyczną 32-bitowym stałym inicjatorem, co oznacza, że wyniki są powtarzalne. Trzecie ziarna przebiegu testowego `mersenne_twister_engine` o 32-bitowym wyniku niedeterministycznym od `random_device` . Czwarty przebieg testu jest rozwijany przy użyciu [sekwencji inicjatora](../standard-library/seed-seq-class.md) wypełnionej `random_device` wynikami, co efektywnie daje ponad 32-bitową losowość niedeterministyczną (ale wciąż nie jest zabezpieczona). Aby uzyskać więcej informacji, przeczytaj artykuł.

## <a name="categorized-listing"></a><a name="listing"></a> Lista z kategoryzacją

### <a name="uniform-random-number-generators"></a><a name="urngs"></a> Jednolite generatory liczb losowych

URNGs są często opisywane pod kątem następujących właściwości:

1. **Długość okresu**: ile iteracji ma powtórzyć sekwencję wygenerowanych wartości. Im większa.

2. **Wydajność**: jak szybko można generować numery i ile pamięci potrzebuje. Im mniejsze.

3. **Jakość**: w jaki sposób zbliżone do prawdziwe liczby losowe Wygenerowano sekwencję. Jest to często nazywane "*losowości*".

W poniższych sekcjach wymieniono jednolite generatory liczb losowych (URNGs), które znajdują się w \<random> nagłówku.

#### <a name="non-deterministic-generator"></a><a name="rd"></a> Generator Niedeterministyczny

[Klasa random_device](../standard-library/random-device-class.md)\
Generuje niedeterministyczną, kryptograficznie bezpieczną sekwencję losową przy użyciu urządzenia zewnętrznego. Zwykle używany do wypełniania aparatu. Niska wydajność i bardzo wysoka jakość. Aby uzyskać więcej informacji, zobacz [uwagi](#comments).

#### <a name="engine-typedefs-with-predefined-parameters"></a><a name="typedefs"></a> Elementy typedef aparatu ze wstępnie zdefiniowanymi parametrami

Do tworzenia wystąpień aparatów i adapterów. Aby uzyskać więcej informacji, zobacz [Aparaty i dystrybucje](#engdist).

- `default_random_engine` Domyślny aparat.

    ```cpp
    typedef mt19937 default_random_engine;
    ```

- `knuth_b` Aparat Knuth.

    ```cpp
    typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;
    ```

- `minstd_rand0` 1988 minimalne standardowe aparatu (Lewis przedstawiają, Goodman i Miller, 1969).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
    ```

- `minstd_rand` Zaktualizowano minimalny silnik standardowy `minstd_rand0` (Park, Miller i Stockmeyer, 1993).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
    ```

- `mt19937` 32-bitowy aparat Twister Mersenne (Matsumoto i Nishimura, 1998).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned int, 32, 624, 397,
        31, 0x9908b0df,
        11, 0xffffffff,
        7, 0x9d2c5680,
        15, 0xefc60000,
        18, 1812433253> mt19937;
    ```

- `mt19937_64` 64-bitowy aparat Twister Mersenne (Matsumoto i Nishimura, 2000).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned long long, 64, 312, 156,
        31, 0xb5026f5aa96619e9ULL,
        29, 0x5555555555555555ULL,
        17, 0x71d67fffeda60000ULL,
        37, 0xfff7eee000000000ULL,
        43, 6364136223846793005ULL> mt19937_64;
    ```

- `ranlux24` 24-bitowy aparat RANLUX (Martin Lüscher i Fred Kuba, 1994).

    ```cpp
    typedef discard_block_engine<ranlux24_base, 223, 23> ranlux24;
    ```

- `ranlux24_base` Używany jako podstawa dla `ranlux24` .

    ```cpp
    typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;
    ```

- `ranlux48` 48-bitowy aparat RANLUX (Martin Lüscher i Fred Kuba, 1994).

    ```cpp
    typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;
    ```

- `ranlux48_base` Używany jako podstawa dla `ranlux48` .

    ```cpp
    typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;
    ```

#### <a name="engine-templates"></a><a name="eng"></a> Szablony aparatu

Szablony aparatu są używane jako autonomiczne URNGs lub jako silniki podstawowe przenoszone do [adapterów aparatu](#engadapt). Zwykle są one tworzone ze [wstępnie zdefiniowanym elementem TypeDef](#typedefs) i są przesyłane do [dystrybucji](#distributions). Aby uzyskać więcej informacji, zobacz sekcję [silniki i dystrybucje](#engdist) .

|Nazwa|Opis|
|-|-|
|[Klasa linear_congruential_engine](../standard-library/linear-congruential-engine-class.md)|Generuje losową sekwencję przy użyciu liniowego algorytmu złożony. Większość uproszczony i najniższej jakości.|
|[Klasa mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)|Generuje losową sekwencję przy użyciu algorytmu Mersenne Twister. Najbardziej złożona i jest najwyższa jakość z wyjątkiem klasy random_device. Bardzo szybka wydajność.|
|[Klasa subtract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md)|Generuje losową sekwencję przy użyciu algorytmu odejmowania i przenoszenia. Poprawa `linear_congruential_engine` wydajności, ale znacznie niższa jakość i wydajność niż `mersenne_twister_engine` .|

#### <a name="engine-adaptor-templates"></a><a name="engadapt"></a> Szablony adaptera

Adaptery aparatu są szablonami, które dostosowują inne (podstawowe) aparaty. Zwykle są one tworzone ze [wstępnie zdefiniowanym elementem TypeDef](#typedefs) i są przesyłane do [dystrybucji](#distributions). Aby uzyskać więcej informacji, zobacz sekcję [silniki i dystrybucje](#engdist) .

|Nazwa|Opis|
|-|-|
|[Klasa discard_block_engine](../standard-library/discard-block-engine-class.md)|Generuje losową sekwencję przez odrzucenie wartości zwracanych przez aparat podstawowy.|
|[Klasa independent_bits_engine](../standard-library/independent-bits-engine-class.md)|Generuje losową sekwencję z określoną liczbą bitów przez przepakowanie bitów z wartości zwracanych przez aparat podstawowy.|
|[Klasa shuffle_order_engine](../standard-library/shuffle-order-engine-class.md)|Generuje losową sekwencję przez zmianę kolejności wartości zwracanych z aparatu podstawowego.|

[[Szablony aparatu](#eng)]

### <a name="random-number-distributions"></a><a name="distributions"></a> Rozkłady liczb losowych

W poniższych sekcjach wymieniono dystrybucje podane w \<random> nagłówku. Dystrybucje to mechanizm przetwarzania końcowego, zwykle korzystający z danych wyjściowych URNG jako dane wejściowe i rozpowszechniania danych wyjściowych przez zdefiniowaną funkcję gęstości prawdopodobieństwa. Aby uzyskać więcej informacji, zobacz sekcję [silniki i dystrybucje](#engdist) .

#### <a name="uniform-distributions"></a>Rozkłady jednorodne

|Nazwa|Opis|
|-|-|
|[Klasa uniform_int_distribution](../standard-library/uniform-int-distribution-class.md)|Tworzy jednolitą dystrybucję wartości całkowitych dla zakresu w zamkniętym interwale \[ a, b] (włącznie).|
|[Klasa uniform_real_distribution](../standard-library/uniform-real-distribution-class.md)|Tworzy jednolitą (zmiennoprzecinkową) dystrybucję wartości dla zakresu w interwale o połowie otwartym [a, b) (włącznie z wyłączeniem).|
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|Tworzy parzystą dystrybucję wartości rzeczywistych (zmiennoprzecinkowych) dla danej precyzji w zakresie [0, 1) (włącznie z wyłączeniem).|

[[Rozkład liczb losowych](#distributions)]

#### <a name="bernoulli-distributions"></a>Rozkłady Bernoulliego

|Nazwa|Opis|
|-|-|
|[Klasa bernoulli_distribution](../standard-library/bernoulli-distribution-class.md)|Tworzy rozkład Bernoulliego **`bool`** wartości.|
|[Klasa binomial_distribution](../standard-library/binomial-distribution-class.md)|Tworzy rozkład dwumianowy wartości liczb całkowitych.|
|[Klasa geometric_distribution](../standard-library/geometric-distribution-class.md)|Generuje geometryczną dystrybucję wartości całkowitych.|
|[Klasa negative_binomial_distribution](../standard-library/negative-binomial-distribution-class.md)|Generuje ujemny rozkład dwumianowy wartości liczb całkowitych.|

[[Rozkład liczb losowych](#distributions)]

#### <a name="normal-distributions"></a>Rozkłady normalne

|Nazwa|Opis|
|-|-|
|[Klasa cauchy_distribution](../standard-library/cauchy-distribution-class.md)|Tworzy rozkład Cauchy wartości rzeczywistych (zmiennoprzecinkowych).|
|[Klasa chi_squared_distribution](../standard-library/chi-squared-distribution-class.md)|Tworzy rozkład wartości rzeczywistej (zmiennoprzecinkowej) w postaci chi-kwadrat.|
|[Klasa fisher_f_distribution](../standard-library/fisher-f-distribution-class.md)|Tworzy rozkład F (znany również jako Snedecor F lub dystrybucji Fisher-Snedecor) rzeczywiste (zmiennoprzecinkowe) wartości.|
|[Klasa lognormal_distribution](../standard-library/lognormal-distribution-class.md)|Tworzy LOGARYTM normalny dla rzeczywistych (zmiennoprzecinkowych) wartości.|
|[Klasa normal_distribution](../standard-library/normal-distribution-class.md)|Tworzy normalny (gaussowskie) rozkład rzeczywistych (zmiennoprzecinkowych) wartości.|
|[Klasa student_t_distribution](../standard-library/student-t-distribution-class.md)|Tworzy dystrybucję *t* dla ucznia rzeczywistych (zmiennoprzecinkowych) wartości.|

[[Rozkład liczb losowych](#distributions)]

#### <a name="poisson-distributions"></a>Rozkłady Poissona

|Nazwa|Opis|
|-|-|
|[Klasa exponential_distribution](../standard-library/exponential-distribution-class.md)|Tworzy wykładniczą dystrybucję rzeczywistych (zmiennoprzecinkowych) wartości.|
|[Klasa extreme_value_distribution](../standard-library/extreme-value-distribution-class.md)|Tworzy rozkład wartości rzeczywistych (zmiennoprzecinkowych) wartości.|
|[Klasa gamma_distribution](../standard-library/gamma-distribution-class.md)|Tworzy rozkład gamma wartości rzeczywistych (zmiennoprzecinkowych).|
|[Klasa poisson_distribution](../standard-library/poisson-distribution-class.md)|Tworzy rozkład Poissona wartości liczb całkowitych.|
|[Klasa weibull_distribution](../standard-library/weibull-distribution-class.md)|Tworzy rozkład Weibulla dla rzeczywistych (zmiennoprzecinkowych) wartości.|

[[Rozkład liczb losowych](#distributions)]

#### <a name="sampling-distributions"></a>Dystrybucje próbkowania

|Nazwa|Opis|
|-|-|
|[Klasa discrete_distribution](../standard-library/discrete-distribution-class.md)|Tworzy dyskretną dystrybucję całkowitą.|
|[Klasa piecewise_constant_distribution](../standard-library/piecewise-constant-distribution-class.md)|Tworzy rozkład elementowy stałą dystrybucję rzeczywistych (zmiennoprzecinkowych) wartości.|
|[Klasa piecewise_linear_distribution](../standard-library/piecewise-linear-distribution-class.md)|Tworzy rozkład liniowy rozkład elementowy wartości rzeczywiste (zmiennoprzecinkowe).|

[[Rozkład liczb losowych](#distributions)]

### <a name="utility-functions"></a>Funkcje narzędziowe

W tej sekcji wymieniono ogólne funkcje narzędzia dostępne w \<random> nagłówku.

|Nazwa|Opis|
|-|-|
|[Klasa seed_seq](../standard-library/seed-seq-class.md)|Generuje nieobciążone sekwencje inicjatora. Służy do uniknięcia replikacji losowych strumieni variate. Przydatne w przypadku wystąpienia wielu URNGs z aparatów.|

### <a name="operators"></a>Operatory

Ta sekcja zawiera listę operatorów, które znajdują się w \<random> nagłówku.

|Nazwa|Opis|
|-|-|
|`operator==`|Testuje, czy URNG po lewej stronie operatora jest równy aparatowi po prawej stronie.|
|`operator!=`|Testuje, czy URNG po lewej stronie operatora nie jest równy aparatowi po prawej stronie.|
|`operator<<`|Zapisuje informacje o stanie w strumieniu.|
|`operator>>`|Wyodrębnia informacje o stanie ze strumienia.|

## <a name="engines-and-distributions"></a><a name="engdist"></a> Aparaty i dystrybucje

Zapoznaj się z następującymi sekcjami, aby uzyskać informacje o każdej z tych kategorii szablonów klas zdefiniowanych w temacie \<random> . Obie te kategorie szablonu klasy przyjmują typ jako argument i używają nazw parametrów szablonu udostępnionego do opisywania właściwości typu, który jest dozwolony jako rzeczywisty typ argumentu, w następujący sposób:

- `IntType` wskazuje,,,,, **`short`** **`int`** ,, **`long`** **`long long`** **`unsigned short`** **`unsigned int`** **`unsigned long`** lub **`unsigned long long`** .

- `UIntType` wskazuje **`unsigned short`** , **`unsigned int`** , **`unsigned long`** , lub **`unsigned long long`** .

- `RealType` wskazuje **`float`** , **`double`** , lub **`long double`** .

### <a name="engines"></a>Silnika

Szablony [aparatu](#eng) i [Szablony adaptera aparatów](#engadapt) są szablonami, których parametry dostosowują utworzony Generator.

*Aparat* jest klasą lub szablonem klasy, którego wystąpienia (Generatory) działają jako źródło liczb losowych równomiernie dystrybuowanych między wartością minimalną i maksymalną. *Adapter* przyciąga za sobą sekwencję wartości, które mają różne właściwości losowe, pobierając wartości z innego silnika liczb losowych i stosując algorytm pewnego rodzaju do tych wartości.

Każdy aparat i aparat adaptera mają następujące elementy członkowskie:

- **`typedef`**`numeric-type` `result_type` jest typem zwracanym przez generatora `operator()` . `numeric-type`Jest przenoszona jako parametr szablonu podczas tworzenia wystąpienia.

- `result_type operator()` zwraca wartości, które są jednolicie dystrybuowane między `min()` i `max()` .

- `result_type min()` Zwraca wartość minimalną, która jest zwracana przez generatora `operator()` . Adaptery silnikowe używają wyniku aparatu podstawowego `min()` .

- `result_type max()` zwraca maksymalną wartość, która jest zwracana przez generatora `operator()` . Gdy `result_type` jest typem całkowitym (o wartości całkowitej), `max()` jest wartością maksymalną, która faktycznie może zostać zwrócona (włącznie); gdy `result_type` jest typem zmiennoprzecinkowym (wartość rzeczywista), `max()` jest najmniejszą wartością większą niż wszystkie wartości, które mogą być zwracane (niewłączne). Adaptery silnikowe używają wyniku aparatu podstawowego `max()` .

- `void seed(result_type s)` Nasiona generatora z wartością inicjatora `s` . W przypadku aparatów podpis jest `void seed(result_type s = default_seed)` przeznaczony dla obsługi parametrów domyślnych (adaptery łączników definiują oddzielne `void seed()` , zobacz następną podsekcję).

- `template <class Seq> void seed(Seq& q)`Nasiona generatora przy użyciu [seed_seq](../standard-library/seed-seq-class.md) `Seq` .

- Jawny Konstruktor z argumentem `result_type x` , który tworzy generator, jako if przez wywołanie `seed(x)` .

- Jawny Konstruktor z argumentem `seed_seq& seq` , który tworzy generator, jako if przez wywołanie `seed(seq)` .

- `void discard(unsigned long long count)` skutecznie wywołuje `operator()` `count` czas i odrzuca każdą wartość.

**Adaptery** obsługują dodatkowo te elementy członkowskie ( `Engine` jest pierwszym parametrem szablonu adaptera silnika, wyznaczając typ aparatu podstawowego):

- Domyślny konstruktor, który umożliwia zainicjowanie generatora jako IF z domyślnego konstruktora aparatu podstawowego.

- Jawny Konstruktor z argumentem `const Engine& eng` . Jest to obsługa kopiowania kopii przy użyciu aparatu podstawowego.

- Jawny Konstruktor z argumentem `Engine&& eng` . Ma to na celu obsługę konstrukcji przenoszenia przy użyciu aparatu podstawowego.

- `void seed()` powoduje to zainicjowanie generatora przy użyciu domyślnej wartości inicjatora aparatu podstawowego.

- `const Engine& base()` Funkcja właściwości, która zwraca silnik podstawowy, który został użyty do skonstruowania generatora.

Każdy aparat zachowuje *stan* , który określa sekwencję wartości, które zostaną wygenerowane przez kolejne wywołania do `operator()` . Stany dwóch generatorów, które są tworzone na podstawie silników tego samego typu, można porównać przy użyciu `operator==` i `operator!=` . Jeśli dwa stany są porównywane jako równe, generują taką samą sekwencję wartości. Stan obiektu można zapisać w strumieniu jako sekwencję 32-bitowe niepodpisane wartości przy użyciu `operator<<` generatora. Stan nie jest zmieniany przez zapisanie go. Zapisany stan można odczytać w generatorze skonkretyzowanym z aparatu tego samego typu przy użyciu `operator>>` .

### <a name="distributions"></a>Dystrybucji

[Rozkład liczb losowych](#distributions) jest klasą lub szablonem klasy, którego wystąpienia przekształcają strumień równomiernie dystrybuowanych liczb losowych uzyskanych z aparatu do strumienia liczb losowych, które mają określoną dystrybucję. Każda dystrybucja ma następujące elementy członkowskie:

- **`typedef`**`numeric-type` `result_type` jest typem zwracanym przez dystrybucję `operator()` . `numeric-type`Jest przenoszona jako parametr szablonu podczas tworzenia wystąpienia.

- `template <class URNG> result_type operator()(URNG& gen)` zwraca wartości, które są dystrybuowane zgodnie z definicją dystrybucji, za pomocą `gen` jako źródło równomiernie dystrybuowanych wartości losowych i przechowywanych *parametrów dystrybucji*.

- `template <class URNG> result_type operator()(URNG& gen, param_type p)` zwraca wartości dystrybuowane zgodnie z definicją dystrybucji, używając `gen` jako źródła równomiernie dystrybuowanych wartości losowych i struktury parametrów `p` .

- **`typedef`**`unspecified-type` `param_type` jest pakiet parametrów, opcjonalnie przekazywać do `operator()` i jest używany zamiast przechowywanych parametrów w celu wygenerowania jego wartości zwracanej.

- `const param&`Konstruktor inicjuje przechowywane parametry z jego argumentu.

- `param_type param() const` Pobiera przechowywane parametry.

- `void param(const param_type&)` Ustawia parametry przechowywane z tego argumentu.

- `result_type min()` Zwraca wartość minimalną, która jest zwracana przez dystrybucję `operator()` .

- `result_type max()` zwraca maksymalną wartość zwracaną przez dystrybucję `operator()` . Gdy `result_type` jest typem całkowitym (o wartości całkowitej), `max()` jest wartością maksymalną, która faktycznie może zostać zwrócona (włącznie); gdy `result_type` jest typem zmiennoprzecinkowym (wartość rzeczywista), `max()` jest najmniejszą wartością większą niż wszystkie wartości, które mogą być zwracane (niewłączne).

- `void reset()` odrzuca wartości w pamięci podręcznej, dzięki czemu wynik następnego wywołania do `operator()` nie zależy od wartości uzyskanych z aparatu przed wywołaniem.

Struktura parametru jest obiektem, który przechowuje wszystkie parametry, które są zbędne do dystrybucji. Zawiera ona:

- **`typedef`**`distribution-type` `distribution_type` , który jest typem rozkładu.

- Co najmniej jeden Konstruktor, który przyjmuje te same listy parametrów jak konstruktory dystrybucji.

- Te same funkcje dostępu do parametrów jak dystrybucja.

- Operatory porównania równości i nierówności.

Aby uzyskać więcej informacji, zapoznaj się z tematami podrzędnymi odwołań poniżej tego, które zostały połączone wcześniej w tym artykule.

## <a name="remarks"></a><a name="comments"></a> Uwagi

Istnieją dwa wysoce przydatne URNGs w programie Visual Studio — `mt19937` i `random_device` — jak pokazano w tej tabeli porównawczej:

|URNG|Duża|Zabezpieczenia kryptograficzne|Do rozsadzenia|Deterministyczne|
|----------|-----------|---------------------|---------------|--------------------|
|`mt19937`|Tak|Nie|Tak|Opcję<sup>*</sup>|
|`random_device`|Nie|Tak|Nie|Nie|

<sup>* Jeśli jest dostarczany ze znanym inicjatorem.</sup>

Mimo że standard ISO C++ nie musi `random_device` być bezpiecznie zabezpieczony, w programie Visual Studio jest zaimplementowana w celu zabezpieczenia kryptograficznego. (Termin "zabezpieczenia kryptograficzne" nie implikuje gwarancji, ale odnosi się do minimalnego poziomu entropii — i w związku z tym poziom przewidywalności — dany algorytm losowości zapewnia. Aby uzyskać więcej informacji, zapoznaj się z artykułem Wikipedia " [cryptographicly Secure pseudolosowych Number Generator](https://go.microsoft.com/fwlink/p/?linkid=398017)"). Ze względu na to, że standard ISO C++ nie wymaga tego, inne platformy mogą implementować `random_device` jako proste generatory liczb pseudolosowych (niezabezpieczone kryptograficznie) i mogą być odpowiednie jako źródło inicjatora dla innego generatora. Zapoznaj się z dokumentacją dla tych platform, korzystając `random_device` z kodu międzyplatformowego.

Zgodnie z definicją `random_device` wyniki nie są odtwarzalne, a efektem ubocznym jest, że może działać znacznie wolniej niż inne URNGs. Większość aplikacji, które nie są wymagane do użycia w kryptografii zabezpieczającej `mt19937` , lub podobnego aparatu, chociaż może chcieć być inicjatorem za pomocą wywołania `random_device` , jak pokazano w [przykładzie kodu](#code).

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)
