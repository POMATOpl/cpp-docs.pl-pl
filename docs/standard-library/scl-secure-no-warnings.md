---
description: 'Dowiedz się więcej na temat: _SCL_SECURE_NO_WARNINGS'
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: 383aeed0bdedc4830076248100c8cf0a1acf34b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187926"
---
# <a name="_scl_secure_no_warnings"></a>_SCL_SECURE_NO_WARNINGS

Wywołanie dowolnych potencjalnie niebezpiecznych metod w standardowej bibliotece języka C++ powoduje [Ostrzeżenie kompilatora (poziom 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Aby wyłączyć to ostrzeżenie, zdefiniuj _SCL_SECURE_NO_WARNINGS makro w kodzie:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

Jeśli używasz prekompilowanych nagłówków, umieść tę dyrektywę we wstępnie skompilowanym pliku nagłówkowym przed uwzględnieniem dowolnej biblioteki środowiska uruchomieniowego języka C lub nagłówków biblioteki standardowej. Jeśli umieścisz ją w pliku kodu źródłowego przed dołączeniem prekompilowanego pliku nagłówkowego, zostanie on zignorowany przez kompilator.

## <a name="remarks"></a>Uwagi

Inne sposoby wyłączenia ostrzeżenia C4996 obejmują:

- Przy użyciu [/d (Definicje preprocesora)](../build/reference/d-preprocessor-definitions.md) opcja kompilatora:

   > CL/D_SCL_SECURE_NO_WARNINGS [inne opcje kompilatora] plik. cpp

- Przy użyciu [/w](../build/reference/compiler-option-warning-level.md) opcji kompilatora:

   > CL/wd4996 [inne opcje kompilatora] plik. cpp

- Za pomocą dyrektywy [ostrzegawczej #pragma](../preprocessor/warning.md) :

   ```cpp
   #pragma warning(disable:4996)
   ```

Ponadto można ręcznie zmienić poziom ostrzeżeń C4996 z opcją **/w \<l> \<n>** kompilatora. Na przykład, aby ustawić ostrzeżenie C4996 na poziomie 4:

> CL/w44996 [inne opcje kompilatora] plik. cpp

Aby uzyskać więcej informacji, zobacz [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/we,/wo,/WV,/WX (poziom ostrzeżeń)](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Zobacz też

[Bezpieczne biblioteki: standardowa biblioteka C++](../standard-library/safe-libraries-cpp-standard-library.md)
