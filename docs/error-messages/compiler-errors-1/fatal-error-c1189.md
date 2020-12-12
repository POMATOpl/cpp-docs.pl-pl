---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1189'
title: Błąd krytyczny C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 4e71903c6567aedf85de81db59b66e45684d8507
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123594"
---
# <a name="fatal-error-c1189"></a>Błąd krytyczny C1189

> **\# błąd:** *podany przez użytkownika komunikat o błędzie*

## <a name="remarks"></a>Uwagi

C1189 jest generowana przez `#error` dyrektywę. Deweloper, który koduje dyrektywę określa tekst komunikatu o błędzie. Aby uzyskać więcej informacji, zobacz [#error dyrektywie (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C1189. W przykładzie deweloper wystawia niestandardowy komunikat o błędzie, ponieważ `_WIN32` nie zdefiniowano identyfikatora:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Zobacz też

[#define — dyrektywa (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
