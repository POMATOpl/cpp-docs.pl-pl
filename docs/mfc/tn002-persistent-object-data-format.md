---
description: 'Dowiedz się więcej na temat: TN002: format trwałych danych obiektu'
title: 'TN002: format trwałych danych obiektu'
ms.date: 11/04/2016
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: e99d54bd2624bffac4f5fea37c72bb7719e1e408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216083"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: format trwałych danych obiektu

Ta Uwaga opisuje procedury MFC obsługujące trwałe obiekty C++ i format danych obiektów, gdy są przechowywane w pliku. Dotyczy to tylko klas z makrami [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) i [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) .

## <a name="the-problem"></a>Problem

Implementacja MFC w przypadku trwałych danych przechowuje dane dla wielu obiektów w pojedynczej ciągłej części pliku. `Serialize`Metoda obiektu tłumaczy dane obiektu na kompaktowy format binarny.

Implementacja gwarantuje, że wszystkie dane są zapisywane w tym samym formacie za pomocą [klasy CArchive](../mfc/reference/carchive-class.md). Używa `CArchive` obiektu jako translatora. Ten obiekt jest trwały od momentu utworzenia, dopóki nie zostanie wywołana [CArchive:: Close](../mfc/reference/carchive-class.md#close). Ta metoda może być wywoływana jawnie przez programistę lub niejawnie przez destruktor, gdy program opuszcza zakres, który zawiera `CArchive` .

Ta Uwaga opisuje implementację `CArchive` elementów członkowskich [CArchive:: ReadObject](../mfc/reference/carchive-class.md#readobject) i [CArchive:: WriteObject](../mfc/reference/carchive-class.md#writeobject). Kod dla tych funkcji można znaleźć w Arcobj. cpp, a główna implementacja programu `CArchive` w Arccore. cpp. Kod użytkownika nie jest wywoływany `ReadObject` i `WriteObject` bezpośrednio. Zamiast tego obiekty te są używane przez operatory wstawiania i wyodrębniania bezpieczne dla typów, które są generowane automatycznie przez DECLARE_SERIAL i IMPLEMENT_SERIAL makra. Poniższy kod pokazuje, jak `WriteObject` i `ReadObject` są wywoływane niejawnie:

```
class CMyObject : public CObject
{
    DECLARE_SERIAL(CMyObject)
};

IMPLEMENT_SERIAL(CMyObj, CObject, 1)

// example usage (ar is a CArchive&)
CMyObject* pObj;
CArchive& ar;
ar <<pObj;        // calls ar.WriteObject(pObj)
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))
```

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>Zapisywanie obiektów w magazynie (CArchive:: WriteObject)

Metoda `CArchive::WriteObject` zapisuje dane nagłówka, które są używane do odtworzenia obiektu. Te dane składają się z dwóch części: typu obiektu i stanu obiektu. Ta metoda jest również odpowiedzialna za utrzymywanie tożsamości zapisywanych obiektów, tak aby tylko jedna kopia była zapisywana, niezależnie od liczby wskaźników do tego obiektu (w tym wskaźników okrągłych).

Zapisywanie (wstawianie) i przywracanie (wyodrębnianie) obiektów polega na kilku "stałych manifestu". Są to wartości, które są przechowywane w formacie binarnym i zawierają ważne informacje dla archiwum (należy zwrócić uwagę, że prefiks "w" wskazuje liczbę 16-bitową):

|Tag|Opis|
|---------|-----------------|
|wNullTag|Używane dla wskaźników obiektu o wartości NULL (0).|
|wNewClassTag|Wskazuje, że Poniższy opis klasy jest nowy dla tego kontekstu archiwum (-1).|
|wOldClassTag|Wskazuje klasę odczytywanego obiektu w tym kontekście (0x8000).|

W przypadku przechowywania obiektów archiwum utrzymuje [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) ( *m_pStoreMap*), który jest mapowaniem z zapisanego obiektu na 32-bitowy identyfikator trwały (PID). Identyfikator PID jest przypisywany do każdego unikatowego obiektu i każdej unikatowej nazwy klasy, która jest zapisywana w kontekście archiwum. Te identyfikatory PID są przekazywane sekwencyjnie, począwszy od 1. Te identyfikatory PID nie mają znaczenia poza zakresem archiwum i, w szczególności, nie należy mylić z numerami rekordów ani innymi elementami tożsamości.

W `CArchive` klasie identyfikatory PID są 32-bitowe, ale są zapisywane jako 16-bitowe, chyba że są większe niż 0x7FFE. Duże identyfikatory PID są zapisywane jako 0x7FFF, po których następuje 32-bitowy Identyfikator PID. Zapewnia to zgodność z projektami, które zostały utworzone we wcześniejszych wersjach.

Gdy zostanie wysłane żądanie zapisania obiektu do archiwum (zazwyczaj przy użyciu globalnego operatora wstawiania), jest wykonywane sprawdzenie dla wskaźnika [CObject](../mfc/reference/cobject-class.md) o wartości null. Jeśli wskaźnik ma wartość NULL, *wNullTag* zostanie wstawiony do strumienia archiwum.

Jeśli wskaźnik nie ma wartości NULL i może być serializowany (Klasa jest `DECLARE_SERIAL` klasą), kod sprawdza *m_pStoreMap* , aby sprawdzić, czy obiekt został już zapisany. Jeśli ma, kod wstawia 32-bitowy Identyfikator PID skojarzony z tym obiektem do strumienia archiwum.

Jeśli obiekt nie został wcześniej zapisany, istnieją dwie metody, które należy wziąć pod uwagę: zarówno obiekt, jak i dokładny typ (czyli Klasa) obiektu są nowe dla tego kontekstu archiwum lub obiekt jest dokładnym już widzianym typem. Aby określić, czy typ był widoczny, kod wysyła zapytanie do *m_pStoreMap* obiektu [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) , który jest zgodny z `CRuntimeClass` obiektem skojarzonym z zapisywanym obiektem. Jeśli istnieje dopasowanie, `WriteObject` wstawia tag, który jest bitem `OR` *wOldClassTag* i tym indeksem. Jeśli `CRuntimeClass` ten kontekst archiwum jest nowy, `WriteObject` przypisuje nowy identyfikator PID do tej klasy i wstawia go do archiwum, poprzedzone przez wartość *wNewClassTag* .

Deskryptor tej klasy jest następnie wstawiany do archiwum przy użyciu `CRuntimeClass::Store` metody. `CRuntimeClass::Store` Wstawia numer schematu klasy (patrz poniżej) i nazwę tekstu ASCII klasy. Należy zauważyć, że użycie nazwy tekstowej ASCII nie gwarantuje unikatowej wartości Archiwum w aplikacjach. W związku z tym należy oznaczyć pliki danych, aby zapobiec uszkodzeniu. Po wstawieniu informacji o klasie archiwum umieszcza obiekt w *m_pStoreMap* a następnie wywołuje `Serialize` metodę, aby wstawić dane specyficzne dla klasy. Umieszczenie obiektu w *m_pStoreMap* przed wywołaniem `Serialize` uniemożliwia zapisanie wielu kopii obiektu w sklepie.

Podczas powrotu do początkowego obiektu wywołującego (zazwyczaj jest to katalog główny sieci obiektów), należy wywołać [CArchive:: Close](../mfc/reference/carchive-class.md#close). Jeśli planujesz wykonać inne operacje [CFile](../mfc/reference/cfile-class.md), należy wywołać `CArchive` metodę [Flush](../mfc/reference/carchive-class.md#flush) , aby zapobiec uszkodzeniu archiwum.

> [!NOTE]
> Ta implementacja nakłada sztywny limit 0x3FFFFFFE indeksów na kontekst archiwum. Ta liczba reprezentuje maksymalną liczbę unikatowych obiektów i klas, które można zapisać w jednym archiwum, ale jeden plik dysku może mieć nieograniczoną liczbę kontekstów archiwum.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>Ładowanie obiektów ze sklepu (CArchive:: ReadObject)

Ładowanie (wyodrębnianie) obiektów używa `CArchive::ReadObject` metody i jest odwrotnie `WriteObject` . Podobnie jak w przypadku `WriteObject` , `ReadObject` nie jest wywoływana bezpośrednio przez kod użytkownika; kod użytkownika powinien wywołać operator wyodrębniania bezpiecznego typu, który wywołuje `ReadObject` z oczekiwanym `CRuntimeClass` . Spowoduje to, że integralność typu operacji wyodrębniania.

Ponieważ `WriteObject` implementacja przypisała rosnące identyfikatory PID, rozpoczynając od 1 (0) jako obiektu o wartości null, `ReadObject` implementacja może użyć tablicy do utrzymania stanu kontekstu archiwum. Gdy identyfikator PID jest odczytywany ze sklepu, jeśli Identyfikator PID jest większy niż bieżący górny granica *m_pLoadArray*, oznacza to, `ReadObject` że jest następujący nowy obiekt (lub opis klasy).

## <a name="schema-numbers"></a>Numery schematów

Numer schematu, który jest przypisany do klasy podczas `IMPLEMENT_SERIAL` napotkania metody klasy, jest "wersja" implementacji klasy. Schemat odwołuje się do implementacji klasy, a nie liczby przypadków, w których dany obiekt został trwały (zwykle określany jako wersja obiektu).

Jeśli zamierzasz zachować kilka różnych implementacji tej samej klasy z upływem czasu, zwiększając schemat w miarę zmiany implementacji metody obiektu, umożliwi `Serialize` to napisać kod, który może ładować obiekty przechowywane przy użyciu starszych wersji implementacji.

`CArchive::ReadObject`Metoda zgłosi [CArchiveException](../mfc/reference/carchiveexception-class.md) , gdy napotka numer schematu w magazynie trwałym, który różni się od numeru schematu opisu klasy w pamięci. Odzyskiwanie z tego wyjątku nie jest łatwe.

`VERSIONABLE_SCHEMA`Aby zapobiec zgłaszaniu tego wyjątku, możesz użyć połączonego z (bitowego **lub**) wersji schematu. Przy użyciu `VERSIONABLE_SCHEMA` , kod może wykonać odpowiednią akcję w `Serialize` funkcji, sprawdzając wartość zwracaną z [CArchive:: GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema).

## <a name="calling-serialize-directly"></a>Bezpośrednie wywoływanie serializacji

W wielu przypadkach obciążenie ogólnego schematu archiwum obiektów `WriteObject` i `ReadObject` nie jest konieczne. Jest to typowy przypadek serializowania danych do [CDocument](../mfc/reference/cdocument-class.md). W tym przypadku `Serialize` Metoda `CDocument` jest wywoływana bezpośrednio, a nie za pomocą operatora Extract lub INSERT. Zawartość dokumentu może być używana przez bardziej ogólny schemat archiwum obiektów.

Bezpośrednie wywoływanie `Serialize` ma następujące zalety i wady:

- Nie dodano żadnych dodatkowych bajtów do archiwum przed lub po serializacji obiektu. To nie tylko powoduje, że zapisane dane są mniejsze, ale umożliwiają implementowanie `Serialize` procedur, które mogą obsługiwać wszystkie formaty plików.

- MFC jest dostrojony, więc `WriteObject` `ReadObject` implementacje i powiązane kolekcje nie będą połączone z aplikacją, chyba że potrzebny jest bardziej ogólny schemat archiwum obiektów w innym celu.

- Kod nie musi odzyskać ze starych numerów schematów. Dzięki temu kod serializacji dokumentu jest odpowiedzialny za kodowanie numerów schematu, numery wersji formatu plików lub inne identyfikujące numery używane na początku plików danych.

- Każdy obiekt, który jest serializowany z bezpośrednim wywołaniem do `Serialize` nie może używać `CArchive::GetObjectSchema` lub musi obsługiwać zwracaną wartość (uint)-1 wskazującą, że wersja była nieznana.

Ponieważ `Serialize` jest wywoływana bezpośrednio w dokumencie, nie jest to zwykle możliwe w przypadku obiektów podrzędnych dokumentu do archiwizowania odwołań do ich dokumentu nadrzędnego. Te obiekty muszą mieć jawnie wskaźnik do swojego dokumentu kontenera lub należy użyć funkcji [CArchive:: MapObject](../mfc/reference/carchive-class.md#mapobject) , aby zmapować `CDocument` wskaźnik na identyfikator PID przed zarchiwizowaniem tych wskaźników wstecznych.

Jak wspomniano wcześniej, należy zakodować informacje o wersji i klasie samodzielnie po wywołaniu `Serialize` bezpośrednio, co pozwala na późniejsze zmianę formatu przy zachowaniu zgodności z poprzednimi wersjami ze starszymi plikami. `CArchive::SerializeClass`Funkcję można wywołać jawnie przed przystąpieniem do bezpośredniego serializacji obiektu lub przed wywołaniem klasy bazowej.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
