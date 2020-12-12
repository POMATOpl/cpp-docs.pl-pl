---
description: 'Dowiedz się więcej na temat: debugowanie i klasy wyjątków'
title: Klasy debugowania i wyjątków
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 2c14ea8d51fd1b63427ad1495e711a906e013ea4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291119"
---
# <a name="debugging-and-exception-classes"></a>Klasy debugowania i wyjątków

Te klasy zapewniają obsługę debugowania alokacji pamięci dynamicznej i przekazywania informacji o wyjątku z funkcji, w której wyjątek jest zgłaszany do funkcji, w której jest przechwytywany.

Używaj klas [CDumpContext](reference/cdumpcontext-class.md) i [CMemoryState](reference/cmemorystate-structure.md) podczas programowania, aby pomóc w debugowaniu, zgodnie z opisem w [debugowaniu aplikacji MFC](/visualstudio/debugger/mfc-debugging-techniques). Użyj [CRuntimeClass](reference/cruntimeclass-structure.md) , aby określić klasę dowolnego obiektu w czasie wykonywania, zgodnie z opisem w artykule [Uzyskiwanie dostępu do Run-Time informacji o klasie](accessing-run-time-class-information.md). Struktura używa programu `CRuntimeClass` do dynamicznego tworzenia obiektów dla określonej klasy.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)
