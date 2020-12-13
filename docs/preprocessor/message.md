---
description: 'Dowiedz się więcej o: pragma wiadomości'
title: message, pragma
ms.date: 08/29/2019
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: 82b8efa7e232c24402b7fb1cce0fd1e38ff8be29
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333376"
---
# <a name="message-pragma"></a>message, pragma

Wysyła literał ciągu do wyjścia standardowego bez przerywania kompilacji.

## <a name="syntax"></a>Składnia

> **komunikat #pragma (** *ciąg komunikatu* **)**

## <a name="remarks"></a>Uwagi

Typowym zastosowaniem dyrektywy pragma **wiadomości** jest wyświetlenie komunikatów informacyjnych w czasie kompilacji.

Parametr *ciągu komunikatu* może być makrem rozwijanym do literału ciągu i można łączyć takie makra z literałami ciągu w dowolnej kombinacji.

W przypadku użycia wstępnie zdefiniowanego makra w pragma **komunikatu** , makro powinno zwrócić ciąg. W przeciwnym razie konieczne będzie przekonwertowanie danych wyjściowych makra na ciąg.

Poniższy fragment kodu używa dyrektywy pragma **komunikatu** do wyświetlania komunikatów podczas kompilacji:

```cpp
// pragma_directives_message1.cpp
// compile with: /LD
#if _M_IX86 >= 500
#pragma message("_M_IX86 >= 500")
#endif

#pragma message("")

#pragma message( "Compiling " __FILE__ )
#pragma message( "Last modified on " __TIMESTAMP__ )

#pragma message("")

// with line number
#define STRING2(x) #x
#define STRING(x) STRING2(x)

#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")

#pragma message("")
```

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
