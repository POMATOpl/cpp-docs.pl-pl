---
description: 'Dowiedz się więcej na temat: korzystanie z CObject'
title: Używanie obiektu CObject
ms.date: 11/04/2016
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
ms.openlocfilehash: 203e2a498f787f23de21db4469e5cdd7c5543761
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271645"
---
# <a name="using-cobject"></a>Używanie obiektu CObject

[CObject](../mfc/reference/cobject-class.md) jest główną klasą bazową dla większości Biblioteka MFC (MFC). `CObject`Klasa zawiera wiele użytecznych funkcji, które można chcieć uwzględnić w swoich obiektach programu, w tym obsługę serializacji, informacje o klasie czasu wykonywania i dane wyjściowe diagnostyki obiektów. Jeśli klasa jest pochodną `CObject` , Klasa może wykorzystać te `CObject` funkcje.

## <a name="what-do-you-want-to-do"></a>Co chcesz zrobić

- [Utwórz klasę z CObject](../mfc/deriving-a-class-from-cobject.md)

- [Dodawanie obsługi informacji o klasie czasu wykonywania, tworzenia dynamicznego i serializacji do klasy pochodnej](../mfc/specifying-levels-of-functionality.md)

- [Dostęp do informacji o klasie czasu wykonywania](../mfc/accessing-run-time-class-information.md)

- [Dynamiczne tworzenie obiektów](../mfc/dynamic-object-creation.md)

- [Zrzuć dane obiektu do celów diagnostycznych](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))

- Sprawdź poprawność stanu wewnętrznego obiektu (zobacz [MFC ASSERT_VALID i CObject:: AssertValid](reference/diagnostic-services.md#assert_valid))

- [Zaserializacji klasy do magazynu trwałego](../mfc/serialization-in-mfc.md)

- Zobacz listę [często zadawanych pytań CObject](../mfc/cobject-class-frequently-asked-questions.md)

## <a name="see-also"></a>Zobacz też

[Pojęcia](../mfc/mfc-concepts.md)<br/>
[Ogólne tematy dotyczące MFC](../mfc/general-mfc-topics.md)<br/>
[CRuntimeClass, struktura](../mfc/reference/cruntimeclass-structure.md)<br/>
[Files](../mfc/files-in-mfc.md)<br/>
[Serializacja](../mfc/serialization-in-mfc.md)
