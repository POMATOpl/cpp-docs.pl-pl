---
description: 'Dowiedz się więcej o: zatopienia Delay-Loaded Importy'
title: Zrzucanie importów załadowanych z opóźnieniem
ms.date: 11/04/2016
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
ms.openlocfilehash: c57ff6bb4a3dce16b4cb1eb85fdffff4ef272396
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201082"
---
# <a name="dumping-delay-loaded-imports"></a>Zrzucanie importów załadowanych z opóźnieniem

Importy z opóźnieniem mogą być zrzucane przy użyciu [polecenia DUMPBIN/Imports —](imports-dumpbin.md) i wyświetlane z nieco różnymi informacjami niż standardowe Importy. Są one podzielone na własne części dumpingu/Imports — i są jawnie oznaczone jako Importy ładowane z opóźnieniem. Jeśli na obrazie znajdują się informacje o zwolnieniu, zanotowano ich wypróbowanie. Jeśli istnieją informacje o powiązaniu, sygnatura czasowa i Data docelowej biblioteki DLL jest zapisywana wraz z adresami związanymi z importami.

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
