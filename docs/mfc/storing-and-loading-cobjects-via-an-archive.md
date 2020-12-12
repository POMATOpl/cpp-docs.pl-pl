---
description: 'Dowiedz się więcej na temat: przechowywanie i ładowanie obiektów CObject za pomocą archiwum'
title: Przechowywanie i ładowanie obiektów CObject za pomocą archiwum
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: c84c507fc556268eea526c1350211fd4b82f54fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216564"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Przechowywanie i ładowanie obiektów CObject za pomocą archiwum

Przechowywanie i ładowanie `CObject` s za pośrednictwem archiwum wymaga dodatkowej uwagi. W niektórych przypadkach należy wywołać `Serialize` funkcję obiektu, gdzie `CArchive` obiekt jest parametrem `Serialize` wywołania, w przeciwieństwie do użycia **<\<** or **>>** operatora `CArchive` . Ważnym faktem, że należy pamiętać, że `CArchive` **>>** operator konstruuje `CObject` w pamięci na podstawie `CRuntimeClass` informacji poprzednio zapisywanych w pliku przez archiwum przechowujące.

W związku z tym, niezależnie od tego, czy są używane `CArchive` **<\<** and **>>** operatory, w przeciwieństwie do wywołania, zależy od tego, `Serialize` czy *potrzebujesz* archiwum ładowania do dynamicznego konstruowania obiektu na podstawie wcześniej przechowywanych `CRuntimeClass` informacji. Użyj `Serialize` funkcji w następujących przypadkach:

- Podczas deserializacji obiektu należy wcześniej znać dokładnie klasę obiektu.

- Podczas deserializacji obiektu masz już przydzieloną pamięć.

> [!CAUTION]
> Jeśli załadujesz obiekt za pomocą `Serialize` funkcji, musisz również zapisać Obiekt przy użyciu `Serialize` funkcji. Nie przechowuj przy użyciu `CArchive` **<<** operatora, a następnie Ładuj przy użyciu `Serialize` funkcji, lub przechowuj przy użyciu `Serialize` funkcji, a następnie załaduj operator using `CArchive >>` .

Poniższy przykład ilustruje przypadki:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Podsumowując, jeśli klasa, której można serializować, definiuje osadzony `CObject` element członkowski, *nie* należy używać `CArchive` **<\<** and **>>** operatorów dla tego obiektu, ale powinna wywołać `Serialize` funkcję. Ponadto, jeśli Klasa możliwa do serializacji definiuje wskaźnik do `CObject` (lub obiektu pochodnego od `CObject` ) jako element członkowski, ale konstruuje ten inny obiekt we własnym konstruktorze, należy również wywołać metodę `Serialize` .

## <a name="see-also"></a>Zobacz też

[Serializacja: serializacja obiektu](../mfc/serialization-serializing-an-object.md)
