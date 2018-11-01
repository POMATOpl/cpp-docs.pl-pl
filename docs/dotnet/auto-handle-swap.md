---
title: auto_handle::swap
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::auto_handle::swap
- auto_handle.swap
- auto_handle::swap
- msclr..auto_handle.swap
helpviewer_keywords:
- auto_handle::swap
ms.assetid: 3ebf82d7-9b69-4a72-a22d-69b4f640f9b0
ms.openlocfilehash: 5588186ab5073dded441dadb75664eec1ee06b77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611448"
---
# <a name="autohandleswap"></a>auto_handle::swap

Zamienia obiekty z innym `auto_handle`.

## <a name="syntax"></a>Składnia

```
void swap(
   auto_handle<_element_type> % _right
);
```

#### <a name="parameters"></a>Parametry

*z _prawej*<br/>
`auto_handle` Za pomocą którego można zamienić obiektów.

## <a name="example"></a>Przykład

```
// msl_auto_handle_swap.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1 = "string one";
   auto_handle<String> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   s1.swap( s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>Wymagania

**Plik nagłówkowy** \<msclr\auto_handle.h >

**Namespace** msclr

## <a name="see-also"></a>Zobacz też

[auto_handle, składowe](../dotnet/auto-handle-members.md)<br/>
[Funkcja swap (auto_handle)](../dotnet/swap-function-auto-handle.md)