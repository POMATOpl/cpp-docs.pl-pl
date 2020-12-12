---
description: 'Dowiedz się więcej o: serializacji danych do i z plików'
title: Serializacja danych do plików i z plików
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
ms.openlocfilehash: 58956b2f11b8f0131aae74a6c5b51715fe25c7e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217448"
---
# <a name="serializing-data-to-and-from-files"></a>Serializacja danych do plików i z plików

Podstawowy pomysł dotyczący trwałości polega na tym, że obiekt powinien mieć możliwość zapisu jego bieżącego stanu, wskazywanego przez wartości zmiennych składowych, do magazynu trwałego. Później obiekt można utworzyć ponownie przez odczytanie lub "deserializacja" stanu obiektu z magazynu trwałego. Kluczowym punktem jest to, że obiekt jest odpowiedzialny za odczytywanie i pisanie własnego stanu. W ten sposób, aby Klasa była trwała, musi implementować podstawowe operacje serializacji.

Struktura zawiera domyślną implementację zapisywania dokumentów w plikach dyskowych w odpowiedzi na polecenia Zapisz i Zapisz jako w menu plik oraz do ładowania dokumentów z plików dysków w odpowiedzi na polecenie Otwórz. Za pomocą bardzo mało pracy można zaimplementować dokument w celu zapisywania i odczytywania jego danych do i z pliku. Główną czynnością, którą należy wykonać, jest przesłonięcie [serializowanej](../mfc/reference/cobject-class.md#serialize) funkcji składowej w klasie dokumentu.

Kreator aplikacji MFC umieszcza przesłonięcie szkieletowe `CDocument` funkcji składowej `Serialize` w klasie dokumentu, którą tworzy. Po zaimplementowaniu zmiennych składowych aplikacji można wypełnić `Serialize` przesłonięcie kodem, który wysyła dane do "obiektu archiwum" połączonego z plikiem. Obiekt [CArchive](../mfc/reference/carchive-class.md) jest podobny do obiektów danych wejściowych/wyjściowych **CIN** i **cout** z biblioteki iostream języka C++. Jednak `CArchive` zapisuje i odczytuje format binarny, a nie sformatowany tekst.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Serializacja](../mfc/serialization-in-mfc.md)

- [Rola dokumentu w serializacji](#_core_the_document.92.s_role_in_serialization)

- [Rola danych w serializacji](#_core_the_data.92.s_role_in_serialization)

- [Pomijanie mechanizmu serializacji](../mfc/bypassing-the-serialization-mechanism.md)

## <a name="the-documents-role-in-serialization"></a><a name="_core_the_document.92.s_role_in_serialization"></a> Rola dokumentu w serializacji

Platforma automatycznie reaguje na polecenia Otwórz, Zapisz i Zapisz jako w menu plik, wywołując `Serialize` funkcję członkowską dokumentu, jeśli jest ona zaimplementowana. Polecenie ID_FILE_OPEN, na przykład wywołuje funkcję procedury obsługi w obiekcie aplikacji. W trakcie tego procesu użytkownik widzi okno dialogowe Otwieranie pliku i odpowiada na nie, a struktura uzyskuje nazwę pliku wybranego przez użytkownika. Struktura tworzy `CArchive` obiekt skonfigurowany do ładowania danych do dokumentu i przekazuje archiwum do programu `Serialize` . Struktura otworzyła już plik. Kod w `Serialize` funkcji członkowskiej dokumentu odczytuje dane z w archiwum, odbudowy obiektów danych zgodnie z potrzebami. Aby uzyskać więcej informacji na temat serializacji, zobacz [serializacji](../mfc/serialization-in-mfc.md)artykułu.

## <a name="the-datas-role-in-serialization"></a><a name="_core_the_data.92.s_role_in_serialization"></a> Rola danych w serializacji

Ogólnie rzecz biorąc, dane typu klasy powinny być w stanie serializować siebie. Oznacza to, że po przekazanie obiektu do archiwum, obiekt powinien wiedzieć, jak napisać sam do archiwum i jak odczytywać dane z archiwum. MFC zapewnia obsługę tworzenia klas w ten sposób. W przypadku projektowania klasy w celu zdefiniowania typu danych i planowane jest Serializacja danych tego typu, projekt do serializacji.

## <a name="see-also"></a>Zobacz też

[Używanie dokumentów](../mfc/using-documents.md)
