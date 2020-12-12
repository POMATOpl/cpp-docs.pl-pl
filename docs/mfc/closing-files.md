---
description: 'Dowiedz się więcej o programie: zamykanie plików'
title: Zamykanie plików
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: e8d2f0792aeb889c40cb516af259fc2a40890a1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338389"
---
# <a name="closing-files"></a>Zamykanie plików

Jak zwykle w operacjach we/wy, po zakończeniu pracy z plikiem należy go zamknąć.

#### <a name="to-close-a-file"></a>Aby zamknąć plik

1. Użyj **zamykającej** funkcji członkowskiej. Ta funkcja zamyka plik systemu plików i opróżnia bufory w razie potrzeby.

Jeśli przydzielono obiekt [CFile](reference/cfile-class.md) w ramce (jak w przykładzie pokazanym w [otwieraniu plików](opening-files.md)), obiekt zostanie automatycznie zamknięty, a następnie zniszczony, gdy wykracza poza zakres. Należy pamiętać, że usunięcie `CFile` obiektu nie powoduje usunięcia pliku fizycznego w systemie plików.

## <a name="see-also"></a>Zobacz też

[Files](files-in-mfc.md)
