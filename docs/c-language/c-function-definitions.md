---
description: Dowiedz się więcej na temat definicji funkcji języka C
title: Definicje funkcji języka C
ms.date: 11/04/2016
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
ms.openlocfilehash: 9e664224608a741897bf8ae6208a0d9011cdb3c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296930"
---
# <a name="c-function-definitions"></a>Definicje funkcji języka C

Definicja funkcji określa nazwę funkcji, typy i liczbę parametrów, które oczekuje na odebranie, i typ zwracany. Definicja funkcji zawiera również treść funkcji z deklaracjami zmiennych lokalnych i instrukcji, które określają działanie funkcji.

## <a name="syntax"></a>Składnia

*Jednostka translation*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deklaracja zewnętrzna* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deklaracja zewnętrzna* *jednostki tłumaczenia*

*deklaracja zewnętrzna*:/ \* dozwolone tylko w zewnętrznym zakresie (pliku) \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Definicja funkcji*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*oświadczeń*

*definicja funkcji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deklaracja-specyfikators*<sub>opt</sub> *Attribute-SEQ*<sub>opt</sub> *deklarator* *deklaracji-list*<sub>opt</sub> *złożone-instrukcja*

/\**atrybut-seq* jest specyficzny dla firmy Microsoft\*/

Parametry prototypu:

*specyfikatory deklaracji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deklaracja* *specyfikatora klasy magazynu* —<sub>wybór</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;Deklaracja *specyfikatora typu* *— wybór specyfikatorów*<sub></sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;Deklaracja *kwalifikatora typu* *— wybór specyfikatorów*<sub></sub>

*Deklaracja-lista*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*oświadczeń*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Deklaracja *listy deklaracji* 

*deklarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<sub>wybór</sub> wskaźnika *Direct-deklarator*

*Direct-deklarator*:/ \* A funkcja deklarator \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-deklarator***(***Typ parametru-list***)**  / \* New-Style deklarator      \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-deklarator***(** nieważność *listy identyfikatorów*<sub></sub> **)**  / \* — przestarzałe style deklarator    \*/

Lista parametrów w definicji używa następującej składni:

*Typ parametru-list*:/ \* Lista parametrów \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Lista parametrów* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Lista parametrów* **,...**

*Lista parametrów*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deklaracja parametru*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Lista parametrów* **,**  *Deklaracja parametru*

*Deklaracja parametru*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*specyfikatory deklaracji* *deklarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;abstrakcyjne *specyfikatory deklaracji* *-deklarator*<sub>opt</sub>

Lista parametrów w definicji funkcji starego stylu używa następującej składni:

*Identyfikator-list*:/ \* używany w definicjach i deklaracjach funkcji przestarzałego stylu \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identyfikatora*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Identyfikator — lista* **,**  *Identyfikator*

Składnia dla treści funkcji jest następująca:

*instrukcja złożona*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *deklaracji*<sub>opt</sub> *instrukcji SELECT-list*<sub>opt</sub> **}**

Jedyne specyfikatory klasy magazynu, które mogą modyfikować deklarację funkcji **`extern`** , są i **`static`** . **`extern`** Specyfikator oznacza, że do funkcji można odwoływać się z innych plików, to oznacza, że nazwa funkcji zostanie wyeksportowana do konsolidatora. **`static`** Specyfikator oznacza, że nie można odwoływać się do funkcji z innych plików, to oznacza, że nazwa nie jest eksportowana przez konsolidator. Jeśli Klasa magazynu nie jest wyświetlana w definicji funkcji, **`extern`** przyjmuje się. W każdym przypadku funkcja jest zawsze widoczna z punktu definicji do końca pliku.

Opcjonalne *specyfikatory deklaracji* i obowiązkowe *deklarator* razem określają typ zwracany i nazwę funkcji. *Deklarator* to kombinacja identyfikatorów, która nazywa funkcję i nawiasy po nazwie funkcji. Opcjonalny *atrybut-seq* nieterminalu jest funkcją specyficzną dla firmy Microsoft zdefiniowaną w [atrybutach funkcji](../c-language/function-attributes.md).

*Direct-deklarator* (w składni *deklarator* ) określa nazwę zdefiniowanej funkcji i identyfikatory jej parametrów. Jeśli polecenie *Direct-deklarator* zawiera *listę typów parametrów*, lista określa typy wszystkich parametrów. Takie deklarator również służy jako prototyp funkcji dla późniejszego wywołania funkcji.

*Deklaracja* na *liście deklaracji* w definicjach funkcji nie może zawierać *specyfikatora klasy magazynu* innego niż **`register`** . *Specyfikator typu* w składni *specyfikatorów deklaracji* można pominąć tylko wtedy, gdy **`register`** Klasa magazynu jest określona dla wartości **`int`** typu.

*Instrukcja złożona* jest treścią funkcji zawierającą deklaracje zmiennej lokalnej, odwołania do elementów zadeklarowanych zewnętrznie i instrukcji.

Sekcje [atrybutów funkcji](../c-language/function-attributes.md), [klasy magazynu](../c-language/storage-class.md), [typu zwracanego](../c-language/return-type.md), [parametrów](../c-language/parameters.md)i [treści funkcji](../c-language/function-body.md) opisują składniki definicji funkcji szczegółowo.

## <a name="see-also"></a>Zobacz też

[Funkcje](../c-language/functions-c.md)
