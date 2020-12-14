---
description: 'Dowiedz się więcej na temat: Instrukcje: kierowanie wskaźników osadzonych za pomocą funkcji PInvoke'
title: 'Porady: przeprowadzanie marshalingu wskaźników osadzonych za pomocą funkcji PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
ms.openlocfilehash: d31660a9a8ba345b380d442bb4484e332fe9d7cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302559"
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>Porady: przeprowadzanie marshalingu wskaźników osadzonych za pomocą funkcji PInvoke

Funkcje zaimplementowane w niezarządzanych bibliotekach DLL mogą być wywoływane z kodu zarządzanego za pomocą funkcji wywołania platformy (P/Invoke). Jeśli kod źródłowy biblioteki DLL nie jest dostępny, Metoda P/Invoke jest jedyną opcją dla współdziałania. Jednak, w przeciwieństwie do innych języków .NET, Visual C++ stanowi alternatywę dla P/Invoke. Aby uzyskać więcej informacji, zobacz [using C++ Interop (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) i [instrukcje: kierowanie wskaźników osadzonych za pomocą międzyoperacyjności języka c++](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).

## <a name="example"></a>Przykład

Przekazywanie struktur do kodu natywnego wymaga utworzenia struktury zarządzanej równoważnej pod względem układu danych do struktury natywnej. Jednak struktury zawierające wskaźniki wymagają specjalnej obsługi. Dla każdego osadzonego wskaźnika w strukturze natywnej zarządzana wersja struktury powinna zawierać wystąpienie <xref:System.IntPtr> typu. Ponadto pamięć dla tych wystąpień musi być jawnie przydzielona, zainicjowana i wydana przy <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A> użyciu <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A> metod, i <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> .

Poniższy kod składa się z niezarządzanego i zarządzanego modułu. Moduł niezarządzany jest biblioteką DLL, która określa funkcję akceptującą strukturę o nazwie ListString, która zawiera wskaźnik, i funkcję o nazwie TakesListStruct. Moduł zarządzany jest aplikacją wiersza polecenia, która importuje funkcję TakesListStruct i definiuje strukturę o nazwie MListStruct, która jest równoważna z natywnym ListStructem, z wyjątkiem tego, że Double * jest reprezentowane <xref:System.IntPtr> wystąpieniem. Przed wywołaniem TakesListStruct funkcja Main alokuje i inicjuje pamięć, do której odwołuje się to pole.

```cpp
// TraditionalDll6.cpp
// compile with: /EHsc /LD
#include <stdio.h>
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct ListStruct {
   int count;
   double* item;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API void TakesListStruct(ListStruct);
}

void TakesListStruct(ListStruct list) {
   printf_s("[unmanaged] count = %d\n", list.count);
   for (int i=0; i<list.count; i++)
      printf_s("array[%d] = %f\n", i, list.item[i]);
}
```

```cpp
// EmbeddedPointerMarshalling.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MListStruct {
   int count;
   IntPtr item;
};

value struct TraditionalDLL {
    [DllImport("TraditionalDLL6.dll")]
   static public void TakesListStruct(MListStruct);
};

int main() {
   array<double>^ parray = gcnew array<double>(10);
   Console::WriteLine("[managed] count = {0}", parray->Length);

   Random^ r = gcnew Random();
   for (int i=0; i<parray->Length; i++) {
      parray[i] = r->NextDouble() * 100.0;
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);
   }

   int size = Marshal::SizeOf(double::typeid);
   MListStruct list;
   list.count = parray->Length;
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);

   for (int i=0; i<parray->Length; i++) {
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);
      Marshal::StructureToPtr(parray[i], t, false);
   }

   TraditionalDLL::TakesListStruct( list );
   Marshal::FreeCoTaskMem(list.item);
}
```

Należy zauważyć, że żadna część biblioteki DLL nie jest ujawniona w zarządzanym kodzie przy użyciu tradycyjnej dyrektywy #include. W rzeczywistości biblioteka DLL jest dostępna tylko w czasie wykonywania, dlatego problemy z funkcjami zaimportowanymi z <xref:System.Runtime.InteropServices.DllImportAttribute> nie zostaną wykryte w czasie kompilacji.

## <a name="see-also"></a>Zobacz też

[Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
