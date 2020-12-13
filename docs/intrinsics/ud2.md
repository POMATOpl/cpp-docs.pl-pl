---
description: 'Dowiedz się więcej na temat: __ud2'
title: __ud2
ms.date: 09/02/2019
f1_keywords:
- __ud2
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
ms.openlocfilehash: 2b5f0b9ffec066baa3eb2fa212dfc7baf3a6cb49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333662"
---
# <a name="__ud2"></a>__ud2

**Specyficzne dla firmy Microsoft**

Generuje niezdefiniowaną instrukcję.

## <a name="syntax"></a>Składnia

```C
void __ud2();
```

## <a name="remarks"></a>Uwagi

Podczas wykonywania niezdefiniowanej instrukcji procesor zgłasza nieprawidłowy wyjątek kodu operacji.

`__ud2`Funkcja jest równoważna z `UD2` instrukcją Machine i jest dostępna tylko w trybie jądra. Aby uzyskać więcej informacji, Wyszukaj dokument "Podręcznik Intel Architecture Software Developer, Tom 2: odwołanie do zestawu instrukcji" w witrynie [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__ud2`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="example"></a>Przykład

Poniższy przykład wykonuje niezdefiniowaną instrukcję, która wywołuje wyjątek. Program obsługi wyjątków zmieni Kod powrotu z zero na jeden.

```cpp
// __ud2_intrinsic.cpp
#include <stdio.h>
#include <intrin.h>
#include <excpt.h>
// compile with /EHa

int main() {

// Initialize the return code to 0.
int ret = 0;

// Attempt to execute an undefined instruction.
  printf("Before __ud2(). Return code = %d.\n", ret);
  __try {
  __ud2();
  }

// Catch any exceptions and set the return code to 1.
  __except(EXCEPTION_EXECUTE_HANDLER){
  printf("  In the exception handler.\n");
  ret = 1;
  }

// Report the value of the return code.
  printf("After __ud2().  Return code = %d.\n", ret);
  return ret;
}
```

```Output
Before __ud2(). Return code = 0.
  In the exception handler.
After __ud2().  Return code = 1.
```

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
