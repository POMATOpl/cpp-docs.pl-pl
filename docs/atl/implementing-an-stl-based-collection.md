---
description: 'Dowiedz się więcej o: implementowanie kolekcji standardowej Library-Based w języku C++'
title: Implementowanie kolekcji standardowej Library-Based w języku C++
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: 4a403885a6fe66bf8e8578deeab05c7fc08e88a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152857"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>Implementowanie kolekcji standardowej Library-Based w języku C++

ATL udostępnia `ICollectionOnSTLImpl` interfejs umożliwiający szybkie Implementowanie interfejsów opartych na bibliotece C++ standard w obiektach. Aby zrozumieć, jak działa ta klasa, będziesz pracować przez prosty przykład (poniżej), który używa tej klasy do implementowania kolekcji tylko do odczytu na klientach automatyzacji.

Przykładowy kod pochodzi z [przykładu ATLCollections](../overview/visual-cpp-samples.md).

Aby wykonać tę procedurę, możesz:

- [Generowanie nowego prostego obiektu](#vccongenerating_an_object).

- [Edytuj plik IDL](#vcconedit_the_idl) dla wygenerowanego interfejsu.

- [Utwórz pięć typów typedef](#vcconstorage_and_exposure_typedefs) opisujących sposób przechowywania elementów kolekcji i sposobu ich udostępnienia klientom za pośrednictwem interfejsów com.

- [Utwórz dwa elementy typedef dla klas zasad kopiowania](#vcconcopy_classes).

- [Utwórz elementy typedef dla implementacji modułu wyliczającego i kolekcji](#vcconenumeration_and_collection).

- [Edytuj kod języka C++ wygenerowany przez kreatora, aby użyć elementu typedef kolekcji](#vcconedit_the_generated_code).

- [Dodaj kod, aby wypełnić kolekcję](#vcconpopulate_the_collection).

## <a name="generating-a-new-simple-object"></a><a name="vccongenerating_an_object"></a> Generowanie nowego obiektu prostego

Utwórz nowy projekt, upewniając się, że pole atrybuty w obszarze Ustawienia aplikacji jest wyczyszczone. Za pomocą okna dialogowego Dodaj klasę ATL i Kreatora dodawania prostego obiektu można wygenerować prosty obiekt o nazwie `Words` . Upewnij się, że jest generowany podwójny interfejs o nazwie `IWords` . Obiekty generowanej klasy będą używane do reprezentowania kolekcji wyrazów (czyli ciągów).

## <a name="editing-the-idl-file"></a><a name="vcconedit_the_idl"></a> Edytowanie pliku IDL

Teraz otwórz plik IDL i Dodaj trzy właściwości niezbędne do włączenia `IWords` interfejsu kolekcji tylko do odczytu, jak pokazano poniżej:

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

Jest to standardowy formularz dla interfejsu kolekcji tylko do odczytu, zaprojektowany z myślą o klientach usługi Automation. Numerowane komentarze w tej definicji interfejsu odpowiadają poniższym komentarzom:

1. Interfejsy kolekcji są zwykle dwa, ponieważ klienci automatyzacji uzyskują dostęp do `_NewEnum` właściwości za pośrednictwem `IDispatch::Invoke` . Jednak klienci usługi Automation mogą uzyskać dostęp do pozostałych metod za pośrednictwem tabeli metod wirtualnych, więc do dispinterfacesi są preferowane podwójne interfejsy.

1. Jeśli podwójny interfejs lub dispinterface nie zostanie rozszerzony w czasie wykonywania (oznacza to, że nie będzie można dostarczyć dodatkowych metod lub właściwości za pośrednictwem `IDispatch::Invoke` ), należy zastosować atrybut **nierozszerzalny** do definicji. Ten atrybut umożliwia klientom automatyzacji wykonywanie pełnej weryfikacji kodu w czasie kompilacji. W takim przypadku interfejs nie powinien być rozszerzony.

1. Prawidłowy identyfikator DISPID jest ważny, jeśli chcesz, aby klienci automatyzacji mogli korzystać z tej właściwości. (Należy zauważyć, że w DISPID_NEWENUM jest tylko jeden znak podkreślenia).

1. Możesz podać dowolną wartość jako identyfikator DISPID `Item` właściwości. Jednak `Item` zazwyczaj używa DISPID_VALUE, aby uczynić go domyślną właściwością kolekcji. Pozwala to klientom automatyzacji na odwoływanie się do właściwości bez jawnego nazewnictwa.

1. Typ danych używany dla wartości zwracanej `Item` właściwości jest typem elementu przechowywanego w kolekcji, jeśli chodzi o klientów com. Interfejs zwraca ciągi, dlatego należy używać standardowego typu ciągu COM, BSTR. Dane można przechowywać w innym formacie wewnętrznie, ponieważ wkrótce zobaczysz.

1. Wartość używana dla DISPID `Count` właściwości jest całkowicie arbitralna. Dla tej właściwości nie istnieje standardowy identyfikator DISPID.

## <a name="creating-typedefs-for-storage-and-exposure"></a><a name="vcconstorage_and_exposure_typedefs"></a> Tworzenie typów typedef dla magazynu i ekspozycji

Po zdefiniowaniu interfejsu kolekcji należy zdecydować, jak będą przechowywane dane oraz jak dane będą widoczne za pośrednictwem modułu wyliczającego.

Odpowiedzi na te pytania można podać w postaci kilku typów typedef, które można dodać w górnej części pliku nagłówkowego dla nowo utworzonej klasy:

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

W takim przypadku dane będą przechowywane jako **std:: Vector** of **std:: String** s. **std:: Vector** jest klasą kontenera standardowej biblioteki języka C++, która zachowuje się jak zarządzana tablica. **std:: String** jest klasą ciągu standardowej biblioteki języka C++. Te klasy ułatwiają współpracę z kolekcją ciągów.

Ponieważ obsługa Visual Basic jest istotna dla sukcesu tego interfejsu, moduł wyliczający zwracany przez `_NewEnum` Właściwość musi obsługiwać `IEnumVARIANT` interfejs. Jest to jedyny interfejs modułu wyliczającego zrozumiały dla Visual Basic.

## <a name="creating-typedefs-for-copy-policy-classes"></a><a name="vcconcopy_classes"></a> Tworzenie typów typedef dla klas zasad kopiowania

Utworzone przez siebie elementy typedef zawierają wszystkie informacje potrzebne do utworzenia dalszych typów typedef dla klas kopiowania, które będą używane przez moduł wyliczający i kolekcję:

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

W tym przykładzie można użyć `GenericCopy` klasy niestandardowej zdefiniowanej w VCUE_Copy. h i VCUE_CopyString. h z przykładu [ATLCollections](../overview/visual-cpp-samples.md) . Można użyć tej klasy w innym kodzie, ale może być konieczne zdefiniowanie dalszych specjalizacji w `GenericCopy` celu obsługi typów danych używanych w własnych kolekcjach. Aby uzyskać więcej informacji, zobacz [klasy zasad kopiowania ATL](../atl/atl-copy-policy-classes.md).

## <a name="creating-typedefs-for-enumeration-and-collection"></a><a name="vcconenumeration_and_collection"></a> Tworzenie typów typedef na potrzeby wyliczania i zbierania

Teraz wszystkie parametry szablonu niezbędne do specjalizacji `CComEnumOnSTL` `ICollectionOnSTLImpl` klas i dla tej sytuacji zostały podane w postaci elementów typedef. Aby uprościć korzystanie z specjalizacji, Utwórz dwa więcej Typedefs, jak pokazano poniżej:

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

Teraz `CollectionType` jest synonimem specjalizacji `ICollectionOnSTLImpl` , który implementuje `IWords` interfejs zdefiniowany wcześniej i udostępnia moduł wyliczający, który obsługuje `IEnumVARIANT` .

## <a name="editing-the-wizard-generated-code"></a><a name="vcconedit_the_generated_code"></a> Edytowanie kodu Wizard-Generated

Teraz musisz pochodzić `CWords` od implementacji interfejsu reprezentowanej przez `CollectionType` element typedef zamiast `IWords` , jak pokazano poniżej:

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

## <a name="adding-code-to-populate-the-collection"></a><a name="vcconpopulate_the_collection"></a> Dodawanie kodu w celu wypełnienia kolekcji

Jedyną czynnością, która pozostanie, jest wypełnienie wektora danymi. W tym prostym przykładzie można dodać kilka słów do kolekcji w konstruktorze dla klasy:

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

Teraz można testować kod przy użyciu wybranego klienta.

## <a name="see-also"></a>Zobacz też

[Kolekcje i moduły wyliczające](../atl/atl-collections-and-enumerators.md)<br/>
[Przykład ATLCollections](../overview/visual-cpp-samples.md)<br/>
[Klasy zasad kopiowania ATL](../atl/atl-copy-policy-classes.md)
