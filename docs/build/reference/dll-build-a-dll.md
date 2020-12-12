---
description: Dowiedz się więcej na temat:/DLL (Kompilowanie biblioteki DLL)
title: /DLL (Kompilowanie biblioteki DLL)
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: 42535fb15762e5c0f1691d5c28029c7368005f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201407"
---
# <a name="dll-build-a-dll"></a>/DLL (Kompilowanie biblioteki DLL)

```
/DLL
```

## <a name="remarks"></a>Uwagi

Opcja/DLL kompiluje bibliotekę DLL jako główny plik wyjściowy. Biblioteka DLL zwykle zawiera eksporty, które mogą być używane przez inny program. Istnieją trzy metody określania eksportu, wymienione w zalecanej kolejności użycia:

1. [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) w kodzie źródłowym

1. Instrukcja [eksportu](exports.md) w pliku. def

1. Specyfikacja [/Export](export-exports-a-function.md) w POleceniu linku

Program może używać więcej niż jednej metody.

Innym sposobem na skompilowanie biblioteki DLL jest z instrukcją definicji modułu **biblioteki** . Opcje/BASE i/DLL razem są równoważne instrukcji **Library** .

Nie określaj tej opcji w środowisku programistycznym; Ta opcja jest używana tylko w wierszu polecenia. Ta opcja jest ustawiana podczas tworzenia projektu DLL za pomocą Kreatora aplikacji.

Należy pamiętać, że jeśli utworzysz bibliotekę importu w ramach wstępnego kroku przed utworzeniem biblioteki. dll, musisz przekazać ten sam zestaw plików obiektów podczas kompilowania biblioteki.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **Właściwości konfiguracji** .

1. Kliknij stronę właściwości **Ogólne** .

1. Zmodyfikuj właściwość **Typ konfiguracji** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
