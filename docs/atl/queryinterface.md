---
description: 'Dowiedz się więcej o: QueryInterface'
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: b22163c9e69bd5573f8e6060df0457862813c366
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159170"
---
# <a name="queryinterface"></a>QueryInterface

Chociaż istnieją mechanizmy, za pomocą których obiekt może wyrazić funkcje, które zapewnia statycznie (przed utworzeniem wystąpienia), podstawowy mechanizm COM ma używać `IUnknown` metody o nazwie [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)).

Każdy interfejs jest wyprowadzany z `IUnknown` , więc każdy interfejs ma implementację programu `QueryInterface` . Niezależnie od implementacji ta metoda wysyła zapytanie do obiektu przy użyciu identyfikatora IID interfejsu, do którego obiekt wywołujący chce wskaźnik. Jeśli obiekt obsługuje ten interfejs, `QueryInterface` Pobiera wskaźnik do interfejsu, a także wywołuje `AddRef` . W przeciwnym razie zwraca E_NOINTERFACE kod błędu.

Należy pamiętać, że w każdej chwili należy przestrzegać reguł [zliczania odwołań](../atl/reference-counting.md) . Jeśli wywołasz `Release` wskaźnik interfejsu w celu zmniejszenia liczby odwołań do zera, nie należy ponownie używać tego wskaźnika. Czasami może być konieczne uzyskanie słabego odwołania do obiektu (to oznacza, że można uzyskać wskaźnik do jednego z jego interfejsów bez zwiększania liczby odwołań), ale nie jest to możliwe do wykonania przez wywołanie metody `QueryInterface` `Release` . Wskaźnik uzyskany w taki sposób jest nieprawidłowy i nie należy go używać. Jest to bardziej łatwo widoczne, gdy [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) jest zdefiniowana, więc zdefiniowanie tego makra jest przydatnym sposobem znajdowania usterek zliczania odwołań.

## <a name="see-also"></a>Zobacz też

[Wprowadzenie do modelu COM](../atl/introduction-to-com.md)<br/>
[QueryInterface: nawigowanie w obiekcie](/windows/win32/com/queryinterface--navigating-in-an-object)
