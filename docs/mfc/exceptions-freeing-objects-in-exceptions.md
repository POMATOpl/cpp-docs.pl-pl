---
description: 'Dowiedz się więcej o: wyjątki: zwalnianie obiektów w wyjątkach'
title: 'Wyjątki: zwalnianie obiektów w wyjątkach'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], freeing objects in exceptions
- local exception handling
- memory leaks, caused by exception
- try-catch exception handling [MFC], destroying objects
- destroying objects [MFC]
- freeing objects [MFC]
- throwing exceptions [MFC], after destroying
- exception handling [MFC], destroying objects
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
ms.openlocfilehash: 47b10f3ecb96875ceee986eadda4595d2afbb77e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290560"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>Wyjątki: zwalnianie obiektów w wyjątkach

W tym artykule wyjaśniono potrzebę i metodę zwalniania obiektów w przypadku wystąpienia wyjątku. Tematy obejmują:

- [Obsługa wyjątku lokalnie](#_core_handling_the_exception_locally)

- [Zgłaszanie wyjątków po usunięciu obiektów](#_core_throwing_exceptions_after_destroying_objects)

Wyjątki zgłoszone przez platformę lub przez aplikację w normalnym przepływie programu. W związku z tym bardzo ważne jest, aby zamknąć śledzenie obiektów, aby można było prawidłowo usunąć je w przypadku zgłoszenia wyjątku.

Istnieją dwie podstawowe metody do wykonania tej czynności.

- Obsługa wyjątków lokalnie przy użyciu **`try`** **`catch`** słów kluczowych i, a następnie zniszczenie wszystkich obiektów z jedną instrukcją.

- Zniszcz wszystkie obiekty w **`catch`** bloku przed wygenerowaniem wyjątku poza blokiem w celu dalszej obsługi.

Te dwa podejścia przedstawiono poniżej jako rozwiązania następujących przykładowych problemów:

[!code-cpp[NVC_MFCExceptions#14](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

Jak napisano powyżej, `myPerson` nie zostanie usunięty, jeśli wyjątek jest zgłaszany przez `SomeFunc` . Wykonanie przechodzi bezpośrednio do następnej zewnętrznej procedury obsługi wyjątków, pomijając normalne wyjście funkcji i kod, który usuwa obiekt. Wskaźnik do obiektu wykracza poza zakres, gdy wyjątek opuszcza funkcję, a Pamięć zajęta przez obiekt nigdy nie zostanie odzyskana, o ile program jest uruchomiony. Jest to przeciek pamięci; zostanie on wykryty przy użyciu diagnostyki pamięci.

## <a name="handling-the-exception-locally"></a><a name="_core_handling_the_exception_locally"></a> Obsługa wyjątku lokalnie

Model **try/catch** oferuje obronną metodę programowania do unikania przecieków pamięci i zapewnianie zniszczenia obiektów w przypadku wystąpienia wyjątków. Przykładowo przedstawiony wcześniej w tym artykule można napisać ponownie w następujący sposób:

[!code-cpp[NVC_MFCExceptions#15](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

Ten nowy przykład konfiguruje procedurę obsługi wyjątków, aby przechwycić wyjątek i obsłużyć ją lokalnie. Następnie zamyka funkcję normalnie i niszczy obiekt. Ważnym aspektem tego przykładu jest to, że kontekst przechwytywania wyjątku jest ustanawiany za pomocą bloków **try/catch** . Bez lokalnej ramki wyjątku funkcja nigdy nie wie, że wyjątek został zgłoszony i nie może wyjść normalnie i zniszczyć obiekt.

## <a name="throwing-exceptions-after-destroying-objects"></a><a name="_core_throwing_exceptions_after_destroying_objects"></a> Zgłaszanie wyjątków po usunięciu obiektów

Innym sposobem obsługi wyjątków jest przekazanie ich do następnego zewnętrznego kontekstu obsługi wyjątków. W **`catch`** bloku można przeprowadzić oczyszczanie lokalnie przyznanych obiektów, a następnie zgłosić wyjątek na potrzeby dalszej obróbki.

Funkcja zgłaszania może być niezbędna do cofnięcia alokacji obiektów sterty. Jeśli funkcja zawsze cofa alokację obiektu sterty przed zwróceniem normalnego przypadku, funkcja powinna również cofnąć alokację obiektu sterty przed wygenerowaniem wyjątku. Z drugiej strony, jeśli funkcja nie powoduje zazwyczaj cofnięcia alokacji obiektu przed zwróceniem w normalnym przypadku, należy podjąć decyzje dotyczące wielkości liter, niezależnie od tego, czy obiekt sterty powinien zostać cofnięty.

Poniższy przykład pokazuje, jak można oczyścić lokalnie przydzieloną obiekty:

[!code-cpp[NVC_MFCExceptions#16](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

Mechanizm wyjątków powoduje automatyczne Cofnięcie alokacji obiektów ramek; wywoływana jest również destruktor obiektu Frame.

Jeśli wywołasz funkcje, które mogą zgłaszać wyjątki, możesz użyć bloków **try/catch** , aby upewnić się, że przechwytujesz wyjątki i chcesz zniszczyć wszystkie obiekty, które zostały utworzone. W szczególności należy pamiętać, że wiele funkcji MFC może generować wyjątki.

Aby uzyskać więcej informacji, zobacz [wyjątki: Przechwytywanie i usuwanie wyjątków](exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Zobacz też

[Obsługa wyjątków](exception-handling-in-mfc.md)
