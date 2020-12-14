---
description: 'Dowiedz się więcej: obsługa błędów i powiadomienia'
title: Obsługa błędów oraz powiadomienia
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 234d50d0b4a7e8b81874d1926ac056f8cba23376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200991"
---
# <a name="error-handling-and-notification"></a>Obsługa błędów oraz powiadomienia

Aby uzyskać więcej informacji na temat obsługi błędów i powiadamiania, zobacz [Omówienie funkcji pomocnika](understanding-the-helper-function.md).

Aby uzyskać więcej informacji na temat funkcji Hook, zobacz [struktury i definicje stałe](structure-and-constant-definitions.md).

Jeśli program używa bibliotek DLL załadowanych z opóźnieniem, musi obsługiwać błędy niezawodnie, ponieważ błędy występujące podczas działania programu spowodują Nieobsłużone wyjątki. Obsługa błędów składa się z dwóch części:

Odzyskiwanie przez punkt zaczepienia.
Jeśli kod wymaga odzyskania lub udostępnienia alternatywnej biblioteki i/lub procedury w przypadku niepowodzenia, można dostarczyć punkt zaczepienia do funkcji pomocnika, która może dostarczyć lub naprawić sytuację. Procedura Hook musi zwrócić odpowiednią wartość, aby przetwarzanie było kontynuowane (HINSTANCE lub FARPROC) lub 0, aby wskazać, że wyjątek powinien zostać wygenerowany. Może również zgłosić swój własny wyjątek lub **longjmp** z punktu zaczepienia. Istnieją punkty zaczepienia powiadomień i punkty zaczepienia awarii.

Raportowanie przez wyjątek.
Jeśli wszystkie elementy, które są niezbędne do obsługi błędu, to przerwanie procedury, nie jest potrzebny żaden hak, o ile kod użytkownika może obsłużyć wyjątek.

W poniższych tematach omówiono obsługę błędów i powiadomienia:

- [Punkty zaczepienia powiadomień](notification-hooks.md)

- [Punkty zaczepienia błędów](failure-hooks.md)

- [Wyjątki](exceptions-c-cpp.md)

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
