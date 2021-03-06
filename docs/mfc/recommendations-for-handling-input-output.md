---
description: 'Dowiedz się więcej o: zalecenia dotyczące obsługi danych wejściowych/wyjściowych'
title: Zalecenia dotyczące obsługi Input-Output
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
ms.openlocfilehash: c9a1acab50dc95f12d3002f54f4ab0819c041068
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248492"
---
# <a name="recommendations-for-handling-inputoutput"></a>Zalecenia dotyczące obsługi we/wy

Niezależnie od tego, czy używasz operacji we/wy opartych na plikach, czy nie zależą od odpowiedzi na pytania w następującym drzewie decyzyjnym:

**Czy dane podstawowe w aplikacji znajdują się w pliku dysku**

- Tak, podstawowe dane znajdują się w pliku dysku:

   **Czy aplikacja odczytuje cały plik do pamięci po otwarciu pliku i zapisuje cały plik z powrotem do dysku przy zapisywaniu pliku**

  - Tak: jest to domyślny przypadek dokumentu MFC. Użyj `CDocument` serializacji.

  - Nie: zwykle jest to przypadek aktualizacji pliku na podstawie transakcji. Aktualizujesz plik na podstawie transakcji i nie potrzebujesz `CDocument` serializacji.

- Nie, dane podstawowe nie znajdują się w pliku dysku:

   **Czy dane znajdują się w źródle danych ODBC**

  - Tak, dane znajdują się w źródle danych ODBC:

      Użyj obsługi bazy danych MFC. Standardowa implementacja MFC w tym przypadku obejmuje `CDatabase` obiekt, zgodnie z opisem w artykule [MFC: używanie klas baz danych z dokumentami i widokami](../data/mfc-using-database-classes-with-documents-and-views.md). Aplikacja może również odczytywać i zapisywać plik pomocniczy — przeznaczenie Kreatora aplikacji "widok bazy danych i obsługa plików". W takim przypadku należy użyć serializacji dla pliku pomocniczego.

  - Nie, dane nie znajdują się w źródle danych ODBC.

      Przykłady w tym przypadku: dane znajdują się w systemie DBMS innym niż ODBC; dane są odczytywane za pośrednictwem innego mechanizmu, takiego jak OLE lub DDE.

      W takich przypadkach nie będziesz używać serializacji, a Twoja aplikacja nie będzie mieć elementów menu Otwórz i Zapisz. Można nadal używać programu `CDocument` jako podstawy, podobnie jak aplikacja MFC ODBC używa dokumentu do przechowywania `CRecordset` obiektów. Ale nie będziesz używać domyślnej serializacji pliku Open/Save dla struktury.

Aby zapewnić obsługę poleceń Otwórz, Zapisz i Zapisz jako w menu plik, struktura zapewnia serializację dokumentu. Serializacja odczytuje i zapisuje dane, w tym obiekty pochodzące z klasy `CObject` , do magazynu trwałego, zazwyczaj plik dyskowy. Serializacja jest łatwa w użyciu i obsługuje wiele Twoich potrzeb, ale może być nieodpowiednia w wielu aplikacjach dostępu do danych. Aplikacje dostępu do danych zazwyczaj aktualizują dane na podstawie poszczególnych transakcji. Aktualizują rekordy, których dotyczy transakcja, zamiast odczytywania i zapisywania całego pliku danych jednocześnie.

Aby uzyskać informacje o serializacji, zobacz [serializacji](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Zobacz też

[Serializacja: serializacja a dane wejściowe/wyjściowe bazy danych](../mfc/serialization-serialization-vs-database-input-output.md)
