---
description: 'Dowiedz się więcej na temat: Command-Line Warning D9026'
title: Ostrzeżenie D9026 dla wiersza polecenia
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 910471215d350f266319f5e14b7bb1a62f641028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115485"
---
# <a name="command-line-warning-d9026"></a>Ostrzeżenie D9026 dla wiersza polecenia

Opcje stosują się do całego wiersza polecenia

Opcja została określona w poleceniu po określeniu nazwy pliku. Opcja została zastosowana do pliku, który poprzedzał go.

Na przykład w poleceniu

```
CL verdi.c /G5 puccini.c
```

plik VERDI. c zostanie skompilowany przy użyciu opcji/G5, a nie domyślnego/G4.

To zachowanie jest inne niż w przypadku niektórych poprzednich wersji, które dotyczyły tylko opcji określonych przed nazwą pliku, co spowodowało VERDI. c jest kompilowane przy użyciu/G4 i PUCCINI. c, które są kompilowane przy użyciu/G5.
