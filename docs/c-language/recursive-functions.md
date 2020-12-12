---
description: 'Dowiedz się więcej o programie: funkcje cykliczne'
title: Funkcje rekursywne
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 4ea374b0831fdcfa8c63243c6e59c017856f047f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176213"
---
# <a name="recursive-functions"></a>Funkcje rekursywne

Każda funkcja w programie C może być wywoływana cyklicznie; oznacza to, że może wywoływać sam siebie. Liczba wywołań cyklicznych jest ograniczona do rozmiaru stosu. Aby uzyskać informacje na temat opcji konsolidatora, które ustawiają rozmiar stosu, zobacz opcję konsolidatora [ `/STACK` stosu](../build/reference/stack-stack-allocations.md) . Za każdym razem, gdy funkcja jest wywoływana, nowy magazyn jest przypisywany do parametrów i **`auto`** dla **`register`** zmiennych i, tak aby ich wartości w poprzednich, nieukończonych wywołaniach nie były zastępowane. Parametry są dostępne tylko bezpośrednio dla wystąpienia funkcji, w której zostały utworzone. Poprzednie parametry nie są bezpośrednio dostępne dla wynikający z tego, wystąpienia funkcji.

Należy zauważyć, że zmienne zadeklarowane za pomocą **`static`** magazynu nie wymagają nowego magazynu przy każdym wywołaniu cyklicznym. Ich magazyn istnieje na okres istnienia programu. Każde odwołanie do tej zmiennej uzyskuje dostęp do tego samego obszaru magazynu.

## <a name="example"></a>Przykład

Ten przykład ilustruje cykliczne wywołania:

```C
int factorial( int num );      /* Function prototype */

int main()
{
    int result, number;
    .
    .
    .
    result = factorial( number );
}

int factorial( int num )      /* Function definition */
{
    .
    .
    .
    if ( ( num > 0 ) || ( num <= 10 ) )
        return( num * factorial( num - 1 ) );
}
```

## <a name="see-also"></a>Zobacz też

[Wywołania funkcji](../c-language/function-calls.md)
