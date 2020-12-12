---
description: 'Dowiedz się więcej o: instrukcja złożona (C)'
title: Instrukcja złożona (C)
ms.date: 11/04/2016
helpviewer_keywords:
- compound statements
- statements, compound
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
ms.openlocfilehash: b4c1ee15bc081c34cbc12bfe2c3e997ca181b7be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293446"
---
# <a name="compound-statement-c"></a>Instrukcja złożona (C)

Instrukcja złożona (nazywana również "blokiem") jest zwykle wyświetlana jako treść innej instrukcji, takiej jak **`if`** instrukcja. [Deklaracje i typy](../c-language/declarations-and-types.md) opisują formę i znaczenie deklaracji, które mogą być wyświetlane w nagłówku złożonej instrukcji.

## <a name="syntax"></a>Składnia

*instrukcja złożona*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *deklaracji*<sub>opt</sub> *instrukcji SELECT-list*<sub>opt</sub> **}**

*Deklaracja-lista*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*oświadczeń*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Deklaracja *listy deklaracji* 

*Lista instrukcji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Merge*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*instrukcja-list —* *instrukcja*

Jeśli istnieją deklaracje, muszą one znajdować się przed wszelkimi instrukcjami. Zakres każdego identyfikatora zadeklarowanego na początku złożonej instrukcji rozciąga się od punktu deklaracji do końca bloku. Jest on widoczny w bloku, chyba że deklaracja tego samego identyfikatora istnieje w bloku wewnętrznym.

Identyfikatory w instrukcji złożonej są przypuszczalne **`auto`** , chyba że jawnie zadeklarowano inaczej przy użyciu **`register`** , **`static`** , lub **`extern`** , z wyjątkiem funkcji, które mogą być **`extern`** . Można opuścić **`extern`** specyfikator w deklaracjach funkcji, a funkcja nadal będzie **`extern`** .

Magazyn nie jest przydzielony i Inicjalizacja jest niedozwolona, jeśli zmienna lub funkcja jest zadeklarowana w instrukcji złożonej z klasą magazynu **`extern`** . Deklaracja odnosi się do zmiennej zewnętrznej lub funkcji zdefiniowanej w innym miejscu.

Zmienne zadeklarowane w bloku ze **`auto`** **`register`** słowem kluczowym or są ponownie przydzieloną i, w razie potrzeby, inicjowane przy każdym wprowadzeniu złożonej instrukcji. Te zmienne nie są zdefiniowane po zakończeniu złożonej instrukcji. Jeśli zmienna zadeklarowana wewnątrz bloku ma **`static`** atrybut, zmienna jest inicjowana po rozpoczęciu wykonywania programu i utrzymuje jego wartość w całym programie. Zobacz [klasy magazynu](../c-language/c-storage-classes.md) , aby uzyskać informacje o programie **`static`** .

Ten przykład ilustruje złożone instrukcje:

```C
if ( i > 0 )
{
    line[i] = x;
    x++;
    i--;
}
```

W tym przykładzie, jeśli `i` jest większa niż 0, wszystkie instrukcje wewnątrz instrukcji złożonej są wykonywane w kolejności.

## <a name="see-also"></a>Zobacz też

[Instrukcje](../c-language/statements-c.md)
