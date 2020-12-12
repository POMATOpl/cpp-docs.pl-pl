---
description: 'Dowiedz się więcej na temat: wpływ buforowania'
title: Effects of Buffering
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: dc46a5a7a390250be1872f9264235e133b9f58ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232723"
---
# <a name="effects-of-buffering"></a>Effects of Buffering

Poniższy przykład pokazuje efekty buforowania. Może się spodziewać, że program drukuje `please wait` , odczeka 5 sekund, a następnie kontynuował. Nie będzie koniecznie działać w ten sposób, ponieważ dane wyjściowe są buforowane.

```cpp
// effects_buffering.cpp
// compile with: /EHsc
#include <iostream>
#include <time.h>
using namespace std;

int main( )
{
   time_t tm = time( NULL ) + 5;
   cout << "Please wait...";
   while ( time( NULL ) < tm )
      ;
   cout << "\nAll done" << endl;
}
```

Aby program działał logicznie, `cout` obiekt musi być pusty, gdy zostanie wyświetlony komunikat. Aby opróżnić `ostream` obiekt, wyślij go do `flush` Manipulator:

```cpp
cout <<"Please wait..." <<flush;
```

Ten krok opróżnia bufor, upewniając się, że wiadomość jest drukowana przed oczekiwaniem. Można również użyć `endl` manipulator, która opróżnia bufor i wyprowadza znak wysuwu wiersza, lub użyć `cin` obiektu. Ten obiekt (z `cerr` obiektami lub `clog` ) jest zwykle powiązany z `cout` obiektem. W takim przypadku użycie `cin` (lub `cerr` `clog` obiektów lub) opróżnia `cout` obiekt.

## <a name="see-also"></a>Zobacz też

[Strumienie wyjściowe](../standard-library/output-streams.md)
