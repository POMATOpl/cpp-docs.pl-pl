---
description: Dowiedz się więcej na temat operatorów języka C
title: Operatory języka C
ms.date: 06/14/2018
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
ms.openlocfilehash: 9e7e3a041b271117c0a7caeaa1ee97d88b4c037e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300258"
---
# <a name="c-operators"></a>Operatory języka C

Operatory języka C są podzbiorem [wbudowanych operatorów C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md).

Istnieją trzy typy operatorów. Wyrażenie jednoargumentowe składa się z operatora jednoargumentowego, który jest poprzedzony operandem lub **`sizeof`** słowa kluczowego, po którym następuje wyrażenie. Wyrażenie może być nazwą zmiennej lub wyrażeniem rzutowania. Jeśli wyrażenie jest wyrażeniem rzutowania, musi być ujęte w nawiasy. Wyrażenie binarne składa się z dwóch operandów przyłączonych do operatora binarnego. Wyrażenie Trzyelementowy składa się z trzech operandów przyłączonych do operatora wyrażenia warunkowego.

C zawiera następujące operatory jednoargumentowe:

|Symbol|Nazwa|
|------------|----------|
|**-** **~** **!**|Operatory negacji i uzupełniania|
|**&#42;****&**|Operatory pośrednie i „address-of”|
|**`sizeof`**|Size — operator|
|**+**|Jednoargumentowy operator plus|
|**++** **--**|Operatory przyrostu i zmniejszania jednoargumentowego|

Operatory binarne są kojarzone od lewej do prawej. C zawiera następujące operatory binarne:

|Symbol|Nazwa|
|------------|----------|
|**&#42;** **/****%**|Operatory multiplikatywne|
|**+** **-**|Operatory addytywne|
|**\<\<** **>>**|Operatory przesunięcia|
|**\<** **>****\<=** **>=** **==** **!=**|Operatory relacyjne|
|**&****&#124;****^**|Operatory bitowe|
|**&&****&#124;&#124;**|Operatory logiczne|
|**,**|Operator obliczania sekwencyjnego|

Operator Base (**: >**) obsługiwany przez poprzednie wersje kompilatora 16-bitowego c firmy Microsoft został opisany w artykule [składnia składni języka c](../c-language/c-language-syntax-summary.md).

Operator wyrażenia warunkowego ma niższy priorytet niż wyrażenia binarne i różni się od nich w prawidłowym skojarzeniu.

Wyrażenia z operatorami zawierają również wyrażenia przypisania, które używają jednoargumentowego lub binarnego operatora przypisania. Operatory przypisania jednoargumentowego to operatory przyrostu ( **++** ) i zmniejszania ( **--** ); operatory przypisania binarnego to operator prostego przypisania ( **=** ) i operatory przypisania złożonego. Każdy operator przypisania złożonego jest kombinacją innego operatora binarnego z operatorem przypisania prostego.

## <a name="see-also"></a>Zobacz też

- [Wyrażenia i przydziały](../c-language/expressions-and-assignments.md)
