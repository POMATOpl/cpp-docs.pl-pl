---
title: Tworzenie prostego dostawcy tylko do odczytu
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: c7c6c5bb2691a110a6368decd875f5a5a06b11b5
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919192"
---
# <a name="creating-a-simple-read-only-provider"></a>Tworzenie prostego dostawcy tylko do odczytu

::: moniker range="msvc-160"

Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

::: moniker-end

::: moniker range="<=msvc-150"

Po utworzeniu dostawcy OLE DB przy użyciu **Kreatora projektu ATL** i **kreatora dostawcy ATL OLE DB** można dodać inne funkcje, które mają być obsługiwane. Rozpocznij projektowanie dostawcy, sprawdzając, jakiego rodzaju dane będą wysyłane do konsumenta i w jakich warunkach. Szczególnie ważne jest, aby określić, czy należy obsługiwać polecenia, transakcje i inne opcjonalne obiekty. Dobrym etapem projektowania jest przyspieszenie wdrożenia i przetestowania.

Przykład jest prezentowany w dwóch częściach:

- Pierwsza część pokazuje, jak [utworzyć prostego dostawcę tylko do odczytu](../../data/oledb/implementing-the-simple-read-only-provider.md) , który odczytuje parę ciągów.

- Druga część pokazuje [, jak zwiększyć prostego dostawcę tylko do odczytu](../../data/oledb/enhancing-the-simple-read-only-provider.md) przez dodanie `IRowsetLocate` interfejsu.

::: moniker-end

## <a name="see-also"></a>Zobacz także

[Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
