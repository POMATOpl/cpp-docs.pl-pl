---
description: 'Dowiedz się więcej o: punkty zaczepienia awarii'
title: Punkty zaczepienia błędów
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: a0e74e3413fc81505941dd6f4545988a0d39436f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200731"
---
# <a name="failure-hooks"></a>Punkty zaczepienia błędów

Punkt zaczepienia awarii jest włączony w taki sam sposób, jak punkt [zaczepienia powiadomienia](notification-hooks.md). Procedura Hook musi zwrócić odpowiednią wartość, aby można było kontynuować przetwarzanie (HINSTANCE lub FARPROC) lub 0 w celu wskazania, że wyjątek powinien zostać wygenerowany.

Zmienna wskaźnika odwołująca się do funkcji zdefiniowanej przez użytkownika to:

```
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

Struktura **DelayLoadInfo** zawiera wszystkie odpowiednie dane niezbędne do dokładnego raportowania błędu, w tym wartość z `GetLastError` .

Jeśli powiadomienie jest **dliFailLoadLib**, funkcja Hook może zwrócić:

- 0, jeśli nie może obsłużyć błędu.

- HMODULE, jeśli hak awarii rozwiązał problem i załadował samą bibliotekę.

Jeśli powiadomienie jest **dliFailGetProc**, funkcja Hook może zwrócić:

- 0, jeśli nie może obsłużyć błędu.

- Prawidłowy adres procesu (adres funkcji importowania), jeśli punkt zaczepienia awarii powiódł się przy pobieraniu samego adresu.

## <a name="see-also"></a>Zobacz też

[Obsługa błędów i powiadomienia](error-handling-and-notification.md)
