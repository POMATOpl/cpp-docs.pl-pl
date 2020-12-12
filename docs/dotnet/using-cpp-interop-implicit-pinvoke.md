---
description: 'Dowiedz się więcej o programie: korzystanie z międzyoperacyjności C++ (niejawne PInvoke)'
title: Korzystanie z międzyoperacyjności języka C++ (niejawna funkcja PInvoke)
ms.date: 11/04/2016
helpviewer_keywords:
- blittable types [C++]
- platform invoke [C++], implicit
- interop [C++], features
- data marshaling [C++], C++ Interop features
- porting [C++], C++ native to .NET
- COM interfaces [C++]
- implicit platform invoke
- examples [C++], interoperability
- types [C++], blittable
- marshaling [C++], C++ Interop features
- platform invoke [C++], examples
- interoperability [C++]
- C++ Interop
- interoperability [C++], Implicit PInvoke
- C++, interop
- C++ COM Interop
- .NET [C++], porting C++ native to
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
ms.openlocfilehash: e2b1f1aeef68fd6329ef04a53249d7dce627f2c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255551"
---
# <a name="using-c-interop-implicit-pinvoke"></a>Korzystanie z międzyoperacyjności języka C++ (niejawna funkcja PInvoke)

W przeciwieństwie do innych języków .NET Visual C++ ma obsługę współdziałania, która umożliwia kod zarządzany i niezarządzany w tej samej aplikacji, a nawet w tym samym pliku (z [zarządzanymi, niezarządzanymi](../preprocessor/managed-unmanaged.md) pragmami). Dzięki temu Visual C++ deweloperzy mogą zintegrować funkcje platformy .NET z istniejącymi aplikacjami Visual C++ bez zakłócania pozostałej części aplikacji.

Można również wywołać funkcje niezarządzane z zarządzanego jednostka kompilacji przy użyciu [dllexport, dllimport](../cpp/dllexport-dllimport.md).

Niejawny PInvoke jest przydatny, gdy nie trzeba określać, jak będą organizowane parametry funkcji lub inne szczegóły, które można określić podczas jawnego wywoływania elementu DllImportAttribute.

Visual C++ zapewnia dwa sposoby współdziałania z funkcjami zarządzanymi i niezarządzanymi:

