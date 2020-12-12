---
description: 'Dowiedz się więcej na temat: jak utworzyć częściowo zaufaną aplikację, usuwając zależność od biblioteki DLL bibliotek CRT'
title: 'Instrukcje: Tworzenie częściowo zaufanej aplikacji (C++/CLI)'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: 937262595df4415d5620b60d9ccd8c17a6c44abf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124283"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Porady: tworzenie aplikacji częściowo zaufanej przez usunięcie zależności od biblioteki DLL środowiska CRT

W tym temacie omówiono sposób tworzenia częściowo zaufanej aplikacji środowiska uruchomieniowego języka wspólnego przy użyciu Visual C++, usuwając zależność od msvcm90.dll.

Aplikacja Visual C++ skompilowana z **/CLR** będzie miała zależność od msvcm90.dll, która jest częścią biblioteki środowiska uruchomieniowego C. Jeśli chcesz, aby aplikacja była używana w środowisku częściowej relacji zaufania, środowisko CLR wymusi pewne reguły zabezpieczeń dostępu kodu w bibliotece DLL. W związku z tym konieczne będzie usunięcie tej zależności, ponieważ msvcm90.dll zawiera kod natywny, a zasady zabezpieczeń dostępu kodu nie mogą być wymuszane na tym komputerze.

Jeśli aplikacja nie korzysta z żadnej funkcji biblioteki środowiska uruchomieniowego C i chcesz usunąć zależność od tej biblioteki z kodu, musisz użyć opcji konsolidatora **/NODEFAULTLIB: msvcmrt. lib** , a następnie połączyć się z ptrustm. lib lub ptrustmd. lib. Te biblioteki zawierają pliki obiektów do zainicjowania i odinicjowania aplikacji, klasy wyjątków używane przez kod inicjujący oraz kod obsługi wyjątków zarządzanych. Łączenie w jednej z tych bibliotek spowoduje usunięcie każdej zależności od msvcm90.dll.

> [!NOTE]
> Kolejność inicjacji zestawu może się różnić w przypadku aplikacji korzystających z bibliotek ptrust. W przypadku normalnych aplikacji zestawy są zwykle zwalniane w kolejności odwrotnej, które są ładowane, ale nie jest to gwarantowane. W przypadku aplikacji częściowo zaufanych zestawy są zwykle zwalniane w takiej samej kolejności, w jakiej zostały załadowane. Jest to również niegwarantowane.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Aby utworzyć częściowo zaufaną aplikację Mixed (/CLR)

1. Aby usunąć zależność od msvcm90.dll, należy określić dla konsolidatora, aby nie dołączać tej biblioteki przy użyciu opcji konsolidatora **/NODEFAULTLIB: msvcmrt. lib** . Aby uzyskać informacje o tym, jak to zrobić za pomocą środowiska programistycznego programu Visual Studio lub programowo, zobacz [/NODEFAULTLIB (ignore](../build/reference/nodefaultlib-ignore-libraries.md)librarys).

1. Dodaj jedną z bibliotek ptrustm do zależności wejściowych konsolidatora. Użyj ptrustm. lib, jeśli tworzysz aplikację w trybie wydania. Dla trybu debugowania Użyj ptrustmd. lib. Aby uzyskać informacje o tym, jak to zrobić za pomocą środowiska programistycznego Visual Studio lub programowo, zobacz [. Pliki lib jako dane wejściowe konsolidatora](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>Zobacz też

[Zestawy mieszane (natywne i zarządzane)](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Inicjowanie zestawów mieszanych](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[Obsługa bibliotek dla zestawów mieszanych](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/Link (Przekaż opcje do konsolidatora)](../build/reference/link-pass-options-to-linker.md)
