---
title: if-else — instrukcja (C++)
description: Użyj if-else, if-else z inicjatorem i instrukcji if-constexpr do kontrolowania warunkowego rozgałęzienia.
ms.date: 10/02/2020
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 20d828bf00a79687fe0a9fffbeb1a9cc56fae08c
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765294"
---
# <a name="if-else-statement-c"></a>if-else — instrukcja (C++)

Instrukcja if-else kontroluje rozgałęzienie warunkowe. Instrukcje w *`if-branch`* są wykonywane tylko wtedy, gdy wartość jest równa *`condition`* zero (lub **`true`** ). Jeśli wartość *`condition`* jest różna od zera, wykonywana jest następująca instrukcja, a instrukcja po instrukcji opcjonalnej jest **`else`** pomijana. W przeciwnym razie Poniższa instrukcja zostanie pominięta i jeśli jest to **`else`** instrukcja po instrukcji get **`else`** .

*`condition`* wyrażenia, które mają wartość różną od zera, są następujące:

- **`true`**
- wskaźnik o wartości innej niż null,
- dowolna wartość arytmetyczna niezerowa lub
- Typ klasy, który definiuje jednoznaczną konwersję na typ arytmetyczny, Boolean lub typu wskaźnika. (Aby uzyskać informacje na temat konwersji, zobacz [Konwersje standardowe](../cpp/standard-conversions.md)).

## <a name="syntax"></a>Składnia

*`init-statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`simple-declaration`*

*`condition`*:\
&emsp; *`expression`*\
&emsp;*`attribute-specifier-seq`* <sub>*opt*</sub> *`decl-specifier-seq`* wybór *`declarator`**`brace-or-equal-initializer`*

*`statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`compound-statement`*

*`expression-statement`*:\
&emsp;*`expression`* <sub>*wybór*</sub>**`;`**

*`compound-statement`*:\
&emsp;**`{`** *`statement-seq`* <sub>*wybór*</sub>**`}`**

*`statement-seq`*:\
&emsp; *`statement`*\
&emsp; *`statement-seq`* *`statement`*

*`if-branch`*:\
&emsp; *`statement`*

*`else-branch`*:\
&emsp; *`statement`*

*`selection-statement`*:\
&emsp;**`if`** **`constexpr`** <sub>*wybór*</sub><sup>17</sup> **`(`** *`init-statement`* <sub>*opt*</sub><sup>17</sup> 17 *`condition`* **`)`***`if-branch`*\
&emsp;**`if`** **`constexpr`** <sub>*wybór*</sub><sup>17</sup> **`(`** *`init-statement`* <sub>*opt*</sub><sup>17</sup> 17 *`condition`* **`)`** *`if-branch`* **`else`***`else-branch`*

<sup>17</sup> Ten opcjonalny element jest dostępny od języka c++ 17.

## <a name="if-else-statements"></a>instrukcje if-else

We wszystkich formach **`if`** instrukcji, *`condition`* które mogą mieć dowolną wartość z wyjątkiem struktury, jest oceniana, łącznie ze wszystkimi efektami ubocznymi. Kontrolka przechodzi z **`if`** instrukcji do następnej instrukcji w programie, chyba że wykonano *`if-branch`* lub *`else-branch`* zawiera [`break`](../cpp/break-statement-cpp.md) , [`continue`](../cpp/continue-statement-cpp.md) lub [`goto`](../cpp/goto-statement-cpp.md) .

**`else`** Klauzula `if...else` instrukcji jest skojarzona z najbliższą poprzednią **`if`** instrukcją w tym samym zakresie, który nie ma odpowiedniej **`else`** instrukcji.

### <a name="example"></a>Przykład

Ten przykładowy kod pokazuje kilka **`if`** instrukcji w użyciu, zarówno z, jak i bez **`else`** :

```cpp
// if_else_statement.cpp
#include <iostream>

using namespace std;

class C
{
    public:
    void do_something(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

    // no else statement
    if (x == 10)
    {
        x = 0;
    }

    C* c;
    init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```

## <a name="if-statement-with-an-initializer"></a><a name="if_with_init"></a> Instrukcja if z inicjatorem

Począwszy od języka C++ 17, **`if`** instrukcja może również zawierać *`init-statement`* wyrażenie, które deklaruje i inicjuje nazwaną zmienną. Użyj tej postaci instrukcji if-Statement, gdy zmienna jest wymagana tylko w zakresie instrukcji if-Statement. **Specyficzny dla firmy Microsoft**: ten formularz jest dostępny w programie Visual Studio 2017 w wersji 15,3 i wymaga co najmniej [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) opcji kompilatora.

### <a name="example"></a>Przykład

```cpp
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>

using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }

    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }
}
```

## <a name="a-nameif_constexpr-if-constexpr-statements"></a><a name="if_constexpr"> If constexpr — instrukcje

Począwszy od języka C++ 17, można użyć **`if constexpr`** instrukcji w szablonach funkcji, aby podejmować decyzje dotyczące rozgałęziania czasu kompilacji bez konieczności przeciążania wielu funkcji. **Specyficzny dla firmy Microsoft**: ten formularz jest dostępny w programie Visual Studio 2017 w wersji 15,3 i wymaga co najmniej [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) opcji kompilatora.

### <a name="example"></a>Przykład

Ten przykład pokazuje, jak można napisać pojedynczą funkcję, która obsługuje rozpakowywanie parametrów. Nie jest wymagany Przeciążenie o wartości zero parametrów:

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
    // handle t
    do_something(t);

    // handle r conditionally
    if constexpr (sizeof...(r))
    {
        f(r...);
    }
    else
    {
        g(r...);
    }
}
```

## <a name="see-also"></a>Zobacz też

[Instrukcje wyboru](../cpp/selection-statements-cpp.md)\
[Służąc](../cpp/keywords-cpp.md)\
[`switch` Instrukcja (C++)](../cpp/switch-statement-cpp.md)
