---
description: 'Dowiedz się więcej o: procedurach obsługi wyjątków'
title: Obsługa wyjątków — Procedury
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: d241c3ef7f32a96f08d4ad499887963fda031967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331098"
---
# <a name="exception-handling-routines"></a>Obsługa wyjątków — Procedury

Użyj funkcji obsługi wyjątków C++ do odzyskania z nieoczekiwanych zdarzeń podczas wykonywania programu.

## <a name="exception-handling-functions"></a>Funkcje Exception-Handling

|Funkcja|Zastosowanie|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Obsługuj wyjątki Win32 (wyjątki strukturalne C) jako wyjątki z definicją języka C++|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Zainstaluj własną procedurę zakończenia, która ma zostać wywołana przez **zakończenie**|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Zainstaluj własną funkcję zakończenia, która ma zostać wywołana przez **nieoczekiwane**|
|[kończyć](../c-runtime-library/reference/terminate-crt.md)|Wywoływana automatycznie w pewnych okolicznościach po wystąpieniu wyjątku. Funkcja **Terminate** wywołuje **metodę Abort** lub funkcję określoną przy użyciu **set_terminate**|
|[oczekiwan](../c-runtime-library/reference/unexpected-crt.md)|Wywołania **zakończone** lub funkcja określona przy użyciu **set_unexpected**. **Nieoczekiwana** funkcja nie jest używana w bieżącej implementacji obsługi wyjątków Microsoft C++|

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
