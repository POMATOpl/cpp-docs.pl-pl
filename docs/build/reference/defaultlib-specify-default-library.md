---
description: Dowiedz się więcej o:/DEFAULTLIB (Określ bibliotekę domyślną)
title: /DEFAULTLIB (Określ bibliotekę domyślną)
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
ms.openlocfilehash: 9abaf158ed01b3e0a04d29c55d213c8749462c43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201693"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Określ bibliotekę domyślną)

Określ domyślną bibliotekę do wyszukania, aby rozpoznać odwołania zewnętrzne.

## <a name="syntax"></a>Składnia

> **/DEFAULTLIB**:_Biblioteka_

### <a name="arguments"></a>Argumenty

*biblioteki*<br/>
Nazwa biblioteki do przeszukania podczas rozpoznawania odwołań zewnętrznych.

## <a name="remarks"></a>Uwagi

Opcja **/DEFAULTLIB** dodaje jedną *bibliotekę* do listy bibliotek, które łączą wyszukiwanie podczas rozpoznawania odwołań. Biblioteka określona za pomocą **/DEFAULTLIB** jest przeszukiwana po określeniu bibliotek jawnie w wierszu polecenia i przed domyślnymi bibliotekami nazwanymi w plikach. obj.

W przypadku użycia bez argumentów opcja [/NODEFAULTLIB (Ignoruj wszystkie biblioteki domyślne)](nodefaultlib-ignore-libraries.md) zastępuje wszystkie opcje **/DEFAULTLIB**:*Library* . Opcja **/NODEFAULTLIB**:*Library* przesłania **/DEFAULTLIB**:*Library* , gdy ta sama nazwa *biblioteki* jest określona w obu.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja właściwości**  >    >  **wiersza polecenia** konsolidatora.

1. W obszarze **Opcje dodatkowe** wprowadź opcję **/DEFAULTLIB**:*Library* dla każdej biblioteki do przeszukania. Wybierz **przycisk OK** , aby zapisać zmiany.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja konsolidatora MSVC](linking.md)
- [MSVC Opcje konsolidatora](linker-options.md)
