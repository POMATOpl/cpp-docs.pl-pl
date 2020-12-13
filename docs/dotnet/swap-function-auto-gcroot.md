---
description: Dowiedz się więcej o funkcji swap (auto_gcroot)
title: Funkcja swap (auto_gcroot)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::swap
- msclr.swap
helpviewer_keywords:
- swap function
ms.assetid: 2fe8146b-a7f7-445a-9ae9-53b5556be701
ms.openlocfilehash: 61f4b8a2a1f694533dc0bfbb0e4a963324bc91d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335304"
---
# <a name="swap-function-auto_gcroot"></a>Funkcja swap (auto_gcroot)

Zamienia obiekty między nimi `auto_gcroot` .

## <a name="syntax"></a>Składnia

```
template<typename _element_type>
void swap(
   auto_gcroot<_element_type> & _left,
   auto_gcroot<_element_type> & _right
);
```

#### <a name="parameters"></a>Parametry

*_left*<br/>
A `auto_gcroot` .

*_right*<br/>
Inny `auto_gcroot` .

## <a name="example"></a>Przykład

```cpp
// msl_swap_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s1 = "string one";
   auto_gcroot<String^> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   swap( s1, s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>Wymagania

**Plik nagłówka**\<msclr\auto_gcroot.h>

Msclr **przestrzeni nazw**

## <a name="see-also"></a>Zobacz też

[auto_gcroot](../dotnet/auto-gcroot.md)<br/>
[auto_gcroot::swap](./auto-gcroot-class.md#swap)
