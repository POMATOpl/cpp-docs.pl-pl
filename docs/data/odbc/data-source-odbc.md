---
description: 'Dowiedz się więcej na temat: Źródło danych (ODBC)'
title: Źródło danych (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: 655ba48414a733c6f2704d51c0e2bf1d4edf3ff4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255681"
---
# <a name="data-source-odbc"></a>Źródło danych (ODBC)

Ten temat dotyczy klas MFC ODBC.

W terminologii bazy danych, źródłem danych jest określony zestaw danych, informacje wymagane do uzyskania dostępu do tych danych oraz lokalizacja źródła danych, które można opisać przy użyciu nazwy źródła danych. Aby można było korzystać z klasy [CDatabase](../../mfc/reference/cdatabase-class.md), źródło danych musi być skonfigurowane za pośrednictwem administratora Open Database Connectivity (ODBC). Przykłady źródeł danych obejmują zdalną bazę danych działającą w Microsoft SQL Server przez sieć lub plik programu Microsoft Access w katalogu lokalnym. Z poziomu aplikacji możesz uzyskać dostęp do dowolnego źródła danych, dla którego masz sterownik ODBC.

W aplikacji można jednocześnie korzystać z co najmniej jednego źródła danych reprezentowanego przez `CDatabase` obiekt. Można także mieć wiele jednoczesnych połączeń z dowolnym źródłem danych. Możesz połączyć się ze zdalnym i lokalnymi źródłami danych, w zależności od zainstalowanych sterowników i możliwości sterowników ODBC. Aby uzyskać więcej informacji na temat źródeł danych i administratora ODBC, zobacz [ODBC](../../data/odbc/odbc-basics.md) i [administrator ODBC](../../data/odbc/odbc-administrator.md).

W poniższych tematach opisano więcej informacji o źródłach danych:

- [Źródło danych: Zarządzanie połączeniami (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [Źródło danych: określanie schematu źródła danych (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>Zobacz też

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
