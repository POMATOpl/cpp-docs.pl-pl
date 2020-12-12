---
description: 'Dowiedz się więcej o: `switch` instrukcja (C)'
title: switch  Instrukcja (C)
ms.date: 04/25/2020
f1_keywords:
- switch
helpviewer_keywords:
- switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
no-loc:
- switch
- case
- default
- break
ms.openlocfilehash: f6089505ac47c657e151a60d6061a79ee0fd3cb8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114445"
---
# <a name="no-locswitch-statement-c"></a>`switch` Instrukcja (C)

**`switch`** Instrukcje i **`case`** ułatwiają kontrolę złożonych operacji warunkowych i rozgałęzień. **`switch`** Instrukcja przekazuje formant do instrukcji w jej treści.

## <a name="syntax"></a>Składnia

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`switch (`**&nbsp;*`expression`* &nbsp;**`)`**&nbsp;*`statement`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`case`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`default`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>Uwagi

**`switch`** Instrukcja powoduje, że kontrolka jest przekazywana do jednego *`labeled-statement`* w jego treści instrukcji, w zależności od wartości *`expression`* .

Wartości *`expression`* i każdego z nich *`constant-expression`* muszą mieć typ całkowity. A *`constant-expression`* musi mieć niejednoznaczną stałą wartość całkowitą w czasie kompilacji.

Kontrolka przechodzi do **`case`** instrukcji, której *`constant-expression`* wartość jest zgodna z wartością *`expression`* . **`switch`** Instrukcja może zawierać dowolną liczbę **`case`** wystąpień. Jednak żadne dwie *`constant-expression`* wartości w tej samej **`switch`** instrukcji nie mogą mieć tej samej wartości. Wykonywanie **`switch`** treści instrukcji rozpoczyna się od pierwszej instrukcji w lub po dopasowaniu *`labeled-statement`* . Wykonywanie przechodzi do końca treści lub do momentu, aż **`break`** instrukcja przeniesie kontrolę z treści.

Użycie **`switch`** instrukcji zwykle wygląda następująco:

```C
switch ( expression )
{
    // declarations
    // . . .
    case constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        break;
    default:
        // statements executed if expression does not equal
        // any case constant_expression
}
```

Możesz użyć instrukcji, **`break`** Aby zakończyć przetwarzanie konkretnej instrukcji oznaczonej etykietą w **`switch`** instrukcji. Oddziały IT do końca **`switch`** instrukcji. Bez **`break`** , program przechodzi do następnej instrukcji oznaczonej etykietą, wykonując instrukcje do momentu **`break`** osiągnięcia lub zakończenia instrukcji. Kontynuacja może być pożądana w niektórych sytuacjach.

**`default`** Instrukcja jest wykonywana, jeśli żadna **`case`** *`constant-expression`* wartość nie jest równa wartości *`expression`* . Jeśli nie ma żadnej **`default`** instrukcji i nie **`case`** znaleziono dopasowania, żadna z instrukcji w treści nie zostanie **`switch`** wykonana. Może istnieć co najwyżej jedna **`default`** instrukcja. **`default`** Instrukcja nie musi znajdować się na końcu. Może pojawić się w dowolnym miejscu w treści **`switch`** instrukcji. **`case`** Etykieta lub **`default`** może wystąpić tylko wewnątrz **`switch`** instrukcji.

Typ **`switch`** *`expression`* i **`case`** *`constant-expression`* musi być liczbą całkowitą. Wartość każdego z nich **`case`** *`constant-expression`* musi być unikatowa w treści instrukcji.

**`case`** Etykiety i **`default`** **`switch`** treści instrukcji są znaczące tylko w teście wstępnym, który określa, gdzie wykonywanie zostanie rozpoczęte w treści instrukcji. **`switch`** instrukcje mogą być zagnieżdżane. Wszystkie zmienne statyczne są inicjowane przed wykonaniem w **`switch`** instrukcjach.

> [!NOTE]
> Deklaracje mogą pojawić się w nagłówku złożonej instrukcji tworzącej **`switch`** treść, ale inicjalizacje zawarte w deklaracjach nie są wykonywane. **`switch`** Instrukcja przekazuje bezpośrednio formant do instrukcji wykonywalnej w treści, pomijając wiersze zawierające inicjalizacje.

W poniższych przykładach przedstawiono **`switch`** instrukcje:

```C
switch( c )
{
    case 'A':
        capital_a++;
    case 'a':
        letter_a++;
    default :
        total++;
}
```

Wszystkie trzy instrukcje **`switch`** treści w tym przykładzie są wykonywane `c` , jeśli jest równe `'A'` , ponieważ **`break`** instrukcja nie pojawia się przed poniższymi instrukcjami **`case`** . Sterowanie wykonywaniem jest przenoszone do pierwszej instrukcji ( `capital_a++;` ) i kontynuuje w pozostałej części treści. Jeśli `c` wartość jest równa `'a'` `letter_a` i jest `total` zwiększana. `total`Wartość jest zwiększana tylko wtedy `c` , gdy nie jest równa `'A'` lub `'a'` .

```C
switch( i )
{
    case -1:
        n++;
        break;
    case 0 :
        z++;
        break;
    case 1 :
        p++;
        break;
}
```

W tym przykładzie instrukcja jest **`break`** zgodna z każdą instrukcją w **`switch`** treści. **`break`** Instrukcja wymusza wyjście z treści instrukcji po wykonaniu jednej instrukcji. Jeśli `i` wartość jest równa-1, tylko `n` jest zwiększana. **`break`** Poniższa instrukcja `n++;` powoduje, że kontrola wykonywania przeszedł z treści instrukcji, pomijając pozostałe instrukcje. Podobnie, jeśli `i` wartość jest równa 0, tylko `z` jest zwiększana `i` . Jeśli wartość jest równa 1, tylko `p` jest zwiększana. Instrukcja Final **`break`** nie jest absolutnie konieczna, ponieważ kontrolka przechodzi poza treść na końcu złożonej instrukcji. Jest on uwzględniany w celu zapewnienia spójności.

Pojedyncza instrukcja może zawierać wiele **`case`** etykiet, jak pokazano w poniższym przykładzie:

```C
switch( c )
{
    case 'a' :
    case 'b' :
    case 'c' :
    case 'd' :
    case 'e' :
    case 'f' :  convert_hex(c);
}
```

W tym przykładzie, jeśli *wyrażenie stałe* jest równe dowolnej literze między `'a'` i `'f'` , `convert_hex` Funkcja jest wywoływana.

### <a name="microsoft-specific"></a>specyficzne dla firmy Microsoft

Microsoft C nie ogranicza liczby **`case`** wartości w **`switch`** instrukcji. Liczba jest ograniczona tylko przez dostępną pamięć. ANSI C wymaga co najmniej 257 **`case`** etykiet w **`switch`** instrukcji.

W default przypadku oprogramowania Microsoft C są włączone rozszerzenia Microsoft. Aby wyłączyć te rozszerzenia, użyj opcji kompilatora [/za](../build/reference/za-ze-disable-language-extensions.md) .

## <a name="see-also"></a>Zobacz też

[switch Instrukcja (C++)](../cpp/switch-statement-cpp.md)
