---
title: and_eq | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- and_eq
- std.and_eq
- std::and_eq
dev_langs:
- C++
helpviewer_keywords:
- and_eq macro
ms.assetid: 11091772-e359-4c2b-95c6-00841ac04354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc20f03a085c9a321fd68f683b6f928991fa559f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392747"
---
# <a name="andeq"></a>and_eq

Zamiast & = — operator.

## <a name="syntax"></a>Składnia

```C

#define and_eq &=

```

## <a name="remarks"></a>Uwagi

Makro daje operator & =.

## <a name="example"></a>Przykład

```cpp
// iso646_and_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 3, b = 2, result;

   result= a &= b;
   cout << result << endl;

   result= a and_eq b;
   cout << result << endl;
}
```

```Output
2
2
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<iso646.h >