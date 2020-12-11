---
description: 'Dowiedz się więcej na temat: opis cech okna'
title: Cechy okna ATL
ms.date: 11/04/2016
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
ms.openlocfilehash: a42ef66afe09e0e528f05419799dce48c43b1bbf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157298"
---
# <a name="understanding-window-traits"></a>Informacje o cechach okna

Klasy cech okna zapewniają prostą metodę standaryzacji stylów używanych do tworzenia obiektu okna ATL. Cechy okna są akceptowane jako parametry szablonu według [CWindowImpl](../atl/reference/cwindowimpl-class.md) i innych klas okien ATL jako sposób udostępniania domyślnych stylów okna na poziomie klasy.

Jeśli twórca wystąpienia okna nie udostępnia stylów jawnie w wywołaniu [tworzenia](../atl/reference/cwindowimpl-class.md#create), można użyć klasy cech, aby upewnić się, że okno jest nadal utworzone przy użyciu poprawnych stylów. Można nawet upewnić się, że niektóre style są ustawione dla wszystkich wystąpień tej klasy okna, jednocześnie pozwalając na ustawienie innych stylów dla poszczególnych wystąpień.

## <a name="atl-window-traits-templates"></a>Szablony cech okna ATL

ATL oferuje dwa szablony cech okna, które umożliwiają ustawianie domyślnych stylów w czasie kompilacji przy użyciu ich parametrów szablonu.

|Klasa|Opis|
|-----------|-----------------|
|[CWinTraits](../atl/reference/cwintraits-class.md)|Użyj tego szablonu, jeśli chcesz podać domyślne style okna, które będą używane tylko wtedy, gdy nie określono innych stylów w wywołaniu `Create` . Style podane w czasie wykonywania mają pierwszeństwo przed stylami ustawionymi w czasie kompilacji.|
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Użyj tej klasy, aby określić style, które muszą być zawsze ustawione dla klasy Window. Style podane w czasie wykonywania są łączone z stylami ustawionymi w czasie kompilacji przy użyciu operatora bitowego or.|

Oprócz tych szablonów ATL udostępnia wiele wstępnie zdefiniowanych specjalizacji `CWinTraits` szablonu dla często używanych kombinacji stylów okna. Aby uzyskać szczegółowe informacje, zobacz dokumentację referencyjną [CWinTraits](../atl/reference/cwintraits-class.md) .

## <a name="custom-window-traits"></a>Cechy okna niestandardowego

W mało prawdopodobnym przypadku specjalizacji jednego z szablonów dostarczonych przez ATL nie jest wystarczające i należy utworzyć własną klasę cech, wystarczy utworzyć klasę, która implementuje dwie funkcje statyczne: `GetWndStyle` i `GetWndStyleEx` :

[!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]

Każda z tych funkcji będzie przekazywać pewną wartość stylu w czasie wykonywania, przy użyciu której można utworzyć nową wartość stylu. Jeśli Klasa cech okna jest używana jako argument szablonu dla klasy okna ATL, wartości stylu przekazane do tych funkcji statycznych będą dowolnie przekazane jako argumenty stylu do [utworzenia](../atl/reference/cwindowimpl-class.md#create).

## <a name="see-also"></a>Zobacz też

[Klasy okien](../atl/atl-window-classes.md)
