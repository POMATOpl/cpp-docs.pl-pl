---
description: 'Dowiedz się więcej na temat: jak: kierowanie struktur za pomocą funkcji PInvoke'
title: 'Porady: kierowanie struktur za pomocą funkcji PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
ms.openlocfilehash: 417701ae1459c265e48171a517b7729d0e92c098
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302533"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Porady: kierowanie struktur za pomocą funkcji PInvoke

W tym dokumencie wyjaśniono, jak natywne funkcje, które akceptują struktury w stylu C, można wywołać z funkcji zarządzanych za pomocą P/Invoke. Chociaż zalecamy używanie funkcji międzyoperacyjnych C++ zamiast P/Invoke, ponieważ funkcja P/Invoke zapewnia niewielkie raportowanie błędów w czasie kompilacji, nie jest bezpieczna pod względem typu i może być żmudnym do wdrożenia, jeśli niezarządzany interfejs API jest spakowany jako biblioteka DLL, a kod źródłowy jest niedostępny, funkcja P/Invoke jest jedyną opcją. W przeciwnym razie zapoznaj się z następującymi dokumentami:

- [Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Instrukcje: kierowanie ciągów za pomocą funkcji PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)

Domyślnie struktury natywne i zarządzane są określane inaczej w pamięci, dlatego pomyślne przekazanie struktur między granicami zarządzaną/niezarządzaną wymaga dodatkowych kroków w celu zachowania integralności danych.

W tym dokumencie opisano kroki wymagane do zdefiniowania zarządzanych odpowiedników struktur natywnych oraz sposobu przekazywania struktur wynikowych do funkcji niezarządzanych. W tym dokumencie przyjęto założenie, że proste struktury — te, które nie zawierają ciągów lub wskaźników — są używane. Aby uzyskać informacje na temat współdziałania niebędącego danych kopiowalnych, zobacz [using C++ Interop (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). Metoda P/Invoke nie może mieć typów innych niż danych kopiowalnych jako wartości zwracanej. Typy danych kopiowalnych mają tę samą reprezentację w kodzie zarządzanym i niezarządzanym. Aby uzyskać więcej informacji, zobacz [typy danych kopiowalnych i danych kopiowalnych](/dotnet/framework/interop/blittable-and-non-blittable-types).

Kierowanie prostych struktur danych kopiowalnych w ramach granic zarządzanych/niezarządzanych najpierw wymaga zdefiniowania zarządzanych wersji każdej struktury natywnej. Struktury te mogą mieć dowolną nazwę prawną; nie istnieje żadna relacja między natywną i zarządzaną wersją dwóch struktur, które różnią się od ich układu danych. W związku z tym ważne jest, aby zarządzana wersja zawierała pola, które mają ten sam rozmiar i w takiej samej kolejności jak wersja natywna. (Nie ma mechanizmu zapewnienia, że zarządzane i natywne wersje struktury są równoważne, więc niezgodności nie staną się widoczne do czasu uruchomienia. Programista jest odpowiedzialny za zapewnienie, że dwie struktury mają ten sam układ danych).

Ze względu na to, że elementy członkowskie struktur zarządzanych są czasami ponownie rozmieszczane w celu zapewnienia wydajności, należy użyć <xref:System.Runtime.InteropServices.StructLayoutAttribute> atrybutu, aby wskazać, że struktura została określona sekwencyjnie. Dobrym pomysłem jest również jawne ustawienie ustawienia pakowania struktury na takie samo, jak używane przez natywną strukturę. (Chociaż domyślnie Visual C++ używa pakowania struktury 8-bajtowej dla kodu zarządzanego).

1. Następnie użyj, <xref:System.Runtime.InteropServices.DllImportAttribute> Aby zadeklarować punkty wejścia odpowiadające niezarządzanym funkcjom, które akceptują strukturę, ale Użyj zarządzanej wersji struktury w sygnaturach funkcji, która jest punktem Moot, jeśli używasz tej samej nazwy dla obu wersji struktury.

1. Teraz kod zarządzany może przekazać zarządzaną wersję struktury do funkcji niezarządzanych, tak jakby są faktycznie zarządzanymi funkcjami. Te struktury mogą być przesyłane przez wartość lub przez odwołanie, jak pokazano w poniższym przykładzie.

## <a name="unmanaged-and-a-managed-modules"></a>Niezarządzane i zarządzane moduły

Poniższy kod składa się z niezarządzanego i zarządzanego modułu. Moduł niezarządzany jest biblioteką DLL, która definiuje strukturę o nazwie Location i funkcję o nazwie GetDistance akceptującą dwa wystąpienia struktury lokalizacji. Drugi moduł jest zarządzaną aplikacją wiersza polecenia, która importuje funkcję GetDistance, ale definiuje ją pod względem zarządzanego odpowiednika struktury lokalizacji, MLocation. W przypadku użycia tej samej nazwy można użyć w obu wersjach struktury; Jednak w tym miejscu użyto innej nazwy, aby zademonstrować, że prototyp DllImport jest zdefiniowany w zakresie zarządzanej wersji.

Należy zauważyć, że żadna część biblioteki DLL nie jest ujawniona w zarządzanym kodzie przy użyciu tradycyjnej dyrektywy #include. W rzeczywistości biblioteka DLL jest dostępna tylko w czasie wykonywania, dlatego problemy z funkcjami zaimportowanymi z DllImport nie będą wykrywane w czasie kompilacji.

### <a name="example-unmanaged-dll-module"></a>Przykład: niezarządzany moduł DLL

```cpp
// TraditionalDll3.cpp
// compile with: /LD /EHsc
#include <iostream>
#include <stdio.h>
#include <math.h>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
   #define TRADITIONALDLL_API __declspec(dllexport)
#else
   #define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct Location {
   int x;
   int y;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API double GetDistance(Location, Location);
   TRADITIONALDLL_API void InitLocation(Location*);
}

double GetDistance(Location loc1, Location loc2) {
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   printf_s("[unmanaged] Initializing location...\n");
   lp->x = 50;
   lp->y = 50;
}
```

### <a name="example-managed-command-line-application-module"></a>Przykład: zarządzany moduł aplikacji wiersza polecenia

```cpp
// MarshalStruct_pi.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MLocation {
   int x;
   int y;
};

value struct TraditionalDLL {
   [DllImport("TraditionalDLL3.dll")]
   static public double GetDistance(MLocation, MLocation);
   [DllImport("TraditionalDLL3.dll")]
   static public double InitLocation(MLocation*);
};

int main() {
   MLocation loc1;
   loc1.x = 0;
   loc1.y = 0;

   MLocation loc2;
   loc2.x = 100;
   loc2.y = 100;

   double dist = TraditionalDLL::GetDistance(loc1, loc2);
   Console::WriteLine("[managed] distance = {0}", dist);

   MLocation loc3;
   TraditionalDLL::InitLocation(&loc3);
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);
}
```

```Output
[unmanaged] loc1(0,0) loc2(100,100)
[managed] distance = 141.42135623731
[unmanaged] Initializing location...
[managed] x=50 y=50
```

## <a name="see-also"></a>Zobacz też

[Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
