---
description: 'Dowiedz się więcej o: Instrukcje: Dodawanie natywnej biblioteki DLL do globalnej pamięci podręcznej zestawów'
title: 'Porady: dodawanie natywnej biblioteki DLL do globalnej pamięci podręcznej zestawów'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: 267bc2f08fdd40da03b71222c48786ab7cc150fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335402"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Porady: dodawanie natywnej biblioteki DLL do globalnej pamięci podręcznej zestawów

Można umieścić natywną bibliotekę DLL (nie COM) w globalnej pamięci podręcznej zestawów.

## <a name="example"></a>Przykład

**/ASSEMBLYLINKRESOURCE** umożliwia osadzenie NATYWNEJ biblioteki DLL w zestawie.

Aby uzyskać więcej informacji, zobacz [/ASSEMBLYLINKRESOURCE (link do zasobów .NET Framework)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>Zobacz też

[Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
