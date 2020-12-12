---
description: 'Dowiedz się więcej o programie: domeny aplikacji i Visual C++'
title: Domeny aplikacji i program Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 55f02aec7b3b2d23f10ae9142dba7c61ff60683f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282825"
---
# <a name="application-domains-and-visual-c"></a>Domeny aplikacji i program Visual C++

Jeśli masz `__clrcall` funkcję wirtualną, to zostanie wydana domena aplikacji (AppDomain). W przypadku utworzenia obiektu w jednej domenie aplikacji można wywołać tylko funkcję wirtualną z poziomu tej domeny aplikacji. W trybie mieszanym (**/CLR**) będziesz mieć dla poszczególnych procesów tablice metod, jeśli typ nie ma żadnych `__clrcall` funkcji wirtualnych. **/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Aby uzyskać więcej informacji, zobacz:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [podstawowych](../cpp/process.md)

## <a name="see-also"></a>Zobacz też

- [Zestawy mieszane (natywne i zarządzane)](../dotnet/mixed-native-and-managed-assemblies.md)
