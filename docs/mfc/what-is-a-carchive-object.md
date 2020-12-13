---
description: 'Dowiedz się więcej na temat: co to jest obiekt CArchive'
title: Co to jest obiekt CArchive
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 7d98200f87f4b428a9450894aca5f8958115d627
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142795"
---
# <a name="what-is-a-carchive-object"></a>Co to jest obiekt CArchive

`CArchive`Obiekt zapewnia bezpieczny dla typu mechanizm buforowania do zapisywania lub odczytywania serializowanych obiektów do lub z `CFile` obiektu. Zazwyczaj `CFile` obiekt reprezentuje plik dysku, jednak może być również plikiem pamięci ( `CSharedFile` obiektem), prawdopodobnie reprezentującym schowek.

Dany `CArchive` obiekt albo zapisuje (zapisuje, serializować) dane lub ładuje (odczytuje, deserializacji) dane, ale nigdy nie obu. Okres istnienia `CArchive` obiektu jest ograniczony do jednego przebiegu przez zapisanie obiektów do pliku lub odczytywanie obiektów z pliku. W ten sposób `CArchive` do serializacji danych do pliku są wymagane dwa po sobie obiekty, a następnie deserializacji z powrotem z pliku.

Gdy archiwum przechowuje obiekty do pliku, archiwum dołącza `CRuntimeClass` nazwę do obiektów. Następnie, gdy inne archiwum ładuje obiekty z pliku do pamięci, `CObject` obiekty pochodne są dynamicznie ponownie konstruowane na podstawie `CRuntimeClass` obiektów. Dany obiekt może być przywoływany więcej niż raz, ponieważ jest zapisywany w pliku przez archiwum przechowujące. Archiwum ładowania, jednak ponownie konstruuje obiekt tylko raz. Szczegóły dotyczące sposobu, w jaki archiwum dołącza `CRuntimeClass` informacje do obiektów i odbudowy obiektów, biorąc pod uwagę możliwe wiele odwołań, są opisane w [uwagi technicznej 2](../mfc/tn002-persistent-object-data-format.md).

Gdy dane są serializowane do archiwum, archiwum zbiera dane do momentu zapełnienia buforu. Następnie archiwum zapisuje swój bufor do `CFile` obiektu wskazywanego przez `CArchive` obiekt. Podobnie podczas odczytywania danych z archiwum dane są odczytywane z pliku do bufora, a następnie z bufora do deserializowanego obiektu. Buforowanie zmniejsza liczbę przypadków, gdy dysk twardy jest odczytywany fizycznie, co poprawia wydajność aplikacji.

## <a name="see-also"></a>Zobacz też

[Serializacja: serializacja obiektu](../mfc/serialization-serializing-an-object.md)
