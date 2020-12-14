---
description: 'Dowiedz się więcej na temat: Czy muszę utworzyć nowe klasy z CObject?'
title: Czy muszę wyprowadzać nowe klasy z obiektu CObject?
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: d37570cb62f1ee274e4cea85fc95a9221c95fd8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261310"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Czy muszę wyprowadzać nowe klasy z obiektu CObject?

Nie.

Utwórz klasę z [CObject](reference/cobject-class.md) , gdy potrzebujesz udostępnianych przez nią obiektów, takich jak Serializacja lub dynamiczne tworzenie. Wiele klas danych musi być serializowanych do plików, więc często dobrym pomysłem jest uzyskanie ich z `CObject` . Przykład klasy pochodzącej od elementu `CObject` można znaleźć w przykładowym [bazgrołie](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Zobacz też

[Klasa CObject: często zadawane pytania](cobject-class-frequently-asked-questions.md)
