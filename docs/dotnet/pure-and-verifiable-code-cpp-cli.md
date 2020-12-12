---
description: 'Dowiedz się więcej na temat: Kod czysty i możliwy do zweryfikowania (C++/CLI)'
title: Kod czysty i weryfikowalny (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
ms.openlocfilehash: 64224f7f462b5e11e522648a5b64ec9d568dc53f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276767"
---
# <a name="pure-and-verifiable-code-ccli"></a>Kod czysty i możliwy do zweryfikowania (C++/CLI)

W przypadku programowania .NET Visual C++ w programie Visual Studio 2017 obsługuje tworzenie zestawów mieszanych za pomocą opcji kompilatora [/CLR (Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md) . **/CLR: Pure** i **CLR: opcje bezpieczne** są przestarzałe w programie Visual Studio 2015 i nie są obsługiwane w programie Visual Studio 2017. Jeśli kod musi być bezpieczny lub możliwy do zweryfikowania, zalecamy przekazanie go do języka C#.

## <a name="mixed-clr"></a>Mieszany (/CLR)

Zestawy mieszane (skompilowane z **/CLR**) zawierają części niezarządzane i zarządzane, dzięki czemu mogą korzystać z funkcji platformy .NET, ale nadal zawierają kod natywny. Pozwala to zaktualizować aplikacje i składniki do korzystania z funkcji platformy .NET bez konieczności przepisania całego projektu. Używanie Visual C++ do mieszania kodu zarządzanego i natywnego w ten sposób jest nazywana C++ Interop. Aby uzyskać więcej informacji, zobacz [zestawy mieszane (natywne i zarządzane)](../dotnet/mixed-native-and-managed-assemblies.md) oraz [Współdziałanie natywne i .NET](../dotnet/native-and-dotnet-interoperability.md).

Wywołania wykonane z zestawów zarządzanych do natywnych bibliotek DLL za pośrednictwem metody P/Invoke będą kompilować, ale mogą kończyć się niepowodzeniem w czasie wykonywania w zależności od ustawień zabezpieczeń.

Istnieje jeden scenariusz kodowania, który przekaże kompilator, ale spowoduje to niemożliwy do zweryfikowania zestaw: wywoływanie funkcji wirtualnej za pośrednictwem wystąpienia obiektu za pomocą operatora rozpoznawania zakresu.  Na przykład: `MyObj -> A::VirtualFunction();`.

## <a name="see-also"></a>Zobacz też

- [Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
