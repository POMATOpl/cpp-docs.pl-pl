---
description: 'Dowiedz się więcej o mechanizmie wyjątku MFC: TN032:'
title: 'TN032: mechanizm wyjątków MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: 847d78762aaf5e04c8a0c1eb2170e951d0b867bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215537"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: mechanizm wyjątków MFC

Poprzednie wersje Visual C++ nie obsługiwały standardowego mechanizmu wyjątków C++, a w przypadku makr w języku MFC podane zostały zamiast nich wykorzystane polecenie **try/catch/throw** . Ta wersja Visual C++ w pełni obsługuje wyjątki C++. Ta Uwaga obejmuje niektóre zaawansowane szczegóły implementacji poprzednich makr, takie jak automatyczne czyszczenie obiektów opartych na stosie. Ponieważ wyjątki C++ obsługują domyślnie rozwinięcia stosu, ta Uwaga techniczna nie jest już potrzebna.

Zobacz [wyjątki: używanie makr MFC i wyjątków języka c++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) , aby uzyskać więcej informacji na temat różnic między makrami MFC i nowymi słowami kluczowymi języka c++.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
