---
description: 'Dowiedz się więcej na temat: pliki w MFC'
title: Pliki w MFC
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
ms.openlocfilehash: 47fab5876efd7d06ec4364721a09b7ed09da9744
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155049"
---
# <a name="files-in-mfc"></a>Pliki w MFC

W biblioteka MFC (MFC) Klasa [CFile](reference/cfile-class.md) obsługuje normalne operacje we/wy na plikach. W tej rodzinie artykułów wyjaśniono, jak otwierać i zamykać pliki oraz odczytywać i zapisywać dane w tych plikach. Omówiono w nim również operacje stanu pliku. Opis sposobu korzystania z funkcji serializacji opartych na obiektach MFC jako alternatywny sposób odczytywania i zapisywania danych w plikach znajduje się w sekcji [Serializacja](serialization-in-mfc.md)artykułu.

> [!NOTE]
> Gdy korzystasz `CDocument` z obiektów MFC, struktura wykonuje większość zadań serializacji. W szczególności struktura tworzy i używa `CFile` obiektu. Musisz tylko napisać kod w przesłonięciu `Serialize` funkcji składowej klasy `CDocument` .

`CFile`Klasa zawiera interfejs dla operacji plików binarnych ogólnego przeznaczenia. `CStdioFile`Klasy i, które `CMemFile` pochodzą z `CFile` i `CSharedFile` klasy pochodzącej z `CMemFile` dostarczania bardziej wyspecjalizowanych usług plików.

Aby uzyskać więcej informacji o alternatywach do obsługi plików MFC, zobacz [Obsługa plików](../c-runtime-library/file-handling.md) w *dokumentacji dotyczącej biblioteki wykonawczej*.

Aby uzyskać informacje o `CFile` klasach pochodnych, zobacz [wykres hierarchii MFC](hierarchy-chart.md).

## <a name="what-do-you-want-to-do"></a>Co chcesz zrobić

*Użyj CFile*

- [Otwórz plik z CFile](opening-files.md)

- [Odczytuj i zapisuj plik z CFile](reading-and-writing-files.md)

- [Zamknij plik z CFile](closing-files.md)

- [Dostęp do stanu pliku za pomocą CFile](accessing-file-status.md)

*Użyj serializacji MFC (trwałość obiektu)*

- [Tworzenie klasy możliwej do serializacji](serialization-making-a-serializable-class.md)

- [Serializacja obiektu za pośrednictwem obiektu CArchive](serialization-serializing-an-object.md)

- [Tworzenie obiektu CArchive](two-ways-to-create-a-carchive-object.md)

- [Używanie operatorów CArchive <\< and >>](using-the-carchive-output-and-input-operators.md)

- [Przechowywanie i ładowanie obiektów pochodnych obiektów CObject i CObject za pomocą archiwum](storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>Zobacz też

[Pojęcia](mfc-concepts.md)<br/>
[Ogólne tematy dotyczące MFC](general-mfc-topics.md)<br/>
[Klasa CArchive](reference/carchive-class.md)<br/>
[Klasa CObject](reference/cobject-class.md)
