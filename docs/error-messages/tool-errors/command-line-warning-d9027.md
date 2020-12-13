---
description: 'Dowiedz się więcej na temat: Command-Line Warning D9027'
title: Ostrzeżenie D9027 dla wiersza polecenia
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 8c17750f3310072f8f69c77587a1c17fc9377e79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136113"
---
# <a name="command-line-warning-d9027"></a>Ostrzeżenie D9027 dla wiersza polecenia

plik źródłowy " \<filename> " został zignorowany

CL.exe zignorował wejściowy plik źródłowy.

To ostrzeżenie może być spowodowane spacją między opcją/fo a wyjściową nazwą pliku w wierszu polecenia z/c opcją. Na przykład:

```
cl /c /Fo output.obj input.c
```

Ponieważ istnieje spacja między/FO i `output.obj` , CL.exe przyjmuje `output.obj` jako nazwę pliku wejściowego. Aby rozwiązać ten problem, Usuń miejsce:

```
cl /c /Fooutput.obj input.c
```
