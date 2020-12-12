---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1309'
title: Błąd narzędzi konsolidatora LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: e04498ae5226f748b6ba5cc2ce0cd9340f4547c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193646"
---
# <a name="linker-tools-error-lnk1309"></a>Błąd narzędzi konsolidatora LNK1309

> Wykryto moduł *Type1* ; Nieprawidłowy z przełącznikiem/CLRIMAGETYPE:*Type2*

## <a name="remarks"></a>Uwagi

Zażądano typu obrazu CLR z **/CLRIMAGETYPE** , ale konsolidator nie może utworzyć obrazu tego typu, ponieważ co najmniej jeden moduł był niezgodny z tym typem.

Na przykład zobaczysz LNK1309, jeśli określisz **/CLRIMAGETYPE: Safe** i przekażesz Moduł skompilowany z **/CLR: Pure**.

**/CLR: Pure** i **/CLR: bezpieczne** opcje kompilatora i biblioteki obsługi są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Zobaczysz również LNK1309, jeśli próbujesz skompilować częściowo zaufaną czystą aplikację CLR przy użyciu ptrustu [d]. lib. Aby uzyskać informacje na temat sposobu tworzenia częściowo zaufanej aplikacji, zobacz [jak to zrobić: Tworzenie częściowo zaufanej aplikacji przez usunięcie zależności od biblioteki dll Biblioteka CRT](../../dotnet/create-a-partially-trusted-application.md).

Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md) i [/CLRIMAGETYPE (Określ typ obrazu CLR)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).
