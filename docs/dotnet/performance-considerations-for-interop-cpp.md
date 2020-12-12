---
description: 'Dowiedz się więcej o programie: zagadnienia dotyczące wydajności międzyoperacyjności (C++)'
title: Zagadnienia dotyczące wydajności związane z międzyoperacyjnością (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
ms.openlocfilehash: 29723f0ea5c7b745100ab4c7abb7f59abce47db6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255564"
---
# <a name="performance-considerations-for-interop-c"></a>Zagadnienia dotyczące wydajności związane z międzyoperacyjnością (C++)

Ten temat zawiera wskazówki dotyczące ograniczania wpływu zarządzanych/niezarządzanych przejść międzyoperacyjnych na wydajność w czasie wykonywania.

Visual C++ obsługuje te same mechanizmy współdziałania jak inne języki .NET, takie jak Visual Basic i C# (P/Invoke), ale również zapewnia obsługę międzyoperacyjną, która jest specyficzna dla Visual C++ (międzyoperacyjności C++). W przypadku aplikacji o krytycznym znaczeniu należy zrozumieć wpływ na wydajność poszczególnych technik międzyoperacyjnych.

Niezależnie od używanej metody międzyoperacyjności, specjalne sekwencje przejścia o nazwie sekcje thunk są wymagane za każdym razem, gdy funkcja zarządza wywołuje niezarządzaną funkcję i odwrotnie. Te sekcje thunk są wstawiane automatycznie przez kompilator języka Microsoft C++, ale ważne jest, aby pamiętać, że te przejścia mogą być kosztowne w zakresie wydajności.

## <a name="reducing-transitions"></a>Zmniejszanie przejść

Jednym ze sposobów uniknięcia lub obniżenia kosztów współdziałania sekcje thunk jest Refaktoryzacja interfejsów mających na celu zminimalizowanie niezarządzanych/niezarządzanych przejść. Znaczne ulepszenia wydajności mogą być realizowane przez kierowanie interfejsów, które są związane z częstymi wywołaniami w granicach zarządzanych/niezarządzanych. Funkcja zarządzana, która wywołuje funkcję niezarządzaną w ścisłej pętli, na przykład jest dobrym kandydatem do refaktoryzacji. Jeśli sama pętla jest przenoszona do niezarządzanej strony lub jeśli zarządzana alternatywa dla wywołania niezarządzanego zostanie utworzona (może to być usługa kolejkowania danych po stronie zarządzanej, a następnie przekierowanie go do niezarządzanego interfejsu API wszystkie jednocześnie po pętli), liczba przejść może być znacznie ograniczona.

## <a name="pinvoke-vs-c-interop"></a>Rozdziałanie P/Invoke a C++

W przypadku języków .NET, takich jak Visual Basic i C#, zalecana metoda współdziałania ze składnikami natywnymi jest P/Invoke. Ponieważ metoda P/Invoke jest obsługiwana przez .NET Framework, Visual C++ ją obsługuje, ale Visual C++ również zapewnia obsługę współdziałania, która jest określana jako międzyoperacyjna C++. Międzyoperacyjność języka C++ jest preferowana za pośrednictwem metody P/Invoke, ponieważ metoda P/Invoke nie jest bezpieczna pod względem typu. W związku z tym błędy są raportowane przede wszystkim w czasie wykonywania, ale międzyoperacyjna C++ również ma zalety wydajności za pośrednictwem elementu P/Invoke.

Obie techniki wymagają kilku rzeczy, gdy zarządzana funkcja wywołuje niezarządzaną funkcję:

- Argumenty wywołania funkcji są organizowane z CLR do typów natywnych.

- Wykonywane jest thunk zarządzane do niezarządzanej.

- Funkcja niezarządzana jest wywoływana (przy użyciu natywnych wersji argumentów).

- Wykonywany jest thunk niezarządzana do zarządzania.

- Typ zwracany i wszystkie argumenty "out" lub "in" out są organizowane z natywnych typów CLR.

Zarządzane/niezarządzane sekcje thunk są niezbędne, aby współdziałanie działało, ale wymagane jest kierowanie danych zależne od typów danych, sygnatury funkcji i sposobu użycia danych.

Kierowanie danych przez C++ Interop jest najprostszym możliwym formularzem: parametry są po prostu kopiowane między granicami zarządzana/niezarządzana w sposób bitowy; żadne przekształcenie nie jest wykonywane wcale. Dla elementu P/Invoke ten element ma wartość true tylko wtedy, gdy wszystkie parametry są proste, typy danych kopiowalnych. W przeciwnym razie P/Invoke wykonuje bardzo niezawodne kroki, aby przekonwertować każdy zarządzany parametr na odpowiedni typ natywny, i na odwrót, jeśli argumenty są oznaczone jako "out" lub "in, out".

Innymi słowy, międzyoperacyjna C++ używa najszybszej możliwej metody organizowania danych, natomiast P/Invoke korzysta z najbardziej niezawodnej metody. Oznacza to, że międzyoperacyjna C++ (w sposób typowy dla języka C++) zapewnia optymalną wydajność, a programista jest odpowiedzialny za adresowanie przypadków, w których takie zachowanie nie jest bezpieczne lub odpowiednie.

Międzyoperacyjność języka C++ wymaga w związku z tym, że kierowanie danych musi być jawnie określone, ale zaletą jest to, że programista może podejmować decyzje dotyczące rodzaju danych i sposobu ich użycia. Ponadto, chociaż zachowanie organizowania danych P/Invoke można zmodyfikować w dostosowany do stopnia, międzyoperacyjności języka C++ umożliwia dostosowanie organizowania danych na zasadzie wywołania przez wywołanie. Nie jest to możliwe przy użyciu elementu P/Invoke.

Aby uzyskać więcej informacji na temat międzyoperacyjności języka C++, zobacz [using C++ Interop (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="see-also"></a>Zobacz też

[Zestawy mieszane (natywne i zarządzane)](../dotnet/mixed-native-and-managed-assemblies.md)
