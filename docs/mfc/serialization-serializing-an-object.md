---
description: 'Dowiedz się więcej o: serializacji: serializacji obiektu'
title: 'Serializacja: serializacja obiektu'
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: ec0782f7faa0d6400f40013925f4a53495a76c7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217476"
---
# <a name="serialization-serializing-an-object"></a>Serializacja: serializacja obiektu

Serializacja artykułu [: utworzenie klasy](../mfc/serialization-making-a-serializable-class.md) możliwej do serializacji pokazuje, jak można serializować klasę. Po utworzeniu klasy możliwej do serializacji można serializować obiekty tej klasy do i z pliku za pośrednictwem obiektu [CArchive](../mfc/reference/carchive-class.md) . W tym artykule wyjaśniono:

- [Co to jest obiekt CArchive](../mfc/what-is-a-carchive-object.md).

- [Dwa sposoby tworzenia CArchive](../mfc/two-ways-to-create-a-carchive-object.md).

- [Jak używać operatorów CArchive <\< and >>](../mfc/using-the-carchive-output-and-input-operators.md).

- [Przechowywanie i ładowanie obiektów CObject za pomocą archiwum](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Możesz pozwolić, aby struktura utworzyła Archiwum dla możliwego do serializacji dokumentu lub `CArchive` samodzielnie utworzyć obiekt. Można przesłać dane między plikiem a obiektem możliwym do serializacji za pomocą \< and > operatorów <> dla `CArchive` lub, w niektórych przypadkach, przez wywołanie `Serialize` funkcji `CObject` klasy pochodnej.

## <a name="see-also"></a>Zobacz też

[Serializacja](../mfc/serialization-in-mfc.md)
