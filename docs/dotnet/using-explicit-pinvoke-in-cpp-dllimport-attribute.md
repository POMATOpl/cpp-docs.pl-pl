---
description: Dowiedz się więcej o tym, jak używać jawnej funkcji PInvoke w języku C++ (atrybut DllImport)
title: Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
ms.openlocfilehash: 6c49195cdb677474809435a5bd826808260680e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305481"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)

.NET Framework zapewnia jawne funkcje wywołania platformy (lub PInvoke) z `Dllimport` atrybutem umożliwiającym aplikacjom zarządzanym wywoływanie funkcji niezarządzanych spakowanych wewnątrz bibliotek DLL. Jawna wartość PInvoke jest wymagana w sytuacjach, gdy niezarządzane interfejsy API są spakowane jako biblioteki DLL, a kod źródłowy jest niedostępny. Na przykład wywoływanie funkcji Win32 Functions wymaga elementu PInvoke. W przeciwnym razie użyj niejawnego P {Invoke; zobacz [using C++ Interop (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) , aby uzyskać więcej informacji.

Działanie PInvoke działa przy użyciu <xref:System.Runtime.InteropServices.DllImportAttribute> . Ten atrybut, który przyjmuje nazwę biblioteki DLL jako pierwszy argument, jest umieszczany przed deklaracją funkcji dla każdego punktu wejścia biblioteki DLL, który będzie używany. Sygnatura funkcji musi być zgodna z nazwą funkcji wyeksportowanej przez DLL (ale niektóre konwersje typów można wykonać niejawnie przez zdefiniowanie `DllImport` deklaracji w postaci typów zarządzanych).

Wynikiem jest zarządzany punkt wejścia dla każdej natywnej funkcji DLL, która zawiera wymagany kod przejścia (lub thunk) oraz proste konwersje danych. Funkcje zarządzane mogą następnie wywołać do biblioteki DLL za pomocą tych punktów wejścia. Kod wstawiony do modułu jako wynik funkcji PInvoke jest całkowicie zarządzany.

## <a name="in-this-section"></a>W tej sekcji

- [Wywoływanie funkcji natywnych z kodu zarządzanego](../dotnet/calling-native-functions-from-managed-code.md)

- [Instrukcje: wywoływanie natywnych bibliotek DLL z kodu zarządzanego za pomocą funkcji PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)

- [Instrukcje: kierowanie ciągów za pomocą funkcji PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)

- [Instrukcje: kierowanie struktur za pomocą funkcji PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)

- [Instrukcje: kierowanie tablic za pomocą funkcji PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)

- [Instrukcje: kierowanie wskaźników funkcji przy użyciu PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)

- [Instrukcje: kierowanie wskaźników osadzonych za pomocą funkcji PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)

## <a name="see-also"></a>Zobacz też

[Wywoływanie funkcji natywnych z kodu zarządzanego](../dotnet/calling-native-functions-from-managed-code.md)
