---
description: 'Dowiedz się więcej na temat: jak: kierowanie wskaźników funkcji przy użyciu PInvoke'
title: 'Porady: kierowanie wskaźników funkcji za pomocą funkcji PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: bfe3f669cf023ed914bdccb3ae15ccafefbb49c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302585"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Porady: kierowanie wskaźników funkcji za pomocą funkcji PInvoke

W tym temacie wyjaśniono, jak zarządzane Delegaty mogą być używane zamiast wskaźników funkcji podczas współdziałania z funkcjami niezarządzanymi przy użyciu .NET Framework funkcji P/Invoke. Jednak Visual C++ programiści są zachęcani do używania funkcji międzyoperacyjnych C++ (jeśli to możliwe), ponieważ funkcja P/Invoke zapewnia niewielkie raportowanie błędów w czasie kompilacji, nie jest bezpieczna pod względem typu i może być żmudnym do wdrożenia. Jeśli niezarządzany interfejs API jest spakowany jako biblioteka DLL, a kod źródłowy nie jest dostępny, jedyną opcją jest opcja P/Invoke. W przeciwnym razie zapoznaj się z następującymi tematami:

- [Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Instrukcje: kierowanie wywołań zwrotnych i delegatów za pomocą międzyoperacyjności języka C++](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

Niezarządzane interfejsy API, które przyjmują wskaźniki funkcji, jako argumenty mogą być wywoływane z kodu zarządzanego z zarządzanym delegatem zamiast wskaźnika funkcji natywnej. Kompilator automatycznie przekazuje delegatowi funkcje niezarządzane jako wskaźnik funkcji i wstawia niezbędny kod przejścia zarządzany/niezarządzany.

## <a name="example"></a>Przykład

Poniższy kod składa się z niezarządzanego i zarządzanego modułu. Moduł niezarządzany jest biblioteką DLL, która definiuje funkcję o nazwie TakesCallback, która akceptuje wskaźnik funkcji. Ten adres jest używany do wykonywania funkcji.

Moduł zarządzany definiuje delegata, który jest zorganizowany do kodu natywnego jako wskaźnik funkcji i używa <xref:System.Runtime.InteropServices.DllImportAttribute> atrybutu, aby udostępnić natywną funkcję TakesCallback w kodzie zarządzanym. W funkcji Main wystąpienie delegata jest tworzone i przesyłane do funkcji TakesCallback. Dane wyjściowe programu pokazują, że ta funkcja jest wykonywana przez natywną funkcję TakesCallback.

Funkcja zarządzana pomija wyrzucanie elementów bezużytecznych dla zarządzanego delegata, uniemożliwiając .NET Framework wyrzucanie elementów bezużytecznych z obiektu delegowanego podczas wykonywania funkcji natywnej.

```cpp
// TraditionalDll5.cpp
// compile with: /LD /EHsc
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   /* Declare an unmanaged function type that takes two int arguments
      Note the use of __stdcall for compatibility with managed code */
   typedef int (__stdcall *CALLBACK)(int);
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);
}

int TakesCallback(CALLBACK fp, int n) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n);
}
```

```cpp
// MarshalDelegate.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

public delegate int GetTheAnswerDelegate(int);
public value struct TraditionalDLL {
   [DllImport("TraditionalDLL5.dll")]
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);
};

int GetNumber(int n) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;
   return x + n;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TraditionalDLL::TakesCallback(fp, 42);
}
```

Należy zauważyć, że żadna część biblioteki DLL nie jest ujawniona w zarządzanym kodzie przy użyciu tradycyjnej dyrektywy #include. W rzeczywistości biblioteka DLL jest dostępna tylko w czasie wykonywania, dlatego problemy z funkcjami zaimportowanymi z <xref:System.Runtime.InteropServices.DllImportAttribute> nie zostaną wykryte w czasie kompilacji.

## <a name="see-also"></a>Zobacz też

[Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
