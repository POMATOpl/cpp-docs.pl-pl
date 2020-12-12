---
description: 'Dowiedz się więcej o: alternatywy wejścia/wyjścia'
title: Input-Output alternatywy
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: a6df022dd38bc23eaaaad49620067aca408b2df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324005"
---
# <a name="inputoutput-alternatives"></a>Input/Output Alternatives

Kompilator języka Microsoft C++ udostępnia kilka alternatywnych rozwiązań programistycznych we/wy:

- Biblioteka wykonawcza języka C bezpośrednio, niebuforowane we/wy.

- Strumień operacji we/wy biblioteki wykonawczej ANSI C.

- Bezpośrednie we/wy konsoli i portu.

- biblioteka MFC.

- Standardowa biblioteka języka Microsoft C++.

Klasy iostream są przydatne w przypadku buforowanych, sformatowanych we/wy tekstu. Są one również przydatne w przypadku niebuforowanego lub binarnego wejścia/wyjścia, jeśli potrzebujesz interfejsu programowania C++ i nie mają korzystać z biblioteki Microsoft Foundation Class (MFC). Klasy iostream są alternatywnym obiektem we/wy dla funkcji w czasie wykonywania języka C.

Klas iostream można użyć z systemem operacyjnym Microsoft Windows. Strumienie ciągów i plików działają bez ograniczeń, ale obiekty strumienia trybu znakowego `cin` , `cout` , `cerr` i `clog` są niespójne z graficznym interfejsem użytkownika systemu Windows. Można również utworzyć niestandardowe klasy strumienia, które współpracują bezpośrednio ze środowiskiem systemu Windows.

## <a name="see-also"></a>Zobacz też

[Co to jest strumień](../standard-library/what-a-stream-is.md)
