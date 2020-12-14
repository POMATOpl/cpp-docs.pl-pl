---
description: 'Dowiedz się więcej na temat: dwa sposoby tworzenia obiektu CArchive'
title: Dwa sposoby tworzenia obiektu CArchive
ms.date: 11/04/2016
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
ms.openlocfilehash: 21a4321eef2d93cf0b37d157f57e12fa1ba940c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263858"
---
# <a name="two-ways-to-create-a-carchive-object"></a>Dwa sposoby tworzenia obiektu CArchive

Istnieją dwa sposoby tworzenia `CArchive` obiektu:

- [Niejawne utworzenie obiektu CArchive za pośrednictwem struktury](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [Jawne utworzenie obiektu CArchive](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> Niejawne utworzenie obiektu CArchive za pośrednictwem struktury

Najbardziej typowym i najprostszym sposobem jest umożliwienie struktury tworzenia `CArchive` obiektu dla dokumentu w imieniu poleceń Zapisz, Zapisz jako i Otwórz w menu plik.

Oto jakie środowisko robi, gdy użytkownik aplikacji wystawia polecenie Zapisz jako z menu plik:

1. Wyświetla okno dialogowe **Zapisz jako** i pobiera nazwę pliku od użytkownika.

1. Otwiera plik o nazwie użytkownika jako `CFile` obiekt.

1. Tworzy `CArchive` obiekt, który wskazuje na ten `CFile` obiekt. W przypadku tworzenia `CArchive` obiektu, struktura ustawia tryb na "Store" (Write, serializacji), w przeciwieństwie do "Load" (odczyt, deserializacji).

1. Wywołuje `Serialize` funkcję zdefiniowaną w `CDocument` klasie pochodnej, przekazując ją do `CArchive` obiektu.

`Serialize`Funkcja dokumentu następnie zapisuje dane do `CArchive` obiektu, jak wyjaśniono wkrótce. Po powrocie z `Serialize` funkcji, struktura niszczy `CArchive` obiekt, a następnie `CFile` obiekt.

W takim przypadku, Jeśli zezwolisz platformie na utworzenie `CArchive` obiektu dla dokumentu, wszystkie czynności, które należy wykonać, zaimplementują `Serialize` funkcję dokumentu, która zapisuje i odczytuje do i z archiwum. Należy również zaimplementować `Serialize` dla wszystkich `CObject` obiektów pochodnych, które `Serialize` Funkcja dokumentu w programie może bezpośrednio lub pośrednio serializować.

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a> Jawne utworzenie obiektu CArchive

Oprócz serializowania dokumentu za pośrednictwem struktury, istnieją inne przypadki, w których może być potrzebny `CArchive` obiekt. Na przykład możesz chcieć serializować dane do i ze schowka reprezentowane przez `CSharedFile` obiekt. Lub można użyć interfejsu użytkownika do zapisywania pliku, który jest inny niż ten, który jest oferowany przez platformę. W takim przypadku można jawnie utworzyć `CArchive` obiekt. Wykonuje się to tak samo jak w przypadku platformy, wykonując poniższą procedurę.

#### <a name="to-explicitly-create-a-carchive-object"></a>Aby jawnie utworzyć obiekt CArchive

1. Konstruowanie `CFile` obiektu lub obiektu pochodnego od `CFile` .

1. Przekaż `CFile` obiekt do konstruktora dla `CArchive` , jak pokazano w następującym przykładzie:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   Drugi argument `CArchive` konstruktora jest wartością wyliczaną, która określa, czy archiwum będzie używane do przechowywania lub ładowania danych do lub z pliku. `Serialize`Funkcja obiektu sprawdza ten stan przez wywołanie `IsStoring` funkcji dla obiektu archiwum.

Po zakończeniu przechowywania lub ładowania danych do lub z `CArchive` obiektu, zamknij go. Mimo że `CArchive` obiekty (i `CFile` ) automatycznie zamkną archiwum (i pliku), dobrym rozwiązaniem jest to, że jest to bardziej jawne, ponieważ sprawia, że odzyskiwanie z błędów jest łatwiejsze. Aby uzyskać więcej informacji na temat obsługi błędów, zobacz [wyjątki artykułów: Przechwytywanie i usuwanie wyjątków](../mfc/exceptions-catching-and-deleting-exceptions.md).

#### <a name="to-close-the-carchive-object"></a>Aby zamknąć obiekt CArchive

1. Poniższy przykład ilustruje sposób zamykania `CArchive` obiektu:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>Zobacz też

[Serializacja: serializacja obiektu](../mfc/serialization-serializing-an-object.md)
