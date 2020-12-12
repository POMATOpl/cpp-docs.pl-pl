---
description: 'Dowiedz się więcej o: niezawodnej'
title: Niezawodność
ms.date: 11/04/2016
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: 7dfe3d40eae4c67f45d4332ce22255a44c33f728
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284515"
---
# <a name="robustness"></a>Niezawodność

Użyj następujących funkcji biblioteki wykonawczej języka C, aby zwiększyć niezawodność programu.

## <a name="run-time-robustness-functions"></a>Run-Time funkcje niezawodne

|Funkcja|Zastosowanie|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Przenosi kontrolę do mechanizmu obsługi błędów, jeśli **`new`** nie można przydzielić pamięci przez operatora.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Obsługuje wyjątki Win32 (wyjątki strukturalne C) jako wyjątki z definicją języka C++.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Instaluje własną funkcję zakończenia, która ma zostać wywołana przez [zakończenie](../c-runtime-library/reference/terminate-crt.md).|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Instaluje własną funkcję zakończenia, która ma zostać wywołana przez [nieoczekiwane](../c-runtime-library/reference/unexpected-crt.md).|

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)<br/>
