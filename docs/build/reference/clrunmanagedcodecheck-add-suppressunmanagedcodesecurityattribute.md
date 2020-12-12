---
description: Dowiedz się więcej na temat:/CLRUNMANAGEDCODECHECK (Usuń SuppressUnmanagedCodeSecurityAttribute)
title: /CLRUNMANAGEDCODECHECK (Usuń atrybut SuppressUnmanagedCodeSecurityAttribute)
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.openlocfilehash: e08b7b4b18a463122316b041ad81d6ddd2598bca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182401"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (Usuń atrybut SuppressUnmanagedCodeSecurityAttribute)

**/CLRUNMANAGEDCODECHECK** określa, że konsolidator nie stosuje <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> się do wywołań generowanych `PInvoke` przez konsolidator z kodu zarządzanego do natywnych bibliotek DLL.

## <a name="syntax"></a>Składnia

> **/CLRUNMANAGEDCODECHECK**[**: No**]

## <a name="remarks"></a>Uwagi

Domyślnie konsolidator stosuje **SuppressUnmanagedCodeSecurityAttribute** do wywołań generowanych przez konsolidator `PInvoke` . Gdy **/CLRUNMANAGEDCODECHECK** jest w praktyce, **SuppressUnmanagedCodeSecurityAttribute** jest usuwany. Aby jawnie zastosować **SuppressUnmanagedCodeSecurityAttribute** do wywołań generowanych przez konsolidator `PInvoke` , można użyć **/CLRUNMANAGEDCODECHECK: No**.

Konsolidator dodaje tylko atrybut do obiektów, które są kompilowane przy użyciu **/CLR** lub **/CLR: Pure**. Jednak opcja " **/CLR: Pure** kompilator" jest przestarzała w programie visual Studio 2015 i nie jest obsługiwana w programie visual Studio 2017 lub nowszym.

`PInvoke`Wywołanie jest generowane przez konsolidator, gdy konsolidator nie może znaleźć zarządzanego symbolu, aby spełnić odwołanie z zarządzanego obiektu wywołującego, ale może znaleźć symbol macierzysty, aby spełnić to odwołanie. Aby uzyskać więcej informacji na temat `PInvoke` , zobacz [wywoływanie funkcji natywnych z kodu zarządzanego](../../dotnet/calling-native-functions-from-managed-code.md).

Należy pamiętać, że jeśli używasz <xref:System.Security.AllowPartiallyTrustedCallersAttribute> w kodzie, należy jawnie ustawić **/CLRUNMANAGEDCODECHECK** , aby usunąć atrybut **SuppressUnmanagedCodeSecurity** . Jest to potencjalna Luka w zabezpieczeniach, jeśli obraz zawiera zarówno atrybuty **SuppressUnmanagedCodeSecurity** , jak i **AllowPartiallyTrustedCallers** .

Aby uzyskać więcej informacji na temat skutków używania **SuppressUnmanagedCodeSecurityAttribute**, zobacz artykuł [dotyczący bezpiecznych zasad kodowania dla niezarządzanego kodu](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji** .

1. Rozwiń węzeł **konsolidatora** .

1. Wybierz stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **sprawdzania kodu niezarządzanego CLR** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja konsolidatora MSVC](linking.md)
- [MSVC Opcje konsolidatora](linker-options.md)
