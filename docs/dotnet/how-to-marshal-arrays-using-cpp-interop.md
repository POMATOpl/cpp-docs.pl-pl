---
description: 'Dowiedz się więcej o tym, jak: kierowanie tablic za pomocą międzyoperacyjności języka C++'
title: 'Porady: kierowanie tablic za pomocą międzyoperacyjności języka C++'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++], marshaling
- marshaling [C++], arrays
- interop [C++], arrays
- C++ Interop, arrays
- data marshaling [C++], arrays
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
ms.openlocfilehash: 5c91b9f24a801f7bf1bd1ec3132503535f0334d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258242"
---
# <a name="how-to-marshal-arrays-using-c-interop"></a>Porady: kierowanie tablic za pomocą międzyoperacyjności języka C++

W tym temacie przedstawiono jeden aspekt współdziałania Visual C++. Aby uzyskać więcej informacji, zobacz [using C++ Interop (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

W poniższych przykładach kodu użyto [zarządzanych, niezarządzanych](../preprocessor/managed-unmanaged.md) #pragma dyrektyw, aby zaimplementować funkcje zarządzane i niezarządzane w tym samym pliku, ale te funkcje współdziałają w taki sam sposób, jeśli zostały zdefiniowane w oddzielnych plikach. Pliki zawierające tylko funkcje niezarządzane nie muszą być kompilowane z [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example-pass-managed-array-to-unmanaged-function"></a>Przykład: Przekaż zarządzaną tablicę do funkcji niezarządzanej

W poniższym przykładzie pokazano, jak przekazać zarządzaną tablicę do funkcji niezarządzanej. Funkcja zarządzana używa [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) , aby pominąć wyrzucanie elementów bezużytecznych dla tablicy przed wywołaniem funkcji niezarządzanej. Dostarczając niezarządzaną funkcję z przypiętym wskaźnikiem do sterty GC, można uniknąć narzutu na tworzenie kopii tablicy. Aby zademonstrować, że niezarządzana funkcja uzyskuje dostęp do pamięci sterty GC, modyfikuje zawartość tablicy, a zmiany są uwzględniane, gdy zarządzana funkcja wznawia kontrolę.

```cpp
// PassArray1.cpp
// compile with: /clr
#ifndef _CRT_RAND_S
#define _CRT_RAND_S
#endif

#include <iostream>
#include <stdlib.h>
using namespace std;

using namespace System;

#pragma unmanaged

void TakesAnArray(int* a, int c) {
   cout << "(unmanaged) array received:\n";
   for (int i=0; i<c; i++)
      cout << "a[" << i << "] = " << a[i] << "\n";

   unsigned int number;
   errno_t err;

   cout << "(unmanaged) modifying array contents...\n";
   for (int i=0; i<c; i++) {
      err = rand_s( &number );
      if ( err == 0 )
         a[i] = number % 100;
   }
}

#pragma managed

int main() {
   array<int>^ nums = gcnew array<int>(5);

   nums[0] = 0;
   nums[1] = 1;
   nums[2] = 2;
   nums[3] = 3;
   nums[4] = 4;

   Console::WriteLine("(managed) array created:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);

   pin_ptr<int> pp = &nums[0];
   TakesAnArray(pp, 5);

   Console::WriteLine("(managed) contents:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);
}
```

## <a name="example-pass-unmanaged-array-to-managed-function"></a>Przykład: Przekaż niezarządzaną tablicę do funkcji zarządzanej

W poniższym przykładzie pokazano przekazywanie niezarządzanej tablicy do funkcji zarządzanej. Funkcja zarządzana uzyskuje bezpośredni dostęp do pamięci tablicy (w przeciwieństwie do tworzenia zarządzanej tablicy i kopiowania zawartości tablicy), co pozwala na odzwierciedlenie zmian wprowadzonych przez funkcję zarządzaną w funkcji zarządzanej, gdy odzyska ona kontrolę.

```cpp
// PassArray2.cpp
// compile with: /clr
#include <iostream>
using namespace std;

using namespace System;

#pragma managed

void ManagedTakesAnArray(int* a, int c) {
   Console::WriteLine("(managed) array received:");
   for (int i=0; i<c; i++)
      Console::WriteLine("a[{0}] = {1}", i, a[i]);

   cout << "(managed) modifying array contents...\n";
   Random^ r = gcnew Random(DateTime::Now.Second);
   for (int i=0; i<c; i++)
      a[i] = r->Next(100);
}

#pragma unmanaged

void NativeFunc() {
   int nums[5] = { 0, 1, 2, 3, 4 };

   printf_s("(unmanaged) array created:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);

   ManagedTakesAnArray(nums, 5);

   printf_s("(ummanaged) contents:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);
}

#pragma managed

int main() {
   NativeFunc();
}
```

## <a name="see-also"></a>Zobacz też

[Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
