---
title: Zakończenie programu C++
description: Zapoznaj się ze standardowymi sposobami zamykania programu języka C++.
ms.date: 12/07/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.openlocfilehash: 15d31d8d454f6ac90e012d35ef14e6d6e0a9e29a
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933212"
---
# <a name="c-program-termination"></a>Zakończenie programu C++

W języku C++ można wyjść z programu w następujący sposób:

- Wywołaj [`exit`](../c-runtime-library/reference/exit-exit-exit.md) funkcję.
- Wywołaj [`abort`](../c-runtime-library/reference/abort.md) funkcję.
- Wykonaj [`return`](return-statement-cpp.md) instrukcję z `main` .

## <a name="exit-function"></a>Funkcja `exit`

[`exit`](../c-runtime-library/reference/exit-exit-exit.md)Funkcja zadeklarowana w \<stdlib.h> , kończy program języka C++. Wartość podana jako argument `exit` jest zwracana do systemu operacyjnego jako kod powrotny programu lub kod zakończenia. Zgodnie z Konwencją, zwracany kod zero oznacza, że program został ukończony pomyślnie. Możesz użyć stałych `EXIT_FAILURE` i `EXIT_SUCCESS` , również zdefiniowanych w \<stdlib.h> , aby wskazać powodzenie lub niepowodzenie programu.

Wygenerowanie **`return`** instrukcji z `main` funkcji jest równoznaczne z wywołaniem `exit` funkcji z wartością zwracaną jako argument.

## <a name="abort-function"></a>Funkcja `abort`

[`abort`](../c-runtime-library/reference/abort.md)Funkcja, zadeklarowana również w standardowym pliku dołączania \<stdlib.h> , kończy program języka C++. Różnica między `exit` i `abort` polega na tym, że `exit` umożliwia przetwarzanie zakończenia w czasie wykonywania w języku C++ (globalne destruktory obiektów wywoływane), ale `abort` natychmiast kończy działanie programu. `abort`Funkcja pomija proces normalnego niszczenia dla zainicjowanych globalnych obiektów statycznych. Pomija również specjalne przetwarzanie, które zostało określone za pomocą [`atexit`](../c-runtime-library/reference/atexit.md) funkcji.

## <a name="atexit-function"></a>Funkcja `atexit`

Użyj [`atexit`](../c-runtime-library/reference/atexit.md) funkcji, aby określić akcje wykonywane przed zakończeniem działania programu. Nie zainicjowano żadnych globalnych obiektów statycznych, zanim wywołanie `atexit` zostanie zniszczone przed wykonaniem funkcji przetwarzania wyjścia.

## <a name="return-statement-in-main"></a>`return` Instrukcja w `main`

Wygenerowanie [`return`](return-statement-cpp.md) instrukcji from `main` jest funkcjonalnie równoważnej wywołania `exit` funkcji. Rozpatrzmy następujący przykład:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`Instrukcje i **`return`** w powyższym przykładzie są funkcjonalnie identyczne. Zwykle C++ wymaga, aby funkcje, które mają zwracane typy inne niż **`void`** zwraca wartość. `main`Funkcja jest wyjątkiem; może kończyć się bez **`return`** instrukcji. W takim przypadku zwraca wartość specyficzną dla implementacji do procesu wywołującego. **`return`** Instrukcja pozwala określić wartość zwracaną z `main` .

## <a name="destruction-of-static-objects"></a>Niszczenie obiektów statycznych

Po wywołaniu `exit` lub wykonaniu **`return`** instrukcji z programu `main` obiekty statyczne są niszczone w odwrotnej kolejności inicjalizacji (po wywołaniu do `atexit` Jeśli taka istnieje). Poniższy przykład pokazuje, jak działa takie inicjowanie i oczyszczanie.

### <a name="example"></a>Przykład

W poniższym przykładzie obiekty statyczne `sd1` i `sd2` są tworzone i inicjowane przed wpisem do `main` . Po zakończeniu działania tego programu przy użyciu **`return`** instrukcji, najpierw `sd2` zostaje zniszczony, a następnie `sd1` . Destruktor dla `ShowData` klasy zamyka pliki skojarzone z tymi obiektami statycznymi.

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

Innym sposobem zapisu tego kodu jest zadeklarowanie `ShowData` obiektów z zakresem bloku, umożliwiając ich zniszczenie, gdy wykraczają poza zakres:

```cpp
int main() {
   ShowData sd1( "CON" ), sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>Zobacz też

[`main` argumenty funkcji i wiersza polecenia](main-function-command-line-args.md)
