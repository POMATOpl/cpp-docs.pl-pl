---
description: 'Dowiedz się więcej na temat: unikanie wyjątków przy zamykaniu środowiska CLR podczas używania obiektów COM skompilowanych przy użyciu opcji/CLR'
title: Unikanie wyjątków zgłoszonych przez obiekty COM skompilowane za pomocą-CLR
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: 899f7905aafcf1bff92e37ee70253e74759b3f57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282617"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Unikanie wyjątków przy zamykaniu środowiska CLR w przypadku konsumowania obiektów COM skompilowanych przy użyciu opcji /clr

Po przejściu środowiska uruchomieniowego języka wspólnego (CLR) do trybu zamykania funkcje natywne mają ograniczony dostęp do usług CLR. Podczas próby wywołania wydania dla obiektu COM skompilowanego za pomocą **/CLR**, przejścia CLR do kodu natywnego, a następnie przejścia do kodu zarządzanego w celu obsługi elementu IUnknown:: Release (zdefiniowanego w kodzie zarządzanym). Środowisko CLR uniemożliwia wywołanie z powrotem do kodu zarządzanego, ponieważ jest w trybie zamykania.

Aby rozwiązać ten problem, upewnij się, że destruktory wywołane z metod wydania zawierają tylko kod natywny.

## <a name="see-also"></a>Zobacz też

[Zestawy mieszane (natywne i zarządzane)](../dotnet/mixed-native-and-managed-assemblies.md)
