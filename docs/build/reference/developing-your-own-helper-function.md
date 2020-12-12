---
description: Dowiedz się więcej na temat tworzenia własnej funkcji pomocnika
title: Tworzenie własnej funkcji Pomocnik
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
ms.openlocfilehash: da536d13da9a596c5667c3fa84311b73e66d71ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201459"
---
# <a name="developing-your-own-helper-function"></a>Tworzenie własnej funkcji Pomocnik

Może być konieczne udostępnienie własnej wersji procedury w celu przeprowadzenia określonego przetwarzania na podstawie nazw bibliotek DLL lub importów. Istnieją dwie metody wykonania tej czynności: kodowanie własnych, prawdopodobnie opartych na dostarczonym kodzie lub samo Podłączanie podanej wersji przy użyciu podanych wcześniej punktów powiadomień.

## <a name="code-your-own"></a>Kod własnych

Jest to dość proste, ponieważ można zasadniczo użyć dostarczonego kodu jako wskazówki dla nowego. Oczywiście musi być zgodna z konwencjami wywołania i jeśli powraca do sekcje thunk wygenerowanych przez konsolidatora, musi zwrócić prawidłowy wskaźnik funkcji. Jeden raz w kodzie można wykonać bardzo wiele rzeczy w celu zaspokojenia wywołania lub uzyskania wywołania.

## <a name="use-the-start-processing-notification-hook"></a>Korzystanie z punktu zaczepienia powiadomień o rozpoczęciu przetwarzania

Prawdopodobnie najłatwiej będzie zapewnić nowy wskaźnik do funkcji podłączania powiadomień dostarczonej przez użytkownika, która otrzymuje te same wartości, co domyślny pomocnik w usłudze Notification dliStartProcessing. W tym momencie funkcja Hook może być zasadniczo nową funkcją pomocnika, ponieważ pomyślne zwrócenie do domyślnego pomocnika spowoduje obejście całego przetwarzania w domyślnym Pomocniku.

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
