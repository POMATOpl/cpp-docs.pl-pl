---
description: 'Dowiedz się więcej na temat: Używanie funkcji VERIFY zamiast potwierdzenia'
title: Korzystanie z VERIFY zamiast ASSERT
ms.date: 05/06/2019
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
ms.openlocfilehash: cbb878e9184536a6888b84f7861a3e8b7b9ab2b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199054"
---
# <a name="using-verify-instead-of-assert"></a>Korzystanie z VERIFY zamiast ASSERT

Załóżmy, że gdy uruchamiasz wersję debugową aplikacji MFC, nie ma żadnych problemów. Jednak wersja tej samej aplikacji ulega awarii, zwraca nieprawidłowe wyniki i/lub wykazuje inne nietypowe zachowanie.

Ten problem może być spowodowany umieszczeniem ważnego kodu w instrukcji ASSERT, aby sprawdzić, czy działa poprawnie. Ponieważ instrukcje ASSERT są oznaczone jako komentarze w kompilacji wydania programu MFC, kod nie jest uruchamiany w kompilacji wydania.

Jeśli używasz metody ASSERT do upewnienia się, że wywołanie funkcji zakończyło się pomyślnie, rozważ użycie polecenia [verify](../mfc/reference/diagnostic-services.md#verify) . Makro VERIFY szacuje własne argumenty w kompilacjach i wersjach aplikacji.

Kolejną preferowaną techniką jest przypisanie wartości zwracanej funkcji do zmiennej tymczasowej, a następnie przetestowanie zmiennej w instrukcji ASSERT.

Zapoznaj się z poniższym fragmentem kodu:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Ten kod działa doskonale w wersji debugowej aplikacji MFC. Jeśli wywołanie `calloc( )` nie powiedzie się, zostanie wyświetlony komunikat diagnostyczny, który zawiera plik i numer wiersza. Jednak w przypadku kompilacji detalicznej aplikacji MFC:

- wywołanie `calloc( )` nigdy nie następuje, pozostawiając `buf` niezainicjowane lub

- `strcpy_s( )` Kopiuje " `Hello, World` " do losowej części pamięci, prawdopodobnie uległa awarii aplikacji lub powoduje, że system przestanie odpowiadać lub

- `free()` próbuje zwolnić pamięć, która nigdy nie została przyznana.

Aby użyć poprawnego potwierdzenia, należy zmienić przykład kodu na następujący:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );
ASSERT( buf != NULL );
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Można też użyć polecenia Weryfikuj:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>Zobacz też

[Rozwiązywanie problemów z kompilacją wersji](fixing-release-build-problems.md)
