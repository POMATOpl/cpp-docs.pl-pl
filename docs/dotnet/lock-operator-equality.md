---
title: Lock::operator, wartość == | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
dev_langs:
- C++
helpviewer_keywords:
- lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f60cf71305731391d03763810775eaf7f8e5fd7e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411537"
---
# <a name="lockoperator"></a>lock::operator==

Operator równości.

## <a name="syntax"></a>Składnia

```
template<class T> bool operator==(
   T t
);
```

#### <a name="parameters"></a>Parametry

*t*<br/>
Obiekt do porównania dla równości.

## <a name="return-value"></a>Wartość zwracana

Zwraca `true` Jeśli `t` jest taka sama jak obiektu blokady `false` inaczej.

## <a name="example"></a>Przykład

```
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="requirements"></a>Wymagania

**Plik nagłówkowy** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>Zobacz też

[lock, składowe](../dotnet/lock-members.md)<br/>
[lock::operator!=](../dotnet/lock-operator-inequality.md)