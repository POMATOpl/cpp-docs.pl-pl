---
description: 'Dowiedz się więcej o: BSCMAKE wiersz polecenia'
title: Wiersz polecenia BSCMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: a0d6cb81fb207c30cd89fbfe3a988380a865a399
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182661"
---
# <a name="bscmake-command-line"></a>Wiersz polecenia BSCMAKE

> [!WARNING]
> Mimo że usługa BSCMAKE jest nadal zainstalowana z programem Visual Studio, nie jest już używana przez IDE. Od programu Visual Studio 2008 informacje dotyczące przeglądania i symboli są przechowywane automatycznie w pliku SQL Server. sdf w folderze rozwiązania.

Aby uruchomić BSCMAKE, użyj następującej składni wiersza polecenia:

```
BSCMAKE [options] sbrfiles
```

Opcje mogą występować tylko w `options` polu w wierszu polecenia.

Pole *Sbrfiles* określa jeden lub więcej plików. sbr utworzonych przez kompilator lub asembler. Rozdziel nazwy plików. sbr za pomocą spacji lub kart. Należy określić rozszerzenie; nie jest to ustawienie domyślne. Można określić ścieżkę z nazwą pliku i można użyć symboli wieloznacznych systemu operacyjnego ( \* i?).

Podczas kompilacji przyrostowej można określić nowe pliki SBR, które nie były częścią oryginalnej kompilacji. Jeśli chcesz, aby wszystkie wkłady pozostały w pliku informacji o przeglądaniu, musisz określić wszystkie pliki. SBR (w tym pliki obcinane), które pierwotnie były używane do tworzenia pliku. BSC. Jeśli pominięto plik. sbr, udział tego pliku w pliku informacji o przeglądaniu zostanie usunięty.

Nie określaj obciętego pliku SBR dla pełnej kompilacji. Pełna kompilacja wymaga udziału ze wszystkich określonych plików. sbr. Przed wykonaniem pełnej kompilacji należy ponownie skompilować projekt i utworzyć nowy plik. sbr dla każdego pustego pliku.

Następujące polecenie uruchamia BSCMAKE w celu skompilowania pliku o nazwie MAIN. bsc z trzech plików. sbr:

```
BSCMAKE main.sbr file1.sbr file2.sbr
```

Aby uzyskać powiązane informacje, zobacz [BSCMAKE Command File](bscmake-command-file-response-file.md) and [BSCMAKE Options](bscmake-options.md).

## <a name="see-also"></a>Zobacz też

[Odwołanie BSCMAKE](bscmake-reference.md)
