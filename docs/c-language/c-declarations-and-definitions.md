---
description: 'Dowiedz się więcej na temat: deklaracje i definicje języka C'
title: Deklaracje i definicje języka C
ms.date: 11/04/2016
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
ms.openlocfilehash: dac53ac203c8e58e3af87e4869983c0443ffb092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254316"
---
# <a name="c-declarations-and-definitions"></a>Deklaracje i definicje języka C

"Deklaracja" ustanawia skojarzenie między określoną zmienną, funkcją lub typem a jej atrybutami. [Przegląd deklaracji](../c-language/overview-of-declarations.md) zawiera składnię ANSI dla `declaration` nieterminalu. Deklaracja określa również, gdzie i kiedy można uzyskać dostęp do identyfikatora ("powiązanie" identyfikatora). Zobacz [okres istnienia, zakres, widoczność i powiązania](../c-language/lifetime-scope-visibility-and-linkage.md) , aby uzyskać informacje dotyczące powiązania.

"Definicja" zmiennej ustanawia te same skojarzenia jak Deklaracja, ale również powoduje przydzielenie magazynu dla zmiennej.

Na przykład,, `main` `find` , i `count` `var` `val` zmienne i są zdefiniowane w jednym pliku źródłowym, w następującej kolejności:

```
int main() {}

int var = 0;
double val[MAXVAL];
char find( fileptr ) {}
int count( double f ) {}
```

Zmienne `var` i `val` mogą być używane w `find` `count` funkcjach i; dalsze deklaracje nie są zbędne. Ale te nazwy nie są widoczne (nie można uzyskać do nich dostępu) w `main` .

## <a name="see-also"></a>Zobacz też

[Pliki źródłowe i programy źródłowe](../c-language/source-files-and-source-programs.md)
