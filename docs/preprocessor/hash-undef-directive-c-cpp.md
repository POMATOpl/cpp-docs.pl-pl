---
description: 'Dowiedz się więcej o: #undef dyrektywie (C/C++)'
title: '#undef, dyrektywa (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 20dfd1d0b26f18a26e7ad407704d6cb0ffd563bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300440"
---
# <a name="undef-directive-cc"></a>#undef — dyrektywa (C/C++)

Usuwa (anuluje) nazwę utworzoną wcześniej przy użyciu `#define` .

## <a name="syntax"></a>Składnia

>  *Identyfikator* #undef

## <a name="remarks"></a>Uwagi

Dyrektywa **#undef** usuwa bieżącą definicję *identyfikatora*. W związku z tym kolejne wystąpienia *identyfikatora* są ignorowane przez preprocesor. Aby usunąć definicję makra przy użyciu **#undef**, należy podać tylko *Identyfikator* makra, a nie listę parametrów.

Można również zastosować dyrektywę **#undef** do identyfikatora, który nie zawiera poprzedniej definicji. Dzięki temu identyfikator jest niezdefiniowany. Zastępowanie makra nie jest wykonywane w instrukcjach **#undef** .

Dyrektywa **#undef** jest zazwyczaj sparowana z dyrektywą w `#define` celu utworzenia regionu w programie źródłowym, w którym identyfikator ma specjalne znaczenie. Na przykład konkretna funkcja programu źródłowego może używać stałych manifestu do definiowania wartości specyficznych dla środowiska, które nie wpływają na resztę programu. Dyrektywa **#undef** współpracuje również z `#if` dyrektywą w celu kontrolowania warunkowej kompilacji programu źródłowego. Aby uzyskać więcej informacji, zobacz [dyrektywy #if, #elif, #else i #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

W poniższym przykładzie dyrektywa **#undef** usuwa definicje stałej symbolicznej i makra. Należy zauważyć, że jest określony tylko identyfikator makra.

```C
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Specyficzne dla firmy Microsoft**

Makra mogą być niezdefiniowane z wiersza polecenia przy użyciu `/U` opcji, a następnie nazwy makr, które mają być niezdefiniowane. Efekt wystawienia tego polecenia jest równoważny sekwencji `#undef` instrukcji *nazwy makra* na początku pliku.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Dyrektywy preprocesora](../preprocessor/preprocessor-directives.md)
