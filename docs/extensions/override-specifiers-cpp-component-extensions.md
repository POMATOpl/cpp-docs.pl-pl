---
description: 'Dowiedz się więcej o: specyfikatory przesłonięcia (C++/CLI i C++/CX)'
title: Specyfikatory przesłonięć  (C++/CLI i C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: ce0b9ad4464eef66bc71826825e8129ef0a24cab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257592"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Specyfikatory przesłonięć  (C++/CLI i C++/CX)

*Specyfikatory przesłonięcia* modyfikują sposób, w jaki dziedziczone typy i elementy członkowskie dziedziczonych typów zachowują się w typach pochodnych.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat specyfikatorów zastąpienia, zobacz:

- [streszczeń](abstract-cpp-component-extensions.md)

- [new (nowe gniazdo w vtable)](new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- [Specyfikatory przesłonięcia i kompilacje natywne](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**abstrakcyjne** i **zapieczętowane** są również prawidłowe dla deklaracji typu, gdzie nie działają jako specyfikatory przesłonięcia.

Aby uzyskać informacje na temat jawnego przesłaniania funkcji klasy podstawowej, zobacz [jawne przesłonięcia](explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

(Nie ma żadnych uwag dla tej funkcji języka, które mają zastosowanie tylko do środowisko wykonawcze systemu Windows).

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/ZW`

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

(Nie ma żadnych uwag dla tej funkcji języka, które mają zastosowanie tylko do środowiska uruchomieniowego języka wspólnego).

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platform .NET i platformy UWP](component-extensions-for-runtime-platforms.md)
