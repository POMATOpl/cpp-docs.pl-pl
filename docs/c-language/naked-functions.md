---
description: 'Dowiedz się więcej o: funkcjach niezwiązanych'
title: Funkcje Naked
ms.date: 11/04/2016
helpviewer_keywords:
- naked functions
- functions [C++], naked
- prolog code
- epilog code
ms.assetid: 2543c8af-00d4-4a2a-8a87-e746da1f9929
ms.openlocfilehash: 1cea9bf2497a14bc7007f97b2c3db68eafc15059
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243357"
---
# <a name="naked-functions"></a>Funkcje Naked

**Specyficzne dla firmy Microsoft**

`naked`Atrybut klasy magazynowania to specyficzne dla firmy Microsoft rozszerzenie języka C. W przypadku funkcji zadeklarowanych z `naked` atrybutem klasy magazynowania kompilator generuje kod bez kodu prologu i epilogu. Za pomocą tej funkcji można napisać własne sekwencje kodu prologu/epilogu przy użyciu kodu asemblera wbudowanego. Wbudowane funkcje są szczególnie przydatne podczas pisania sterowników urządzeń wirtualnych.

Ponieważ `naked` atrybut ma zastosowanie tylko do definicji funkcji i nie jest modyfikatorem typu, funkcja bezużytecznych użyj składni atrybutów rozszerzonych, opisanej w [rozszerzonym Storage-Class atrybutów](../c-language/c-extended-storage-class-attributes.md).

W poniższym przykładzie zdefiniowano funkcję z `naked` atrybutem:

```
__declspec( naked ) int func( formal_parameters )
{
   /* Function body */
}
```

Lub alternatywnie:

```
#define Naked   __declspec( naked )

Naked int func( formal_parameters )
{
   /* Function body */
}
```

Ten `naked` atrybut ma wpływ tylko na charakter generowania kodu kompilatora dla sekwencji Prolog i epilogu funkcji. Nie ma to wpływu na kod, który jest generowany do wywoływania takich funkcji. W ten sposób `naked` atrybut nie jest uważany za część typu funkcji, a wskaźniki funkcji nie mogą mieć `naked` atrybutu. Ponadto `naked` nie można zastosować atrybutu do definicji danych. Na przykład poniższy kod generuje błędy:

```
__declspec( naked ) int i;  /* Error--naked attribute not */
                            /* permitted on data declarations. */
```

`naked`Atrybut jest istotny tylko dla definicji funkcji i nie może być określony w prototypie funkcji. Następująca deklaracja generuje błąd kompilatora:

```
__declspec( naked ) int func();   /* Error--naked attribute not */
                     /* permitted on function declarations.    */   \
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Definicje funkcji języka C](../c-language/c-function-definitions.md)
