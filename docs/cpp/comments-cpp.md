---
description: 'Dowiedz się więcej o: komentarzach (C++)'
title: Komentarze (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: b3bbcafe1f18c791fc5935161b6cdbfae0bf03cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239795"
---
# <a name="comments-c"></a>Komentarze (C++)

Komentarz jest tekstem, który kompilator ignoruje, ale jest przydatny dla programistów. Komentarze są zwykle używane do dodawania adnotacji do kodu w przyszłości. Kompilator traktuje je jako biały znak. Możesz użyć komentarzy w testowaniu, aby niektóre wiersze kodu były nieaktywne; Jednakże `#if` / `#endif` dyrektywy preprocesora działają w ten sposób lepiej, ponieważ możesz otoczyć kod zawierający komentarze, ale nie możesz zagnieżdżać komentarzy.

Komentarz w języku C++ jest zapisywana w jeden z następujących sposobów:

- `/*`Znaki (ukośnik, gwiazdka), po których następuje jakakolwiek sekwencja znaków (w tym nowe wiersze), po której następują `*/` znaki. Ta składnia jest taka sama jak ANSI C.

- `//`Znaki (dwa ukośniki), po których następuje jakakolwiek sekwencja znaków. Nowy wiersz bezpośrednio poprzedzony ukośnikiem odwrotnym kończy tę formę komentarza. W związku z tym często nazywa się "jednowierszowym komentarzem".

Znaki komentarza ( `/*` , `*/` i `//` ) nie mają specjalnego znaczenia w obrębie znaku stałej, literału ciągu ani komentarza. Komentarze z użyciem pierwszej składni nie mogą być zagnieżdżane.

## <a name="see-also"></a>Zobacz też

[Konwencje leksykalne](../cpp/lexical-conventions.md)
