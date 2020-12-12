---
description: 'Dowiedz się więcej o: serializacji w MFC'
title: Serializacja w MFC
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: 278de59c6e091fd59826622553f50503b12602bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217578"
---
# <a name="serialization-in-mfc"></a>Serializacja w MFC

W tym artykule opisano mechanizm serializacji zapewniany w biblioteka MFC (MFC), aby umożliwić utrzymywanie obiektów między uruchomieniami programu.

Serializacja jest procesem zapisywania lub odczytywania obiektu do lub z trwałego nośnika magazynu, takiego jak plik dysku. Serializacja jest idealnym rozwiązaniem w sytuacjach, gdy jest to potrzebne do utrzymania stanu danych strukturalnych (takich jak klasy lub struktury C++) podczas wykonywania programu lub po jego wykonaniu. Korzystając z obiektów serializacji dostarczonych przez MFC, można to zrobić w sposób standardowy i spójny, co uwalnia użytkownika z konieczności ręcznego wykonywania operacji na plikach.

Wbudowana obsługa serializacji MFC w klasie `CObject` . W ten sposób wszystkie klasy pochodne `CObject` mogą korzystać z `CObject` protokołu serializacji.

Podstawowy pomysł serializacji polega na tym, że obiekt powinien być w stanie zapisać swój bieżący stan, zwykle wskazywany przez wartość jej zmiennych Członkowskich, do magazynu trwałego. Później obiekt można utworzyć ponownie, odczytując lub deserializacji, czyli stanu obiektu z magazynu. Serializacja obsługuje wszystkie szczegóły wskaźników obiektów i cykliczne odwołania do obiektów, które są używane podczas serializacji obiektu. Kluczowym punktem jest to, że obiekt jest odpowiedzialny za odczytywanie i pisanie własnego stanu. W tym celu dla klasy, która ma być możliwa do serializacji, musi implementować podstawowe operacje serializacji. Jak pokazano w grupie serializacji artykułów, można łatwo dodać tę funkcję do klasy.

MFC używa obiektu `CArchive` klasy jako pośrednika między obiektem do serializacji a nośnikiem magazynu. Ten obiekt jest zawsze skojarzony z `CFile` obiektem, z którego uzyskuje informacje niezbędne do serializacji, łącznie z nazwą pliku i czy żądana operacja jest operacją odczytu lub zapisu. Obiekt wykonujący operację serializacji może używać `CArchive` obiektu bez względu na charakter nośnika magazynu.

`CArchive`Obiekt używa przeciążonych operatorów wstawiania ( **<\<**) and extraction (**>>** ) do wykonywania operacji zapisu i odczytu. Aby uzyskać więcej informacji, zobacz [przechowywanie i ładowanie obiektów CObject za pośrednictwem archiwum](../mfc/storing-and-loading-cobjects-via-an-archive.md) w ramach serializacji artykułu: serializacji obiektu.

> [!NOTE]
> Nie należy mylić `CArchive` klasy z klasami iostream ogólnego przeznaczenia, które są tylko dla sformatowanego tekstu. `CArchive`Klasa jest dla obiektów serializowanych w formacie binarnym.

Jeśli chcesz, możesz pominąć serializację MFC, aby utworzyć własny mechanizm dla trwałego magazynu danych. Należy przesłonić funkcje składowe klasy, które inicjują serializację przy użyciu polecenia użytkownika. Zapoznaj się z dyskusjami w artykule [technicznym 22](../mfc/tn022-standard-commands-implementation.md) ID_FILE_OPEN, ID_FILE_SAVE i ID_FILE_SAVE_AS standardowych poleceń.

Poniższe artykuły obejmują dwa podstawowe zadania wymagane do serializacji:

- [Serializacja: Tworzenie klasy możliwej do serializacji](../mfc/serialization-making-a-serializable-class.md)

- [Serializacja: serializacja obiektu](../mfc/serialization-serializing-an-object.md)

Serializacja artykułu [: serializacja a dane wejściowe/wyjściowe bazy danych](../mfc/serialization-serialization-vs-database-input-output.md) opisuje, kiedy Serializacja jest odpowiednią techniką wejścia/wyjścia w aplikacjach baz danych.

## <a name="see-also"></a>Zobacz też

[Pojęcia](../mfc/mfc-concepts.md)<br/>
[Ogólne tematy dotyczące MFC](../mfc/general-mfc-topics.md)<br/>
[Klasa CArchive](../mfc/reference/carchive-class.md)<br/>
[Klasa CObject](../mfc/reference/cobject-class.md)<br/>
[Klasa CDocument](../mfc/reference/cdocument-class.md)<br/>
[Klasa CFile](../mfc/reference/cfile-class.md)
