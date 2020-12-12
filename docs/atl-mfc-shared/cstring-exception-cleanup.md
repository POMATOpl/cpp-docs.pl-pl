---
description: 'Dowiedz się więcej o: oczyszczanie wyjątków CString'
title: CString — oczyszczanie wyjątków
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: 9c77c9bf5d3f123315c126ce2361be63230c173b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167152"
---
# <a name="cstring-exception-cleanup"></a>CString — oczyszczanie wyjątków

W poprzednich wersjach MFC ważne było czyszczenie [CString](../atl-mfc-shared/reference/cstringt-class.md) obiektów po użyciu. W przypadku biblioteki MFC w wersji 3,0 lub nowszej czyszczenie jawne nie jest już konieczne.

W ramach mechanizmu obsługi wyjątków C++, który jest obecnie stosowany przez MFC, nie trzeba martwić się o czyszczenie po wystąpieniu wyjątku. Aby uzyskać opis sposobu, w jaki C++ "rozwinięcia" stosu po przechwyceniu wyjątku, zobacz [Instrukcje try, catch i throw](../cpp/try-throw-and-catch-statements-cpp.md). Nawet jeśli korzystasz ze środowiska MFC **try** / **catch** zamiast słów kluczowych języka c++ **`try`** i **`catch`** , MFC używa mechanizmu wyjątków c++ poniżej, więc nie trzeba czyścić jawnie.

## <a name="see-also"></a>Zobacz też

[Ciągi (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Obsługa wyjątków](../mfc/exception-handling-in-mfc.md)
