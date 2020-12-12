---
description: 'Dowiedz się więcej o: błąd kompilatora C3099'
title: Błąd kompilatora C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: d065edd58df1e9196dc6aa31cfd4fb263f062f1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116226"
---
# <a name="compiler-error-c3099"></a>Błąd kompilatora C3099

"słowo kluczowe": Użyj [System:: AttributeUsageAttribute] dla atrybutów zarządzanych; Użyj [Windows:: Foundation:: Metadata:: AttributeUsageAttribute] dla atrybutów WinRT

Użyj <xref:System.AttributeUsageAttribute> , aby zadeklarować atrybuty **/CLR** . Użyj `Windows::Foundation::Metadata::AttributeUsageAttribute` , aby zadeklarować atrybuty środowisko wykonawcze systemu Windows.

Aby uzyskać więcej informacji na temat atrybutów/CLR, zobacz [atrybuty zdefiniowane przez użytkownika](../../extensions/user-defined-attributes-cpp-component-extensions.md). Aby uzyskać obsługiwane atrybuty w środowisko wykonawcze systemu Windows, zobacz [przestrzeń nazw Windows. Foundation. Metadata](/uwp/api/windows.foundation.metadata)

## <a name="example"></a>Przykład

Poniższy przykład generuje C3099 i pokazuje, jak rozwiązać ten problem.

```cpp
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```
