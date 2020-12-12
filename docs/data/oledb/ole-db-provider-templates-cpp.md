---
description: 'Dowiedz się więcej o: OLE DB szablonów dostawców (C++)'
title: Szablony dostawców OLE DB (C++)
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
ms.openlocfilehash: 8706fcd9467e6d184633917d7c83ac81ad137b9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286920"
---
# <a name="ole-db-provider-templates-c"></a>Szablony dostawców OLE DB (C++)

OLE DB jest ważną częścią strategii uniwersalnego dostępu do danych firmy Microsoft. Projekt OLE DB umożliwia dostęp do danych o wysokiej wydajności z dowolnego źródła danych. Wszystkie dane tabelaryczne są widoczne za pośrednictwem OLE DB niezależnie od tego, czy pochodzą z bazy danych. Elastyczność zapewnia ogromną ilość mocy.

Jak wyjaśniono w [OLE DB konsumenci i dostawcy](../../data/oledb/ole-db-consumers-and-providers.md), OLE DB używa koncepcji odbiorców i dostawców. Odbiorca wysyła żądania dotyczące danych; Dostawca zwraca dane do konsumenta w formacie tabelarycznym. Z perspektywy programowania, najważniejsze implikacje tego modelu polega na tym, że dostawca musi zaimplementować każde wywołanie, które może wykonać konsument.

## <a name="what-is-a-provider"></a>Co to jest dostawca?

Dostawca OLE DB to zbiór obiektów COM, które obsługują wywołania interfejsów z obiektu odbiorcy, a następnie przesyłają dane w formacie tabelarycznym z trwałego źródła (nazywanego magazynem danych) do konsumenta.

Dostawcy mogą być proste lub złożone. Dostawca może obsłużyć minimalną liczbę funkcji lub rozwiniętąą jakości produkcyjnej, implementując więcej interfejsów. Dostawca może zwrócić tabelę, zezwolić klientowi na określenie formatu tej tabeli i wykonywanie operacji na tych danych.

Każdy dostawca implementuje standardowy zestaw obiektów COM do obsługi żądań od klienta, w standardowym znaczeniu, że każdy OLE DB konsument może uzyskać dostęp do danych z dowolnego dostawcy, niezależnie od języka (na przykład C++ i Basic).

Każdy obiekt COM zawiera kilka interfejsów, niektóre z nich są wymagane i niektóre z nich są opcjonalne. Implementując interfejsy obowiązkowe, dostawca gwarantuje minimalny poziom funkcjonalności (nazywany zgodnością), który może być używany przez dowolnego klienta. Dostawca może zaimplementować opcjonalne interfejsy w celu zapewnienia dodatkowych funkcji. [Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md) opisuje te interfejsy szczegółowo. Klient powinien zawsze wywołać, `QueryInterface` Aby określić, czy dostawca obsługuje dany interfejs.

## <a name="ole-db-specification-level-support"></a>Obsługa poziomu specyfikacji OLE DB

Szablony dostawcy OLE DB obsługują specyfikację OLE DB w wersji 2,7. Korzystając z szablonów dostawców OLE DB, można zaimplementować zgodnego poziomu 0 dostawcy. `Provider`Przykładowo używa szablonów do wdrożenia serwera poleceń innych niż SQL (MS-DOS), który wykonuje polecenie DOS dir, aby wykonać zapytanie o system plików. `Provider`Przykład zwraca informacje dotyczące katalogu w zestawie wierszy, który jest standardowym mechanizmem OLE DB do zwracania danych tabelarycznych.

Najprostszym typem dostawcy obsługiwanym przez szablony OLE DB jest dostawca tylko do odczytu bez poleceń. Obsługiwane są również dostawcy z poleceniami, w tym funkcje tworzenia zakładek i odczytu i zapisu. Można zaimplementować dostawcę odczytu/zapisu, pisząc dodatkowy kod. Dynamiczne zestawy wierszy i transakcje nie są obsługiwane przez bieżącą wersję, ale można je dodać, jeśli chcesz.

## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>Kiedy należy utworzyć dostawcę OLE DB?

Nie zawsze musisz tworzyć własnego dostawcę; Firma Microsoft udostępnia kilku dostawców w pakiecie, w oknie dialogowym **Właściwości łącza danych** w Visual C++. Głównym powodem tworzenia dostawcy OLE DB jest skorzystanie z strategii uniwersalnego dostępu do danych. Poniżej przedstawiono niektóre zalety wykonywania takich czynności:

- Uzyskiwanie dostępu do danych za pomocą dowolnego języka, takiego jak C++, Basic i Visual Basic Scripting Edition. Umożliwia ona różnym programistom w organizacji uzyskiwanie dostępu do tych samych danych w taki sam sposób, niezależnie od używanego języka.

- Otwórz dane w innych źródłach danych, takich jak SQL Server, Excel i Access. Może to być przydatne, jeśli chcesz przesłać dane między różnymi formatami.

- Uczestnictwo w operacjach ze źródeł danych krzyżowych (heterogenicznych). Może to być efektywny sposób magazynowania danych. Korzystając z dostawców OLE DB, można przechowywać dane w formacie natywnym i nadal uzyskiwać do nich dostęp w prostej operacji.

- Dodawanie do danych dodatkowych funkcji, takich jak przetwarzanie zapytań.

- Zwiększenie wydajności dostępu do danych przez kontrolowanie sposobu manipulowania nimi.

- Zwiększenie niezawodności. Jeśli posiadasz własny format danych, do którego może uzyskać dostęp tylko jeden programista, jest to ryzykowne. Korzystając z OLE DB dostawców, można otworzyć ten format własności dla wszystkich programistów.

## <a name="read-only-and-updatable-providers"></a>Dostawcy Read-Only i Aktualizowalni

Dostawcy mogą się znacznie różnić w zależności od złożoności i funkcjonalności. Warto przydzielić dostawcy do kategorii dostawcy tylko do odczytu i aktualizowalnych dostawców:

- Visual C++ 6,0 obsługiwane są tylko dostawcy tylko do odczytu. [Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md) omawia sposób tworzenia dostawcy tylko do odczytu.
- Visual C++ obsługuje aktualizowalnych dostawców, które mogą aktualizować (zapisywać w) magazyn danych. Aby uzyskać informacje na temat aktualizowalnych dostawców, zobacz [Tworzenie aktualizowalnego dostawcy](../../data/oledb/creating-an-updatable-provider.md). Przykładowy [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) jest przykładem aktualizowalnego dostawcy.

Aby uzyskać więcej informacji, zobacz:

- [Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)

- [Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)

- [Programowanie OLE DB](../../data/oledb/ole-db-programming.md)

## <a name="see-also"></a>Zobacz też

[Dostęp do danych](../data-access-in-cpp.md)<br/>
[Dokumentacja zestawu SDK OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[Dokumentacja programisty OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)<br/>
