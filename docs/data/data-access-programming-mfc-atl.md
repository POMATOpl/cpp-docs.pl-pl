---
description: 'Dowiedz się więcej o programie: Programowanie dostępu do danych (MFC/ATL)'
title: Programowanie dostępu do danych (MFC-ATL)
ms.date: 11/16/2018
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
ms.openlocfilehash: 7785eb65bd26c6c8bf4b60d5a8a919097627f20c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136477"
---
# <a name="data-access-programming-mfcatl"></a>Programowanie dostępu do danych (MFC/ATL)

W ciągu lat Visual C++ zapewniał kilka sposobów pracy z bazami danych. W firmie 2011 Microsoft ogłosiła, że jest on wyrównany do Open Database Connectivity (ODBC) jako preferowana technologia uzyskiwania dostępu do SQL Server produktów z kodu natywnego. ODBC jest standardem branżowym, a przy jego użyciu uzyskuje maksymalną przenośność kodu na wielu platformach i źródłach danych. Większość produktów bazy danych SQL i wiele produktów NoSQL obsługują ODBC. ODBC można używać bezpośrednio, wywołując interfejsy API ODBC niskiego poziomu, lub można użyć klas otoki ODBC MFC lub biblioteki otoki C++ innej firmy.

OLE DB to interfejs API o niskim poziomie i wysokiej wydajności oparty na specyfikacji COM, który jest obsługiwany tylko w systemie Windows. Użyj OLE DB, jeśli program uzyskuje dostęp do [połączonych serwerów](/sql/relational-databases/linked-servers/linked-servers-database-engine). ATL oferuje OLE DB szablonów, które ułatwiają tworzenie niestandardowych dostawców OLE DB i klientów. Najnowszego dostawcę Microsoft SQL Server można znaleźć w dokumentacji dotyczącej [sterownika OLE DB na potrzeby SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server).

## <a name="porting-data-applications"></a>Przenoszenie aplikacji danych

Jeśli Starsza aplikacja używa OLE DB lub interfejsu ADO wyższego poziomu do nawiązywania połączenia z SQL Server, należy rozważyć Migrowanie do najnowszego [sterownika OLE DB dla SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server) , aby móc korzystać z najnowszych funkcji SQL Server. Alternatywnie, jeśli nie jest wymagana przenośność międzyplatformowa lub Najnowsza SQL Server funkcje, możesz użyć dostawcy OLE DB firmy Microsoft dla ODBC (MSDASQL).  MSDASQL umożliwia aplikacjom, które są oparte na OLE DB i ADO (które używają wewnętrznie OLEDB) do uzyskiwania dostępu do źródeł danych za pośrednictwem sterownika ODBC. Podobnie jak w przypadku dowolnej warstwy tłumaczenia MSDASQL może mieć wpływ na wydajność bazy danych. Należy przetestować, aby określić, czy wpływ na działanie jest istotny dla aplikacji. MSDASQL są dostarczane z systemem operacyjnym Windows, a system Windows Server 2008 & Windows Vista z dodatkiem SP1 to pierwsze wersje systemu Windows, które obejmują 64-bitową wersję technologii.

Jeśli aplikacja C++ łączy się z SQL Server lub Azure SQL Database za pośrednictwem ODBC, powinien korzystać z najnowszego [sterownika ODBC](/sql/connect/odbc/download-odbc-driver-for-sql-server).

W przypadku korzystania z języka C++/CLI można nadal używać ADO.NET jako zawsze. Aby uzyskać więcej informacji, zobacz [dostęp do danych za pomocą ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)i [Uzyskiwanie dostępu do danych w programie Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).

- Oprócz klas otoki ODBC, MFC udostępnia również klasy otoki obiektów dostępu do danych (DAO) do łączenia się z bazami danych programu Access.  Jednak obiekt DAO jest przestarzały. Należy uaktualnić dowolny kod oparty na CDaoDatabase lub CDaoRecordset.

Aby uzyskać więcej informacji na temat historii technologii dostępu do danych w systemie Microsoft Windows, zobacz [Microsoft Data Access Components (Wikipedia)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>Zobacz też

[Dostęp do danych](data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
