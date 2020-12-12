---
description: 'Dowiedz się więcej o: agregacji'
title: Agregacja
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: fb02dd399020f8768fcdb3cc86687578e51cb3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166099"
---
# <a name="aggregation"></a>Agregacja

Istnieją przypadki, w których implementujący obiekt chce skorzystać z usług oferowanych przez inny, wstępnie skonstruowany obiekt. Ponadto chcemy, aby ten drugi obiekt pojawił się jako naturalna część pierwszego. COM realizuje oba te cele za poorednictwem zawierania i agregacji.

Agregacja oznacza, że obiekt zawierający (zewnętrzny) tworzy zawarty obiekt (wewnętrzny) jako część procesu tworzenia, a interfejsy obiektu wewnętrznego są uwidaczniane przez zewnętrzny. Obiekt umożliwia możliwość agregowania. Jeśli tak, to musi przestrzegać pewnych reguł, aby agregacja działała prawidłowo.

Przede wszystkim `IUnknown` wywołania metody na zawartym obiekcie muszą delegować do obiektu zawierającego.

## <a name="see-also"></a>Zobacz też

[Wprowadzenie do modelu COM](../atl/introduction-to-com.md)<br/>
[Używanie obiektów](/windows/win32/com/reusing-objects)
