---
description: 'Dowiedz się więcej na temat: plik polecenia BSCMAKE (plik odpowiedzi)'
title: Plik polecenia BSCMAKE (Plik odpowiedzi)
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
ms.openlocfilehash: 4bb321cd7aa705d7e33d0f539ab3e0aa2e3cb8bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187159"
---
# <a name="bscmake-command-file-response-file"></a>Plik polecenia BSCMAKE (Plik odpowiedzi)

> [!WARNING]
> Mimo że usługa BSCMAKE jest nadal zainstalowana z programem Visual Studio, nie jest już używana przez IDE. Od programu Visual Studio 2008 informacje dotyczące przeglądania i symboli są przechowywane automatycznie w pliku SQL Server. sdf w folderze rozwiązania.

Możesz podać część lub wszystkie dane wejściowe wiersza polecenia w pliku poleceń. Określ plik poleceń przy użyciu następującej składni:

```
BSCMAKE @filename
```

Dozwolony jest tylko jeden plik poleceń. Możesz określić ścieżkę z *nazwą pliku*. Poprzedź *nazwę pliku* znakiem ( **\@** ). BSCMAKE nie zakłada rozszerzenia. Możesz określić dodatkowe *Sbrfiles* w wierszu polecenia po *nazwie pliku*. Plik polecenia to plik tekstowy, który zawiera dane wejściowe do BSCMAKE w takiej samej kolejności jak w wierszu polecenia. Oddziel argumenty wiersza polecenia z co najmniej jedną spacją, tabulatorami lub znakami nowego wiersza.

Następujące polecenie wywołuje BSCMAKE przy użyciu pliku polecenia:

```
BSCMAKE @prog1.txt
```

Poniżej znajduje się przykładowy plik poleceń:

```
/n /v /o main.bsc /El
/S (
toolbox.h
verdate.h c:\src\inc\screen.h
)
file1.sbr file2.sbr file3.sbr file4.sbr
```

## <a name="see-also"></a>Zobacz też

[Odwołanie BSCMAKE](bscmake-reference.md)
