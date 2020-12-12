---
description: Dowiedz się więcej na temat interfejsów obiektów poleceń
title: Interfejsy obiektu polecenia
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 07dce6a71e7afd3a47c63942d48dd78d758103f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307525"
---
# <a name="command-object-interfaces"></a>Interfejsy obiektu polecenia

Obiekt Command używa `IAccessor` interfejsu do określania powiązań parametrów. Klient wywołuje `IAccessor::CreateAccessor` , przekazując do tablicy `DBBINDING` struktury. `DBBINDING` zawiera informacje o powiązaniach kolumn (takich jak typ i długość). Dostawca otrzymuje struktury i decyduje o sposobie transferu danych oraz o tym, czy konwersje są wymagane.

`ICommandText`Interfejs pozwala określić polecenie tekstowe. `ICommandProperties`Interfejs obsługuje wszystkie właściwości polecenia.

## <a name="see-also"></a>Zobacz też

[Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
