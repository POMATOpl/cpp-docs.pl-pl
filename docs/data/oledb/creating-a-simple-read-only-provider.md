---
description: Dowiedz się więcej na temat tworzenia prostego dostawcy Read-Only
title: Tworzenie prostego dostawcy tylko do odczytu
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: 1904e850bc6a681e13e4799a2822963932ad9dfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323223"
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

## <a name="see-also"></a>Zobacz też

[Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
