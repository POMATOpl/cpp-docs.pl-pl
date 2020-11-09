---
title: Kwalifikatory typów
description: Opisuje Kwalifikatory typu języka C używanego w kompilatorze Microsoft Visual C
ms.date: 11/6/2020
helpviewer_keywords:
- volatile keyword [C], type qualifier
- type qualifiers
- volatile keyword [C]
- qualifiers for types
- const keyword [C]
- memory, access using volatile
- volatile keyword [C], type specifier
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
ms.openlocfilehash: dd36aeb5d142eebbd6e4a339fe6c18925a6fd45a
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381613"
---
# <a name="type-qualifiers"></a>Kwalifikatory typów

Kwalifikatory typu dają jedną z dwóch właściwości do identyfikatora. **`const`** Kwalifikator typu deklaruje obiekt jako niemodyfikowalny. **`volatile`** Kwalifikator typu deklaruje element, którego wartość może być słusznie zmieniona przez coś poza formantem programu, w którym występuje, na przykład współbieżnie wykonywany wątek.

Kwalifikatory typu,, **`const`** **`restrict`** , i **`volatile`** , mogą występować tylko raz w deklaracji. Kwalifikatory typu mogą występować z dowolnym specyfikatorem typu; nie mogą jednak występować po pierwszym przecinku w deklaracji wielu elementów. Na przykład następujące deklaracje są dozwolone:

```c
typedef volatile int VI;
const int ci;
```

Te deklaracje nie są dozwolone:

```c
typedef int *i, volatile *vi;
float f, const cf;
```

Kwalifikatory typu są istotne tylko podczas uzyskiwania dostępu do identyfikatorów jako wartości l w wyrażeniach. Aby uzyskać informacje na temat wartości l i wyrażeń, zobacz [wyrażenia wartości l i R](../c-language/l-value-and-r-value-expressions.md) .

## <a name="syntax"></a>Składnia

*`type-qualifier`* :\
&emsp;**`const`**\
&emsp;**`restrict`**\
&emsp;**`volatile`**

## <a name="const-and-volatile"></a>`const` i `volatile`

Poniżej przedstawiono prawne **`const`** i **`volatile`** deklaracje:

```c
int const *p_ci;      // Pointer to constant int
int const (*p_ci);   // Pointer to constant int
int *const cp_i;     // Constant pointer to int
int (*const cp_i);   // Constant pointer to int
int volatile vint;     // Volatile integer
```

Jeśli specyfikacja typu tablicy zawiera kwalifikatory typu, element jest kwalifikowany, a nie typ tablicy. Jeśli specyfikacja typu funkcji zawiera kwalifikatory, zachowanie jest niezdefiniowane. **`volatile`** i **`const`** nie ma wpływu na zakres wartości lub właściwości arytmetyczne obiektu.

- **`const`** Słowo kluczowe może służyć do modyfikowania dowolnego typu podstawowego lub agregacji lub wskaźnika do obiektu dowolnego typu lub **`typedef`** . Jeśli element jest zadeklarowany tylko przy użyciu **`const`** kwalifikatora typu, jego typ jest traktowany jako **const int**. **`const`** Zmienna może być inicjowana lub może zostać umieszczona w regionie magazynu tylko do odczytu. **`const`** Słowo kluczowe jest przydatne do deklarowania wskaźników do **`const`** , ponieważ wymaga, aby funkcja nie zmieniła wskaźnika w jakikolwiek sposób.

- Kompilator zakłada, że w dowolnym momencie w programie **`volatile`** zmienna może być dostępna przez nieznany proces, który używa lub modyfikuje jego wartość. Bez względu na optymalizacje określone w wierszu polecenia, kod dla każdego przypisania lub odwołania do **`volatile`** zmiennej musi być wygenerowany, nawet jeśli wydaje się, że nie ma żadnego wpływu.

Jeśli **`volatile`** jest używany samodzielnie, **`int`** przyjmowana jest wartość. **`volatile`** Specyfikatora typu można użyć, aby zapewnić niezawodny dostęp do specjalnych lokalizacji pamięci. Używany **`volatile`** z obiektami danych, które mogą być dostępne lub modyfikowane przez programy obsługi sygnałów przez współbieżnie wykonywane programy lub przez specjalny sprzęt, taki jak rejestry kontroli we/wy mapowane na pamięć. Możesz zadeklarować zmienną jako **`volatile`** dla swojego okresu istnienia lub można rzutować pojedyncze odwołanie na nie **`volatile`** .

- Element może być zarówno **`const`** , jak i **`volatile`** , w tym przypadku nie można go zmodyfikować w sposób wiarygodny przez swój własny program, ale może zostać zmodyfikowany przez proces asynchroniczny.
 
## `restrict`

**`restrict`** Kwalifikator typu wprowadzony w C99 można zastosować do deklaracji wskaźnika. Jest ono zgodne ze wskaźnikiem, a nie z tym, co wskazuje.

**`restrict`** jest wskazówką optymalizacji do kompilatora, że żaden inny wskaźnik w bieżącym zakresie nie odwołuje się do tej samej lokalizacji pamięci. Oznacza to, że do uzyskania dostępu do obiektu w okresie istnienia wskaźnika jest używany tylko wskaźnik lub wartość pochodna (na przykład wskaźnik + 1). Dzięki temu kompilator tworzy bardziej zoptymalizowany kod. Język C++ ma odpowiedni mechanizm, [`__restrict`](../cpp/extension-restrict.md)

Pamiętaj, że **`restrict`** jest to umowa między ty i kompilatorem. Jeśli utworzysz alias wskaźnika oznaczonego za pomocą **`restrict`** , wynik jest niezdefiniowany.

Oto przykład, który używa **`restrict`** :

```c
void test(int* restrict first, int* restrict second, int* val)
{
    *first += *val;
    *second += *val;
}

int main()
{
    int i = 1, j = 2, k = 3;
    test(&i, &j, &k);

    return 0;
}

// Marking union members restrict tells the compiler that
// only z.x or z.y will be accessed in any scope, which allows
// the compiler to optimize access to the members.
union z 
{
    int* restrict x;
    double* restrict y;
};
```

## <a name="see-also"></a>Zobacz też

[`/std` (Określ wersję standardową języka)](../build/reference/std-specify-language-standard-version.md)\
[Deklaracje i typy](../c-language/declarations-and-types.md)
