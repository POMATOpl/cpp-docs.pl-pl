---
description: 'Dowiedz się więcej o: wielu plikach wbudowanych'
title: Pliki wbudowane
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: d739591910007f69eca5d4834f6943ae0a0082ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190604"
---
# <a name="multiple-inline-files"></a>Pliki wbudowane

Polecenie może utworzyć więcej niż jeden plik wbudowany.

## <a name="syntax"></a>Składnia

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Uwagi

Dla każdego pliku należy określić co najmniej jeden wiersz tekstu wbudowanego, po którym następuje wiersz zamykający zawierający ogranicznik. Rozpocznij tekst drugiego pliku w wierszu po ograniczniku wiersza dla pierwszego pliku.

## <a name="see-also"></a>Zobacz też

[Pliki wbudowane w pliku reguł programu make](inline-files-in-a-makefile.md)
