---
description: Dowiedz się więcej na temat OLE DB szablonów konsumentów (C++)
title: Szablony konsumentów OLE DB (C++)
ms.date: 10/22/2018
helpviewer_keywords:
- databases [C++], OLE DB templates
- OLE DB consumers [C++], data access
- OLE DB consumer templates [C++]
- databases [C++], consumers
ms.assetid: d3e42612-0bc0-4d65-9c32-0e8a7b219e82
ms.openlocfilehash: 6aaf935234b8ec3396c97345ca7e38a0f8d806bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317158"
---
# <a name="ole-db-consumer-templates-c"></a>Szablony konsumentów OLE DB (C++)

Szablony konsumentów OLE DB obsługują specyfikację OLE DB w wersji 2,6. (OLE DB Szablony konsumentów są testowane względem OLE DB 2,6, ale nie obsługują wszystkich interfejsów w specyfikacji). Szablony konsumentów umożliwiają zminimalizowanie ilości kodu, który należy napisać, aby zaimplementować OLE DB konsumenta. Szablony zapewniają następujące:

- Łatwy dostęp do funkcji OLE DB i łatwa integracja z bibliotekami ATL i MFC.

- Model prostego powiązania dla parametrów i kolumn bazy danych.

- Natywne typy danych C/C++ do programowania OLE DB.

Aby korzystać z szablonów OLE DB, należy zapoznać się z szablonami języka C++, COM i OLE DB. Jeśli nie znasz OLE DB, zobacz [Microsoft OLE DB Driver for SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server).

Szablony OLE DB obsługują istniejący model obiektów OLE DB zamiast dodawania nowego modelu obiektów. Klasy najwyższego poziomu w szablonach konsumentów OLE DB równolegle ze składnikami zdefiniowanymi w specyfikacji OLE DB. Projekt OLE DB szablonów konsumentów zawiera zaawansowane funkcje, takie jak wiele metod dostępu w zestawie wierszy. Użycie szablonów i wielokrotne dziedziczenie sprawia, że biblioteka jest niewielka i elastyczna.

## <a name="how-ole-db-consumers-access-data"></a>Jak OLE DB konsumenci uzyskują dostęp do danych

Konsumenci używają kilku rodzajów obiektów, które są opisane w następujących tematach:

- [Źródła danych i sesje](../../data/oledb/data-sources-and-sessions.md)

- [Metody dostępu i zestawy wierszy](../../data/oledb/accessors-and-rowsets.md)

- [Polecenia i tabele](../../data/oledb/commands-and-tables.md)

- [Rekordy użytkowników](../../data/oledb/user-records.md)

Przed zakończeniem działania konsumenta należy najpierw wybrać dostawcę OLE DB, który jest odpowiedni dla typu bazy danych, do której należy uzyskać dostęp (na przykład SQL, Oracle, ODBC i MSDS). W tym celu zwykle używany jest moduł wyliczający (zobacz [CEnumerator](../../data/oledb/cenumerator-class.md) , jak wspomniano w obszarze [źródła danych i sesje](../../data/oledb/data-sources-and-sessions.md)).

[Obiekt źródła danych](../../data/oledb/data-sources-and-sessions.md) zawiera informacje o połączeniu niezbędne do nawiązania połączenia z wybranym źródłem danych. Obiekt źródła danych zawiera również informacje uwierzytelniania (takie jak nazwy logowania i hasła), które służą do nadawania użytkownikom uprawnienia dostępu do źródła danych. Obiekt źródła danych nawiązuje połączenie z bazą danych, a następnie tworzy co najmniej jeden obiekt sesji. Każdy [obiekt sesji](../../data/oledb/data-sources-and-sessions.md) zarządza swoimi własnymi interakcjami z bazą danych (czyli badaniem i pobieraniem danych) i wykonuje te transakcje niezależnie od innych istniejących sesji.

Sesja tworzy zestaw wierszy i obiekty poleceń. [Obiekt Command](../../data/oledb/commands-and-tables.md) umożliwia użytkownikom współpracującie z bazą danych, na przykład za pomocą poleceń SQL. [Obiekt zestawu wierszy](../../data/oledb/accessors-and-rowsets.md) to zestaw danych, za pomocą którego można nawigować i w których można je [aktualizować, usuwać i wstawiać wiersze](../../data/oledb/updating-rowsets.md).

Odbiorca OLE DB wiąże kolumny w tabelach bazy danych ze zmiennymi lokalnymi; w tym celu używa [metody dostępu](../../data/oledb/accessors-and-rowsets.md), która zawiera mapę sposobu przechowywania danych w ramach konsumenta. Mapa składa się z zestawu powiązań między kolumnami tabeli i buforami lokalnymi (zmiennymi) w aplikacji konsumenta.

Jednym ważnym pojęciem podczas pracy z klientami jest zadeklarowanie dwóch klas w odbiorcy: [Klasa polecenia (lub tabeli)](../../data/oledb/commands-and-tables.md) i [Klasa rekordu użytkownika](../../data/oledb/user-records.md). Dostęp do zestawu wierszy można uzyskać za pomocą klasy Command (lub Table), która dziedziczy z klasy akcesora i klasy zestawu wierszy. Klasa rekordu użytkownika zawiera wcześniej opisaną mapę powiązania zestawu wierszy.

Aby uzyskać więcej informacji, zobacz następujące tematy:

- [Tworzenie klienta OLE DB](../../data/oledb/creating-an-ole-db-consumer.md)

- [Typowe scenariusze klientów OLE DB (przykłady)](../../data/oledb/working-with-ole-db-consumer-templates.md)

## <a name="see-also"></a>Zobacz też

[Programowanie OLE DB](../../data/oledb/ole-db-programming.md)<br/>
[Dostęp do danych](../data-access-in-cpp.md)<br/>
[Dokumentacja zestawu SDK OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[Sterownik OLE DB firmy Microsoft dla SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server)
