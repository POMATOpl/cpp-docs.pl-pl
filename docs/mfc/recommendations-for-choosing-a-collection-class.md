---
description: 'Dowiedz się więcej o: zalecenia dotyczące wybierania klasy kolekcji'
title: Zalecenia dotyczące wybierania klasy kolekcji
ms.date: 11/04/2016
helpviewer_keywords:
- type safety of collection classes [MFC]
- collection classes [MFC], serialization
- collection classes [MFC], speed
- collection classes [MFC], type safety
- collection classes [MFC], choosing
- collection classes [MFC], functionality
- shapes, collection
- collection classes [MFC], template-based
- MFC collection classes [MFC], characteristics
- collection classes [MFC], about collection classes [MFC]
- serialization [MFC], collection classes
- collection classes [MFC], duplicates allowed
- collection classes [MFC], shapes
ms.assetid: a82188cd-443f-40d8-a244-edf292a53db4
ms.openlocfilehash: 47cf0cc1f52a10d641dba9eecbd49190d9820f41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248535"
---
# <a name="recommendations-for-choosing-a-collection-class"></a>Zalecenia dotyczące wybierania klasy kolekcji

Ten artykuł zawiera szczegółowe informacje pomocne w wyborze klasy kolekcji dla konkretnych potrzeb aplikacji.

Wybór klasy kolekcji zależy od wielu czynników, takich jak:

