---
description: 'Dowiedz się więcej o: Włączanie i wyłączanie usług dla dostawcy'
title: Włączanie i wyłączanie usług dla dostawcy
ms.date: 07/30/2019
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: ead2ce9b8f1e678af00bcc03140c2868986a1564
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287544"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Włączanie i wyłączanie usług dla dostawcy

Poszczególne usługi OLE DB można włączyć lub wyłączyć domyślnie dla wszystkich aplikacji, które uzyskują dostęp do jednego dostawcy. W tym celu należy dodać wpis rejestru OLEDB_SERVICES w ramach identyfikatora CLSID dostawcy, z wartością DWORD określającą usługi do włączenia lub wyłączenia, jak pokazano w poniższej tabeli.

|Domyślne usługi włączone|Wartość DWORD|
|------------------------------|-------------------|
|Wszystkie usługi z wyjątkiem kursora klienta i puli|0xfffffffa|
|Wszystkie usługi z wyjątkiem kursora klienta|0xfffffffb|
|Wszystkie usługi z wyjątkiem pul i autorejestracji|0xfffffffc|
|Wszystkie usługi z wyjątkiem pul|0xfffffffe|
|Wszystkie usługi (wartość domyślna)|0xFFFFFFFF|
|Brak usług|0x00000000|
|Bez agregacji, wszystkie usługi wyłączone|Brak wpisu rejestru OLEDB_Services|

## <a name="see-also"></a>Zobacz też

[Włączanie i wyłączanie usług OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)
