---
description: 'Dowiedz się więcej na temat: COMP'
title: compl
ms.date: 11/04/2016
api_name:
- compl
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- std::compl
- std.compl
- compl
helpviewer_keywords:
- compl function
ms.assetid: e03f6fb5-cb8b-4afa-99c0-905f4105fb34
ms.openlocfilehash: 73ce31c8d8fefc4021b797b9b9e061e616f60e5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260634"
---
# <a name="compl"></a>compl

Alternatywa dla operatora ~.

## <a name="syntax"></a>Składnia

```C
#define compl ~
```

## <a name="remarks"></a>Uwagi

Makro daje operator ~.

## <a name="example"></a>Przykład

```cpp
// iso646_compl.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 1, result;

   result = ~a;
   cout << result << endl;

   result= compl(a);
   cout << result << endl;
}
```

```Output
-2
-2
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<iso646.h>
