---
description: 'Dowiedz się więcej na temat: co to jest strumień'
title: Czym jest strumień?
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
ms.openlocfilehash: 3786fe05f25949129c1bce63bdbbd73a16209475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187783"
---
# <a name="what-a-stream-is"></a>Czym jest strumień?

Podobnie jak C, C++ nie ma wbudowanej możliwości wejścia/wyjścia. Wszystkie kompilatory języka C++ są jednak powiązane z systematycznym pakietem we/wy zorientowanym na obiekty, znanym jako klasy iostream. Strumień jest centralną koncepcją klas iostream. Obiekt strumienia można traktować jako plik inteligentny, który działa jako źródło i miejsce docelowe dla bajtów. Charakterystyki strumienia są określane przez klasę i przez niestandardowe operatory wstawiania i wyodrębniania.

W przypadku sterowników urządzeń system operacyjny dysku zajmuje się przy użyciu klawiatury, ekranu, drukarki i portów komunikacyjnych jako plików rozszerzonych. Klasy iostream współpracują z tymi rozszerzonymi plikami. Wbudowane klasy obsługują odczytywanie i zapisywanie w pamięci przy użyciu składni identycznej z tą dla operacji we/wy dysku, co ułatwia wyprowadzanie klas strumienia.

## <a name="in-this-section"></a>W tej sekcji

[Alternatywy wejścia/wyjścia](../standard-library/input-output-alternatives.md)

## <a name="see-also"></a>Zobacz też

[Programowanie iostream](../standard-library/iostream-programming.md)
