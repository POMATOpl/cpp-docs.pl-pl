---
description: 'Dowiedz się więcej o: dostęp do argumentów'
title: Dostęp do argumentów
ms.date: 04/04/2018
f1_keywords:
- c.arguments
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
ms.openlocfilehash: f62ac2bc4ae895afe763d0a0a4caa32601e82713
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221868"
---
# <a name="argument-access"></a>Dostęp do argumentów

Makra **va_arg**, **va_end** i **va_start** zapewniają dostęp do argumentów funkcji, gdy liczba argumentów jest zmienna. Te makra są zdefiniowane w programie w celu zapewnienia zgodności \<stdarg.h> ze standardami ANSI/ISO C i w programie w \<varargs.h> celu zapewnienia kompatybilności z systemem UNIX System.

## <a name="argument-access-macros"></a>Makra dostępu do argumentów

|Makro|Zastosowanie|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Pobierz argument z listy|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Resetuj wskaźnik|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Ustaw wskaźnik na początek listy argumentów|

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)
