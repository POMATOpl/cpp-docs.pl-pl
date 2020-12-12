---
description: 'Dowiedz się więcej na temat: Redystrybuowanie składników ODBC do klientów'
title: Redystrybucja składników ODBC wśród klientów
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
ms.openlocfilehash: 02840156d648507065e0cadb1b8fa2b9c8146a7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204319"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>Redystrybucja składników ODBC wśród klientów

Jeśli dołączysz funkcjonalność programów administratora ODBC do aplikacji, musisz również przekazać użytkownikom pliki, które uruchamiają te programy. Te pliki ODBC znajdują się w Visual C++ katalogu \OS\System dysku CD-ROM. Plik Redistrb. wri i Umowa licencyjna w tym samym katalogu zawierają listę plików ODBC, które można rozpowszechniać.

Zapoznaj się z dokumentacją dotyczącą wszelkich sterowników ODBC, które planujesz wysłać. Należy określić, które biblioteki DLL i inne pliki mają być dostarczane. Należy również zapoznać [się z redystrybucją składników ODBC do klientów](../../data/odbc/redistributing-odbc-components-to-your-customers.md), co wyjaśnia, jak ponownie dystrybuować składniki ODBC.

Ponadto należy w większości przypadków dołączyć jeden plik. Odbccr32.dll jest biblioteką kursorów ODBC. Ta biblioteka zapewnia poziom 1 Sterowniki możliwości przewijania do przodu i do tyłu. Oferuje również możliwość obsługi migawek. Aby uzyskać więcej informacji na temat biblioteki kursora ODBC, zobacz [ODBC: Biblioteka kursorów ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).

Poniższe tematy zawierają więcej informacji na temat używania ODBC z klasami baz danych:

- [ODBC: Biblioteka kursorów ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: Konfigurowanie źródła danych ODBC](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: bezpośrednie wywoływanie funkcji ODBC API](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje dotyczące ODBC](../../data/odbc/odbc-basics.md)<br/>
[Administrator ODBC](../../data/odbc/odbc-administrator.md)
