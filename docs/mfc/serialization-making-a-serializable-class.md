---
description: 'Dowiedz się więcej o: serializacji: Tworzenie klasy możliwej do serializacji'
title: 'Serializacja: ustawianie klasy jako możliwej do serializacji'
ms.date: 11/04/2016
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
ms.openlocfilehash: 21c45887199768094953066818acfe1b87d8d45d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217539"
---
# <a name="serialization-making-a-serializable-class"></a>Serializacja: ustawianie klasy jako możliwej do serializacji

Aby można było serializować klasę, wymagane są pięć głównych kroków. Są one wymienione poniżej i wyjaśniono w następujących sekcjach:

1. [Wyprowadzanie klasy z CObject](#_core_deriving_your_class_from_cobject) (lub z innej klasy pochodnej z `CObject` ).

1. [Zastępowanie serializowanej funkcji składowej](#_core_overriding_the_serialize_member_function).

1. [Użycie makra DECLARE_SERIAL](#_core_using_the_declare_serial_macro) w deklaracji klasy.

1. [Definiowanie konstruktora, który nie przyjmuje argumentów](#_core_defining_a_constructor_with_no_arguments).

1. [Użycie makra IMPLEMENT_SERIAL w pliku implementacji](#_core_using_the_implement_serial_macro_in_the_implementation_file) dla klasy.

W przypadku wywołania `Serialize` bezpośrednio, a nie za pomocą operatorów >> i << [CArchive](../mfc/reference/carchive-class.md), ostatnie trzy kroki nie są wymagane do serializacji.

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a> Wyprowadzanie klasy z CObject

Podstawowy protokół serializacji i funkcje są zdefiniowane w `CObject` klasie. Dzięki `CObject` wykorzystaniu klasy z (lub z klasy pochodnej `CObject` ), jak pokazano w następującej deklaracji klasy `CPerson` , uzyskuje się dostęp do protokołu serializacji i funkcji programu `CObject` .

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a> Zastępowanie serializowanej funkcji składowej

`Serialize`Funkcja członkowska, która jest zdefiniowana w `CObject` klasie, jest odpowiedzialna za faktyczne Serializowanie danych niezbędnych do przechwycenia bieżącego stanu obiektu. `Serialize`Funkcja ma `CArchive` argument, który używa do odczytu i zapisu danych obiektu. Obiekt [CArchive](../mfc/reference/carchive-class.md) ma funkcję członkowską, `IsStoring` która wskazuje, czy `Serialize` są przechowywane (zapisywanie danych) czy ładowanie (odczytywanie danych). Korzystając z wyników `IsStoring` jako przewodnika, wstawiasz dane obiektu do `CArchive` obiektu za pomocą operatora wstawiania ( **<\<**) or extract data with the extraction operator (**>>** ).

Rozważmy klasę, która pochodzi od `CObject` i ma dwie nowe zmienne Członkowskie, typy `CString` i **słowo**. Poniższy fragment deklaracji klasy przedstawia nowe zmienne Członkowskie i deklarację dla zastąpionej `Serialize` funkcji składowej:

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Aby zastąpić serializowaną funkcję członkowską

1. Wywołaj swoją wersję klasy bazowej, `Serialize` Aby upewnić się, że dziedziczona część obiektu jest serializowana.

1. Wstaw lub Wyodrębnij Zmienne Członkowskie specyficzne dla klasy.

   Operatory wstawiania i wyodrębniania współdziałają z klasą archiwalną, aby odczytywać i zapisywać dane. Poniższy przykład pokazuje, jak zaimplementować `Serialize` dla `CPerson` klasy zadeklarowanej powyżej:

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

Można również użyć funkcji [CArchive:: Read](../mfc/reference/carchive-class.md#read) i [CArchive:: Write](../mfc/reference/carchive-class.md#write) Członkowskiego, aby odczytywać i zapisywać duże ilości danych nienależących do typu.

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a> Za pomocą makra DECLARE_SERIAL

Makro DECLARE_SERIAL jest wymagane w deklaracji klas, które będą obsługiwać serializacji, jak pokazano poniżej:

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a> Definiowanie konstruktora bez argumentów

MFC wymaga konstruktora domyślnego podczas ponownego tworzenia obiektów w miarę ich deserializacji (załadowany z dysku). Proces deserializacji wypełni wszystkie zmienne Członkowskie wartościami wymaganymi do ponownego utworzenia obiektu.

Ten konstruktor można zadeklarować jako Public, protected lub Private. W przypadku zapewnienia ochrony IT lub prywatnego, należy upewnić się, że będzie on używany tylko przez funkcje serializacji. Konstruktor musi umieścić obiekt w stanie, który umożliwia jego usunięcie w razie potrzeby.

> [!NOTE]
> Jeśli zapomnisz zdefiniować konstruktora bez argumentów w klasie, która używa makr DECLARE_SERIAL i IMPLEMENT_SERIAL, otrzymasz ostrzeżenie kompilatora "Brak domyślnego konstruktora dostępne" w wierszu, w którym jest używane makro IMPLEMENT_SERIAL.

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> Używanie makra IMPLEMENT_SERIAL w pliku implementacji

Makro IMPLEMENT_SERIAL służy do definiowania różnych funkcji wymaganych podczas wyprowadzania klasy możliwej do serializacji `CObject` . To makro jest używane w pliku implementacji (. CPP) dla klasy. Pierwsze dwa argumenty makra są nazwą klasy i nazwą swojej bezpośredniej klasy podstawowej.

Trzeci argument tego makra to numer schematu. Numer schematu jest zasadniczo numerem wersji dla obiektów klasy. Dla numeru schematu Użyj liczby całkowitej większej lub równej 0. (Nie należy mylić tego numeru schematu z terminologią bazy danych).

Kod serializacji MFC sprawdza numer schematu podczas odczytu obiektów do pamięci. Jeśli numer schematu na dysku nie jest zgodny z numerem schematu klasy w pamięci, biblioteka zgłosi `CArchiveException` , uniemożliwiając programowi odczytywanie niepoprawnej wersji obiektu.

Jeśli chcesz, aby `Serialize` funkcja członkowska była w stanie odczytać wiele wersji, czyli plików pisanych z różnymi wersjami aplikacji — możesz użyć wartości *VERSIONABLE_SCHEMA* jako argumentu dla IMPLEMENT_SERIAL makro. Aby uzyskać informacje na temat użycia i przykład, zobacz `GetObjectSchema` funkcja członkowska klasy `CArchive` .

Poniższy przykład pokazuje, jak używać IMPLEMENT_SERIAL klasy, `CPerson` , która jest pochodną `CObject` :

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

Po utworzeniu klasy możliwej do serializacji można serializować obiekty klasy, jak to opisano w [serializacji artykułu: serializacji obiektu](../mfc/serialization-serializing-an-object.md).

## <a name="see-also"></a>Zobacz też

[Serializacja](../mfc/serialization-in-mfc.md)
