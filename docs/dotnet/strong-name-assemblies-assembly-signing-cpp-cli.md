---
description: Dowiedz się więcej o zestawach o silnych nazwach (podpisywanie zestawów) (C++/CLI)
title: Zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: 9fc08df759fa384ed13dbe3d8c3eb2d843183517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335321"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)

W tym temacie omówiono sposób podpisywania zestawu, często nazywanego nadawaniem silnej nazwy zestawu.

## <a name="remarks"></a>Uwagi

W przypadku korzystania z Visual C++ Użyj opcji konsolidatora, aby podpisać zestaw, aby uniknąć problemów związanych z atrybutami CLR dla podpisywania zestawu:

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

Powody nieużywania atrybutów to fakt, że nazwa klucza jest widoczna w metadanych zestawu, co może stanowić zagrożenie bezpieczeństwa, jeśli nazwa pliku zawiera poufne informacje. Ponadto proces kompilacji używany przez środowisko deweloperskie Visual C++ unieważnia klucz, z którym jest podpisany zestaw, jeśli używasz atrybutów CLR do przydzielenia zestawu silną nazwą, a następnie uruchomisz narzędzie do przetwarzania końcowego, takie jak mt.exe na zestawie.

Jeśli kompilujesz w wierszu polecenia, użyj opcji konsolidatora, aby podpisać zestaw, a następnie uruchomisz narzędzie do przetwarzania końcowego (takie jak mt.exe), należy ponownie podpisać zestaw przy użyciu sn.exe. Alternatywnie można skompilować i opóźnić podpisywanie zestawu i po uruchomieniu narzędzi do przetwarzania końcowego wykonaj podpisywanie.

Jeśli używasz atrybutów podpisywania podczas kompilowania w środowisku programistycznym, możesz pomyślnie podpisać zestaw, jawnie wywołując sn.exe[Sn.exe (Narzędzie silnej nazwy)](/dotnet/framework/tools/sn-exe-strong-name-tool)) w zdarzeniu po kompilacji. Aby uzyskać więcej informacji, zobacz [Określanie zdarzeń kompilacji](../build/specifying-build-events.md). Czasy kompilacji mogą być mniejsze w przypadku używania atrybutów i zdarzenia wykonywanego po kompilacji w porównaniu z użyciem opcji konsolidatora.

Następujące opcje konsolidatora obsługują podpisywanie zestawów:

- [/DELAYSIGN (częściowo podpisz zestaw)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (Określ klucz lub parę kluczy, aby podpisać zestaw)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (Określ klucz kontenera, aby podpisać zestaw)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Aby uzyskać więcej informacji na temat silnych zestawów, zobacz [Tworzenie i używanie zestawów Strong-Named](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

## <a name="see-also"></a>Zobacz też

[Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
