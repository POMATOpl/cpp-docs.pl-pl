---
description: 'Dowiedz się więcej o: nazwy środowisk'
title: Nazwy środowiska
ms.date: 11/04/2016
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
ms.openlocfilehash: f40da15151385cea4bd581dea8946f50d2b58ea8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213757"
---
# <a name="environment-names"></a>Nazwy środowiska

**4.10.4.4 ANSI** Zestaw nazw środowisk i metody zmiany listy środowiska używanej przez funkcję [getenv](../c-runtime-library/reference/getenv-wgetenv.md)

Zbiór nazw środowisk jest nieograniczony.

Aby zmienić zmienne środowiskowe z poziomu programu w języku C, wywołaj funkcję [_putenv](../c-runtime-library/reference/putenv-wputenv.md) . Aby zmienić zmienne środowiskowe z wiersza polecenia w systemie Windows, użyj polecenia SET (na przykład SET LIB = D:\ LIBS).

Zmienne środowiskowe ustawione w ramach programu C istnieją tylko tak długo, jak ich kopia hosta powłoki poleceń systemu operacyjnego jest uruchomiona (CMD.EXE lub COMMAND.COM). Na przykład wiersz

```
system( SET LIB = D:\LIBS );
```

Uruchom kopię powłoki poleceń (CMD.EXE), Ustaw zmienną środowiskową LIB i wróć do programu C, a następnie Wyjdź z kopii pomocniczej CMD.EXE. Wyjście z tej kopii CMD.EXE spowoduje usunięcie tymczasowej zmiennej środowiskowej LIB.

Podobnie zmiany wprowadzane przez funkcję są `_putenv` ostatnie tylko do momentu zakończenia programu.

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki](../c-language/library-functions.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)
