---
description: 'Dowiedz się więcej o: jak: kierowanie tablic za pomocą funkcji PInvoke'
title: 'Porady: przeprowadzanie marshalingu tablic za pomocą funkcji PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
ms.openlocfilehash: 90fd7b2cbefe2fb3621f512d49fbc088240922a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258228"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>Porady: przeprowadzanie marshalingu tablic za pomocą funkcji PInvoke

W tym temacie wyjaśniono, jak natywne funkcje, które akceptują ciągi w stylu C, można wywołać za pomocą typu ciągu CLR <xref:System.String> przy użyciu funkcji wywołania .NET Framework platformy. Visual C++ programiści są zachęcani do używania funkcji międzyoperacyjnych języka C++ (jeśli to możliwe), ponieważ funkcja P/Invoke zapewnia niewielkie raportowanie błędów w czasie kompilacji, nie jest bezpieczna pod względem typu i może być żmudnym do wdrożenia. Jeśli niezarządzany interfejs API jest spakowany jako biblioteka DLL, a kod źródłowy jest niedostępny, Metoda P/Invoke jest jedyną opcją (w przeciwnym razie zobacz [Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)).

## <a name="example"></a>Przykład

Ponieważ natywne i zarządzane tablice są rozmieszczone inaczej w pamięci, przekazanie ich pomyślnie przez granicę zarządzaną/niezarządzaną wymaga konwersji lub organizowania. W tym temacie pokazano, jak można przesłać tablicę elementów prostych (blitable) do funkcji natywnych z kodu zarządzanego.

Podobnie jak w przypadku zarządzania danymi zarządzanym/niezarządzanym, ten <xref:System.Runtime.InteropServices.DllImportAttribute> atrybut jest używany do tworzenia zarządzanego punktu wejścia dla każdej funkcji natywnej, która będzie używana. W przypadku funkcji, które pobierają tablice jako argumenty, <xref:System.Runtime.InteropServices.MarshalAsAttribute> atrybut musi być używany również do określenia kompilatora, w jaki sposób dane będą organizowane. W poniższym przykładzie <xref:System.Runtime.InteropServices.UnmanagedType> Wyliczenie służy do wskazywania, że zarządzana tablica będzie organizowana jako tablica w stylu C.

Poniższy kod składa się z niezarządzanego i zarządzanego modułu. Moduł niezarządzany jest biblioteką DLL, która określa funkcję, która akceptuje tablicę liczb całkowitych. Drugi moduł jest zarządzaną aplikacją wiersza polecenia, która importuje tę funkcję, ale definiuje ją w postaci tablicy zarządzanej i używa <xref:System.Runtime.InteropServices.MarshalAsAttribute> atrybutu, aby określić, że tablica powinna być konwertowana na tablicę natywną po wywołaniu.

Zarządzany moduł został skompilowany przy użyciu/CLR.

```cpp
// TraditionalDll4.cpp
// compile with: /LD /EHsc
#include <iostream>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);
}

void TakesAnArray(int len, int a[]) {
   printf_s("[unmanaged]\n");
   for (int i=0; i<len; i++)
      printf("%d = %d\n", i, a[i]);
}
```

```cpp
// MarshalBlitArray.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL {
   [DllImport("TraditionalDLL4.dll")]
   static public void TakesAnArray(
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);
};

int main() {
   array<int>^ b = gcnew array<int>(3);
   b[0] = 11;
   b[1] = 33;
   b[2] = 55;
   TraditionalDLL::TakesAnArray(3, b);

   Console::WriteLine("[managed]");
   for (int i=0; i<3; i++)
      Console::WriteLine("{0} = {1}", i, b[i]);
}
```

Należy zauważyć, że żadna część biblioteki DLL nie jest ujawniona w zarządzanym kodzie za pomocą tradycyjnego #include dyrektywy. W rzeczywistości, ponieważ biblioteka DLL jest dostępna tylko w czasie wykonywania, problemy z funkcjami zaimportowanymi za pomocą programu <xref:System.Runtime.InteropServices.DllImportAttribute> nie będą wykrywane w czasie kompilacji.

## <a name="see-also"></a>Zobacz też

[Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
