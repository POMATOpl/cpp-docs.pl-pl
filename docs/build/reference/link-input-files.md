---
description: 'Dowiedz się więcej na temat: łączenie plików wejściowych'
title: Pliki wyjściowe LINK
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: 3bf25d36ab61b35dfe3d1551e9f85e8c2f26862b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199509"
---
# <a name="link-input-files"></a>Pliki wyjściowe LINK

Udostępniasz konsolidator zawierający pliki, które zawierają obiekty, importowane i standardowe biblioteki, zasoby, definicje modułów i dane wejściowe polecenia. LINK nie używa rozszerzeń plików do wprowadzania założeń dotyczących zawartości pliku. Zamiast tego, LINK sprawdza każdy plik wejściowy, aby określić rodzaj pliku.

Pliki obiektów w wierszu polecenia są przetwarzane w kolejności, w jakiej występują w wierszu polecenia. Biblioteki są przeszukiwane w kolejności wiersza polecenia, z następującymi zastrzeżeniami: symbole, które nie są rozpoznawane podczas umieszczania w pliku obiektu z biblioteki są najpierw wyszukiwane w tej bibliotece, a następnie następujące biblioteki z wiersza polecenia i [/DEFAULTLIB (Określ bibliotekę domyślną)](defaultlib-specify-default-library.md) , a następnie do wszystkich bibliotek na początku wiersza polecenia.

> [!NOTE]
> LINK nie akceptuje już średnika (ani żadnego innego znaku) jako początku komentarza w plikach odpowiedzi i plikach kolejności. Średniki są rozpoznawane tylko jako początku komentarzy w plikach definicji modułów (. def).

LINK używa następujących typów plików wejściowych:

- [pliki. obj](dot-obj-files-as-linker-input.md)

- [pliki. module](netmodule-files-as-linker-input.md)

- [pliki. lib](dot-lib-files-as-linker-input.md)

- [pliki. EXP](dot-exp-files-as-linker-input.md)

- [. def — pliki](dot-def-files-as-linker-input.md)

- [pliki. pdb](dot-pdb-files-as-linker-input.md)

- [pliki. res](dot-res-files-as-linker-input.md)

- [pliki. exe](dot-exe-files-as-linker-input.md)

- [. txt — pliki](dot-txt-files-as-linker-input.md)

- [pliki. ilk](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
