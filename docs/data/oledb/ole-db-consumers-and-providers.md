---
description: 'Dowiedz się więcej o: OLE DB użytkowników i dostawców'
title: Konsumenci i dostawcy OLE DB
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
ms.openlocfilehash: dedcbe7837cf7fad5bc9db8832e34edd3859a02b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317145"
---
# <a name="ole-db-consumers-and-providers"></a>Konsumenci i dostawcy OLE DB

Architektura OLE DB korzysta z modelu odbiorców i dostawców. Odbiorca wysyła żądania dotyczące danych. Dostawca reaguje na te żądania przez umieszczenie danych w formacie tabelarycznym i zwrócenie go do konsumenta. Każde wywołanie, które może zostać wykonane przez konsumenta, musi zostać zaimplementowane w dostawcy.

Zdefiniowane technicznie, konsument to dowolny system lub kod aplikacji (niekoniecznie składnik OLE DB), który uzyskuje dostęp do danych za pomocą interfejsów OLE DB. Interfejsy są zaimplementowane w dostawcy. Dostawca jest dowolnym składnikiem oprogramowania, który implementuje interfejsy OLE DB, aby hermetyzować dostęp do danych i uwidaczniać je innym obiektom (czyli konsumentom).

W przypadku ról odbiorca wywołuje metody dotyczące interfejsów OLE DB; Dostawca OLE DB implementuje wymaganych interfejsów OLE DB.

OLE DB unika warunków klienta i serwera, ponieważ te role nie zawsze mają sens, szczególnie w przypadku n-warstwowa. Ze względu na to, że konsument może być składnikiem w warstwie, która obsługuje inny składnik, aby wywołać go, składnik klienta mógłby być mylący. Ponadto dostawca czasami działa podobnie jak w przypadku sterownika bazy danych niż serwer.

## <a name="see-also"></a>Zobacz też

[Programowanie OLE DB](../../data/oledb/ole-db-programming.md)<br/>
[Omówienie programowania OLE DB](../../data/oledb/ole-db-programming-overview.md)
