---
description: 'Dowiedz się więcej na temat: alokowanie i dealokowanie pamięci okna'
title: Alokowanie i dealokowanie pamięci okna
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: 7648914289babffdfb5195f1ec53cd736e26892c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343721"
---
# <a name="allocating-and-deallocating-window-memory"></a>Alokowanie i dealokowanie pamięci okna

Nie używaj operatora C++, **`delete`** aby zniszczyć okno lub widok ramki. Zamiast tego należy wywołać `CWnd` funkcję członkowską `DestroyWindow` . W związku z tym należy przydzielyć okna ramowe do sterty z operatorem **`new`** . Należy zachować ostrożność podczas alokowania okien ramowych w ramce stosu lub globalnie. W miarę możliwości można przydzielać inne okna na ramkę stosu.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Tworzenie okien](creating-windows.md)

- [Sekwencja niszczenia okna](window-destruction-sequence.md)

- [Odłączanie obiektu CWnd od jego właściwości HWND](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Zobacz też

[Niszczenie obiektów okien](destroying-window-objects.md)