- [Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Jawna wartość PInvoke jest obsługiwana przez .NET Framework i jest dostępna w większości języków .NET. Ale jako że jego nazwa oznacza, że międzyoperacyjna C++ jest specyficzna dla Visual C++.

## <a name="c-interop"></a>międzyoperacyjność C++

C++ Interop zapewnia lepszą bezpieczeństwo typów i jest zazwyczaj mniej żmudnym do wdrożenia. Jednak międzyoperacyjna C++ nie jest opcją, jeśli niezarządzany kod źródłowy jest niedostępny lub dla projektów międzyplatformowych.

## <a name="c-com-interop"></a>współdziałanie języka C++ z modelem COM

Funkcje współdziałania obsługiwane przez program Visual C++ oferują konkretną korzyść w porównaniu z innymi językami .NET, gdy chodzi o współdziałanie ze składnikami modelu COM. Zamiast ograniczać się do ograniczeń [Tlbimp.exe .NET Framework (Importer biblioteki typów)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), takich jak ograniczona obsługa typów danych i obowiązkowe narażenie każdego członka każdego z interfejsów COM, międzyoperacyjna C++ umożliwia dostęp do składników com w i nie wymaga oddzielnych zestawów międzyoperacyjnych. W przeciwieństwie do Visual Basic i C#, Visual C++ może używać obiektów COM bezpośrednio przy użyciu standardowych mechanizmów COM (takich jak funkcja **CoCreateInstance** i **QueryInterface**). Jest to możliwe z powodu funkcji międzyoperacyjnych języka C++, które powodują, że kompilator automatycznie wstawia kod przejścia do przenoszenia z zarządzanych do funkcji niezarządzanych i ponownie z powrotem.

Za pomocą międzyoperacyjności języka C++ można używać składników COM, ponieważ są one zwykle używane lub mogą być opakowane wewnątrz klas języka C++. Te klasy otoki są nazywane niestandardowymi otokami w środowisku uruchomieniowym lub CRCWs i mają dwie zalety użycia modelu COM bezpośrednio w kodzie aplikacji:

- Klasa będąca wynikiem może być używana z języków innych niż Visual C++.

- Szczegóły interfejsu COM można ukryć w kodzie zarządzanego klienta. Typy danych platformy .NET mogą być używane zamiast typów natywnych, a szczegółowe informacje o kierowaniu danych mogą być wykonywane w sposób przezroczysty wewnątrz CRCW.

Bez względu na to, czy COM jest używany bezpośrednio, czy za pomocą CRCW, typy argumentów inne niż proste, typy danych kopiowalnych muszą być organizowane.

## <a name="blittable-types"></a>Typy danych kopiowalnych

W przypadku niezarządzanych interfejsów API, które używają prostych typów wewnętrznych (zobacz [typy danych kopiowalnych i inne niż danych kopiowalnych](/dotnet/framework/interop/blittable-and-non-blittable-types)), nie jest wymagane żadne specjalne kodowanie, ponieważ te typy danych mają tę samą reprezentację w pamięci, ale bardziej złożone typy danych wymagają jawnego organizowania danych. Aby zapoznać się z przykładem, zobacz [jak: wywoływanie natywnych bibliotek DLL z kodu zarządzanego za pomocą funkcji PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).

## <a name="example"></a>Przykład

```cpp
// vcmcppv2_impl_dllimp.cpp
// compile with: /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

// Implicit DLLImport specifying calling convention
extern "C" int __stdcall MessageBeep(int);

// explicit DLLImport needed here to use P/Invoke marshalling because
// System::String ^ is not the type of the first parameter to printf
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]
// or just
// [DllImport("msvcrt.dll")]
int printf(System::String ^, ...);

int main() {
   // (string literals are System::String by default)
   printf("Begin beep\n");
   MessageBeep(100000);
   printf("Done\n");
}
```

```Output
Begin beep
Done
```

## <a name="in-this-section"></a>W tej sekcji

- [Instrukcje: kierowanie ciągów ANSI przy użyciu międzyoperacyjności języka C++](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Instrukcje: kierowanie ciągów Unicode przy użyciu międzyoperacyjności języka C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Instrukcje: kierowanie ciągów COM za pomocą międzyoperacyjności języka C++](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [Instrukcje: kierowanie struktur za pomocą międzyoperacyjności języka C++](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [Instrukcje: kierowanie tablic za pomocą międzyoperacyjności języka C++](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [Instrukcje: kierowanie wywołań zwrotnych i delegatów za pomocą międzyoperacyjności języka C++](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [Instrukcje: kierowanie wskaźników osadzonych za pomocą międzyoperacyjności języka C++](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [Instrukcje: dostęp do znaków w elemencie System:: String](../dotnet/how-to-access-characters-in-a-system-string.md)

- [Instrukcje: konwertowanie ciągu char * na tablicę System:: Byte](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [Instrukcje: konwertowanie system:: String na wchar_t * lub char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Instrukcje: konwertowanie typu System:: String na ciąg standardowy](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Instrukcje: konwertowanie ciągu standardowego na system:: String](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Instrukcje: uzyskiwanie wskaźnika do tablicy typu Byte](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Instrukcje: ładowanie zasobów niezarządzanych do tablicy typu Byte](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Instrukcje: modyfikowanie klasy referencyjnej w funkcji natywnej](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Instrukcje: ustalanie, czy obraz jest natywny czy CLR](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Instrukcje: Dodawanie natywnej biblioteki DLL do globalnej pamięci podręcznej zestawów](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Instrukcje: utrzymywanie odwołania do typu wartości w typie natywnym](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Instrukcje: utrzymywanie odwołania do obiektu w pamięci niezarządzanej](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Instrukcje: Wykrywanie kompilacji/CLR](../dotnet/how-to-detect-clr-compilation.md)

- [Instrukcje: konwertowanie między system:: GUID i _GUID](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Instrukcje: Określanie parametru out](../dotnet/how-to-specify-an-out-parameter.md)

- [Instrukcje: korzystanie z typu natywnego w kompilacji/CLR](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Instrukcje: deklarowanie dojść w typach natywnych](../dotnet/how-to-declare-handles-in-native-types.md)

- [Instrukcje: Zawijanie klasy natywnej do użycia przez C #](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Aby uzyskać informacje na temat korzystania z delegatów w scenariuszu międzyoperacyjnym, zobacz [Delegat (C++ Component Extensions)](../extensions/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>Zobacz też

- [Wywoływanie funkcji natywnych z kodu zarządzanego](../dotnet/calling-native-functions-from-managed-code.md)
