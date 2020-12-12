---
description: Dowiedz się więcej na temat:/APPCONTAINER (aplikacja Microsoft Store)
title: /APPCONTAINER (aplikacja platformy UWP/Microsoft Store)
ms.date: 11/04/2016
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
ms.openlocfilehash: 4cb78c85aa59ebd7fc0eb82af9497606bc3c431c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179580"
---
# <a name="appcontainer-microsoft-store-app"></a>/APPCONTAINER (aplikacja Microsoft Store)

Określa, czy konsolidator tworzy obraz wykonywalny, który musi być uruchamiany w kontenerze aplikacji.

## <a name="syntax"></a>Składnia

```
/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Uwagi

Domyślnie/APPCONTAINER jest wyłączona.

Ta opcja modyfikuje plik wykonywalny, aby wskazać, czy aplikacja musi być uruchamiana w środowisku izolacji procesu kontenera aplikacji. Określ/APPCONTAINER dla aplikacji, która musi być uruchamiana w środowisku APPCONTAINER — na przykład platforma uniwersalna systemu Windows (platformy UWP) lub Windows Phone 8. x aplikacji. (Opcja jest ustawiana automatycznie w programie Visual Studio podczas tworzenia aplikacji uniwersalnej systemu Windows na podstawie szablonu). W przypadku aplikacji klasycznej należy określić/APPCONTAINER: NO lub po prostu pominąć opcję.

Opcja/APPCONTAINER została wprowadzona w systemie Windows 8.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Aby ustawić tę opcję konsolidatora w programie Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji** .

1. Rozwiń węzeł **konsolidatora** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. W obszarze **Opcje dodatkowe** wprowadź `/APPCONTAINER` lub `/APPCONTAINER:NO` .

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