- Funkcje kształtu klasy: kolejność, indeksowanie i wydajność, jak pokazano w tabeli [funkcji kształtu kolekcji](#_core_collection_shape_features) w dalszej części tego tematu

- Czy Klasa używa szablonów języka C++

- Czy elementy przechowywane w kolekcji mogą być serializowane

- Czy elementy przechowywane w kolekcji mogą być zrzucane na potrzeby diagnostyki

- Czy kolekcja jest bezpieczna pod względem typu

Poniższa tabela zawiera [funkcje kształtu kolekcji](#_core_collection_shape_features), podsumowujące charakterystyki dostępnych kształtów kolekcji.

- Kolumny 2 i 3 opisują kolejność i charakterystykę dostępu każdego kształtu. W tabeli termin "uporządkowane" oznacza, że kolejność, w której elementy są wstawiane i usuwane, określa ich kolejność w kolekcji. nie oznacza to, że elementy są sortowane według ich zawartości. Termin "Indexed" oznacza, że elementy w kolekcji mogą być pobierane przez indeks liczby całkowitej, podobnie jak elementy w typowej tablicy.

- Kolumny 4 i 5 opisują wydajność każdego kształtu. W aplikacjach, które wymagają wielu operacji wstawiania do kolekcji, szybkość wstawiania może być szczególnie ważna; w przypadku innych aplikacji szybkość wyszukiwania może być bardziej ważna.

- Kolumna 6 zawiera informacje o tym, czy każdy kształt umożliwia duplikowanie elementów.

### <a name="collection-shape-features"></a><a name="_core_collection_shape_features"></a> Funkcje kształtu kolekcji

|Kształt|Zamówione|Pełnotekstowych|Wstaw element|Wyszukaj określony element|Zduplikowane elementy|
|-----------|--------------|--------------|-----------------------|----------------------------------|-------------------------|
|Lista|Tak|Nie|Duża|Mała|Tak|
|Tablica|Tak|Według int|Mała|Mała|Tak|
|Mapa|Nie|Według klucza|Duża|Duża|Nie (klucze) tak (wartości)|

Poniższa tabela, [Charakterystyka klas kolekcji MFC](#_core_characteristics_of_mfc_collection_classes), podsumowuje inne ważne cechy określonych klas kolekcji MFC jako wskazówkę do wyboru. Wybór może zależeć od tego, czy Klasa jest oparta na szablonach języka C++, czy jego elementy mogą być serializowane za pośrednictwem mechanizmu [serializacji](../mfc/serialization-in-mfc.md) dokumentu MFC, czy jego elementy mogą być zrzucane za pośrednictwem mechanizmu dumpingu diagnostycznego MFC, czy też klasy są bezpieczne, czyli czy można zagwarantować typ elementów przechowywanych w kolekcji i pobieranych z niej na podstawie klasy.

### <a name="characteristics-of-mfc-collection-classes"></a><a name="_core_characteristics_of_mfc_collection_classes"></a> Charakterystyki klas kolekcji MFC

|Klasa|Używa języka C++<br /><br /> szablonów|Może być<br /><br /> serializowana|Może być<br /><br /> wykonano zrzutu|Is<br /><br /> bezpieczne dla typu|
|-----------|------------------------------|---------------------------|-----------------------|-----------------------|
|`CArray`|Tak|Tak 1|Tak 1|Nie|
|`CByteArray`|Nie|Tak|Tak|Tak 3|
|`CDWordArray`|Nie|Tak|Tak|Tak 3|
|`CList`|Tak|Tak 1|Tak 1|Nie|
|`CMap`|Tak|Tak 1|Tak 1|Nie|
|`CMapPtrToPtr`|Nie|Nie|Tak|Nie|
|`CMapPtrToWord`|Nie|Nie|Tak|Nie|
|`CMapStringToOb`|Nie|Tak|Tak|Nie|
|`CMapStringToPtr`|Nie|Nie|Tak|Nie|
|`CMapStringToString`|Nie|Tak|Tak|Tak 3|
|`CMapWordToOb`|Nie|Tak|Tak|Nie|
|`CMapWordToPtr`|Nie|Nie|Tak|Nie|
|`CObArray`|Nie|Tak|Tak|Nie|
|`CObList`|Nie|Tak|Tak|Nie|
|`CPtrArray`|Nie|Nie|Tak|Nie|
|`CPtrList`|Nie|Nie|Tak|Nie|
|`CStringArray`|Nie|Tak|Tak|Tak 3|
|`CStringList`|Nie|Tak|Tak|Tak 3|
|`CTypedPtrArray`|Tak|Jest zależne od 2|Tak|Tak|
|`CTypedPtrList`|Tak|Jest zależne od 2|Tak|Tak|
|`CTypedPtrMap`|Tak|Jest zależne od 2|Tak|Tak|
|`CUIntArray`|Nie|Nie|Tak|Tak 3|
|`CWordArray`|Nie|Tak|Tak|Tak 3|

1. Aby serializować, należy jawnie wywołać funkcję obiektu kolekcji `Serialize` ; aby zrzucić, należy jawnie wywołać jej `Dump` funkcję. Nie można użyć formularza `ar << collObj` do serializacji lub formularza `dmp` `<< collObj` do zrzutu.

2. Serializacja zależy od typu kolekcji bazowej. Na przykład jeśli typ tablicy wskaźnika jest oparty na typie `CObArray` , można go serializować; jeśli jest oparty na `CPtrArray` , nie można serializować. Ogólnie rzecz biorąc, klasy "PTR" nie mogą być serializowane.

3. Jeśli w tej kolumnie zostanie oznaczona wartość tak, Klasa kolekcji niebędącej szablonem jest bezpieczna pod względem typu, pod warunkiem, że używasz jej jako zamierzonej. Na przykład, Jeśli przechowujesz bajty w `CByteArray` , tablica jest bezpieczna pod względem typów. Ale jeśli używasz go do przechowywania znaków, jego bezpieczeństwo typu jest mniej określone.

## <a name="see-also"></a>Zobacz też

[Kolekcje](../mfc/collections.md)<br/>
[Klasy oparte na szablonach](../mfc/template-based-classes.md)<br/>
[Instrukcje: Tworzenie kolekcji Type-Safe](../mfc/how-to-make-a-type-safe-collection.md)<br/>
[Uzyskiwanie dostępu do wszystkich elementów członkowskich kolekcji](../mfc/accessing-all-members-of-a-collection.md)
