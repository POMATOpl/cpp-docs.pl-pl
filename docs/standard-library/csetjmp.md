---
description: 'Dowiedz się więcej na temat: &lt; csetjmp&gt;'
title: '&lt;csetjmp&gt;'
ms.date: 11/04/2016
f1_keywords:
- <csetjmp>
helpviewer_keywords:
- csetjmp header
ms.assetid: 8f21fddd-5e9b-4219-a848-581cdd3569d9
ms.openlocfilehash: ebd3acefbdf96c8dd2b0cba569e7cd2ffc128d31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324777"
---
# <a name="ltcsetjmpgt"></a>&lt;csetjmp&gt;

Zawiera nagłówek standardowej biblioteki C \<setjmp.h> i dodaje skojarzone nazwy do `std` przestrzeni nazw.

## <a name="syntax"></a>Składnia

```cpp
#include <csetjmp>

using jmp_buf = see below;
```

## <a name="functions"></a>Funkcje

```cpp
[[noreturn]] void longjmp(jmp_buf env, int val);
```

## <a name="macros"></a>Makra

```cpp
#define setjmp(env)
```

## <a name="remarks"></a>Uwagi

Dołączenie tego nagłówka zapewnia, że nazwy zadeklarowane za pomocą zewnętrznego powiązania w nagłówku standardowej biblioteki C są deklarowane w `std` przestrzeni nazw.

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
