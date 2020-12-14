---
description: 'Dowiedz się więcej o: makra (C/C++)'
title: Makra (C/C++)
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
ms.openlocfilehash: 460fd993ae27ab2603c3d2f832481c07713f4f98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333417"
---
# <a name="macros-cc"></a>Makra (C/C++)

Preprocesor rozszerza makra we wszystkich wierszach z wyjątkiem *dyrektyw preprocesora*, wierszy, które mają **#** jako pierwszy znak niebędący odstępem. Rozszerza on makra w części niektórych dyrektyw, które nie są pomijane w ramach kompilacji warunkowej. *Dyrektywy kompilacji warunkowej* umożliwiają pomijanie kompilacji części pliku źródłowego. Testuje stałe wyrażenie lub identyfikator, aby określić, które bloki tekstu należy przekazać do kompilatora, i które mają zostać usunięte z pliku źródłowego podczas przetwarzania wstępnego.

Dyrektywa `#define` jest zazwyczaj używana do kojarzenia znaczących identyfikatorów ze stałymi, słowami kluczowymi i powszechnie używanymi instrukcjami lub wyrażeniami. Identyfikatory reprezentujące stałe są czasami nazywane *symbolicznymi* lub *stałymi manifestami*. Identyfikatory, które reprezentują instrukcje lub wyrażenia, są nazywane *makrami*. W tej dokumentacji preprocesora, używany jest jedynie termin „makro”.

Gdy nazwa makra jest rozpoznawana w tekście źródłowym programu lub w argumentach niektórych innych poleceń preprocesora, jest traktowana jako wywołanie do tego makra. Nazwa makra jest zamieniana przez kopię ciała makra. Jeśli makro akceptuje argumenty, rzeczywiste argumenty następujące po nazwie makra są zastępowane parametrami formalnymi w ciele makra. Proces zamiany wywołania makra z przetworzoną kopią treści jest nazywany *rozwinięciem* wywołania makra.

W praktyce, istnieją dwa typy makr. Makra *podobne do obiektów* nie przyjmują argumentów. Makra *podobne do funkcji* można definiować w celu akceptowania argumentów, tak aby wyglądały i działały jak wywołania funkcji. Ponieważ makra nie generują rzeczywistych wywołań funkcji, czasami można sprawiać, że programy działają szybciej przez zastępowanie wywołań funkcji za pomocą makr. (W języku C++ funkcje wbudowane są często preferowanymi metodami). Jednak makra mogą tworzyć problemy, jeśli nie są zdefiniowane i używane z opieką. Może zaistnieć potrzeba użycia nawiasów w definicji makra z argumentami, aby zachować właściwą kolejność w wyrażeniu. Ponadto, makra mogą nie obsługiwać poprawnie wyrażeń z efektami ubocznymi. Aby uzyskać więcej informacji, zobacz `getrandom` przykład w [dyrektywie #define](../preprocessor/hash-define-directive-c-cpp.md).

Po zdefiniowaniu makra nie można przedefiniować go na inną wartość bez wcześniejszego usunięcia oryginalnej definicji. Jednakże, można ponownie zdefiniować makro z identyczną definicją. W ten sam sposób definicja może pojawić się więcej niż jeden raz w programie.

`#undef`Dyrektywa usuwa definicję makra. Po usunięciu definicji, można ponownie zdefiniować makro pod inną wartością. [Dyrektywa #define](../preprocessor/hash-define-directive-c-cpp.md) i dyrektywa [#undef](../preprocessor/hash-undef-directive-c-cpp.md) omawiają `#define` `#undef` odpowiednio dyrektywy i.

Aby uzyskać więcej informacji, zobacz,

- [Makra i język C++](../preprocessor/macros-and-cpp.md)

- [Makra wariadyczne](../preprocessor/variadic-macros.md)

- [Wstępnie zdefiniowane makra](../preprocessor/predefined-macros.md)

## <a name="see-also"></a>Zobacz też

[Odwołania preprocesora języka C/C++](../preprocessor/c-cpp-preprocessor-reference.md)
