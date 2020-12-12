---
description: 'Dowiedz się więcej na temat: uzyskiwanie dostępu do stanu pliku'
title: Uzyskiwanie dostępu do stanu pliku
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: defff16ddfb8cb5321def898cad451f1e12f1f8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169531"
---
# <a name="accessing-file-status"></a>Uzyskiwanie dostępu do stanu pliku

`CFile` Program obsługuje również pobieranie stanu pliku, w tym tego, czy plik istnieje, Data utworzenia i modyfikacji oraz godziny, rozmiar logiczny i ścieżkę.

### <a name="to-get-file-status"></a>Aby pobrać stan pliku

1. Użyj klasy [CFile](reference/cfile-class.md) , aby pobrać i ustawić informacje o pliku. Jedną z przydatnych aplikacji jest użycie `CFile` statycznej funkcji składowej **GetStatus** , aby określić, czy plik istnieje. **GetStatus** zwraca wartość 0, jeśli określony plik nie istnieje.

W związku z tym możesz użyć wyniku **GetStatus** , aby określić, czy podczas otwierania pliku ma być używana flaga **CFile:: modeCreate** , jak pokazano w następującym przykładzie:

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

Aby uzyskać powiązane informacje, zobacz [serializacji](serialization-in-mfc.md).

## <a name="see-also"></a>Zobacz też

[Files](files-in-mfc.md)
