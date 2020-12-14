---
description: 'Dowiedz się więcej o programie: Określanie poziomów funkcjonalności'
title: Określanie poziomów funkcjonalności
ms.date: 11/06/2018
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
ms.openlocfilehash: 1b016cd5a41d3e09790f678a2d49d88df33d9782
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216850"
---
# <a name="specifying-levels-of-functionality"></a>Określanie poziomów funkcjonalności

W tym artykule opisano sposób dodawania następujących poziomów funkcjonalności do klasy pochodnej [CObject](../mfc/reference/cobject-class.md):

- Informacje o klasie czasu wykonywania

- Obsługa dynamicznego tworzenia

- Obsługa serializacji

Ogólny opis `CObject` funkcji znajduje się w artykule [pochodnym klasy z CObject](../mfc/deriving-a-class-from-cobject.md).

## <a name="to-add-run-time-class-information"></a>Aby dodać informacje o klasie czasu wykonywania

1. Utwórz klasę z `CObject` , zgodnie z opisem w artykule [pochodny klasy z CObject](../mfc/deriving-a-class-from-cobject.md) .

1. Użyj makra DECLARE_DYNAMIC w deklaracji klasy, jak pokazano poniżej:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. Użyj makra IMPLEMENT_DYNAMIC w pliku implementacji (. CPP) klasy. To makro przyjmuje jako argumenty nazwę klasy i jej klasy bazowej w następujący sposób:

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> Zawsze umieszczaj IMPLEMENT_DYNAMIC w pliku implementacji (. CPP) dla klasy. Makro IMPLEMENT_DYNAMIC powinno być oceniane tylko raz podczas kompilacji i dlatego nie powinno być używane w pliku interfejsu (. H), która może być potencjalnie zawarta w więcej niż jednym pliku.

## <a name="to-add-dynamic-creation-support"></a>Aby dodać obsługę dynamicznego tworzenia

1. Utwórz klasę z `CObject` .

1. Użyj makra DECLARE_DYNCREATE w deklaracji klasy.

1. Zdefiniuj konstruktora bez argumentów (Konstruktor domyślny).

1. Użyj makra IMPLEMENT_DYNCREATE w pliku implementacji klasy.

## <a name="to-add-serialization-support"></a>Aby dodać obsługę serializacji

1. Utwórz klasę z `CObject` .

1. Przesłoń `Serialize` funkcję członkowską.

   > [!NOTE]
   > Jeśli wywołasz `Serialize` bezpośrednio, to oznacza, że nie chcesz serializować obiektu za pomocą wskaźnika polimorficznego, Pomiń kroki od 3 do 5.

1. Użyj makra DECLARE_SERIAL w deklaracji klasy.

1. Zdefiniuj konstruktora bez argumentów (Konstruktor domyślny).

1. Użyj makra IMPLEMENT_SERIAL w pliku implementacji klasy.

> [!NOTE]
> "Wskaźnik polimorficzny" wskazuje obiekt klasy (wywoływany przez niego) lub obiekt klasy pochodnej z (Powiedz, B). Aby serializować przez wskaźnik polimorficzny, struktura musi określić klasę czasu wykonywania obiektu, który jest serializowany (B), ponieważ może być obiektem dowolnej klasy pochodnej od klasy podstawowej (A).

Aby uzyskać więcej informacji na temat włączania serializacji podczas wyprowadzania klasy z `CObject` , zobacz artykuły [pliki w MFC](../mfc/files-in-mfc.md) i [serializacji](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Zobacz też

[Wyprowadzanie klasy z CObject](../mfc/deriving-a-class-from-cobject.md)
