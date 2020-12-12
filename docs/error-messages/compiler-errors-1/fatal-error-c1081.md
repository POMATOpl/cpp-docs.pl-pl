---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1081'
title: Błąd krytyczny C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: 97e1070cb24a70750e9c7d9f78a3860b26a7831a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330691"
---
# <a name="fatal-error-c1081"></a>Błąd krytyczny C1081

"symbol": nazwa pliku jest za długa

Długość nazwy ścieżki pliku przekracza `_MAX_PATH` (zdefiniowany przez STDLIB. h jako 260 znaków). Skróć nazwę pliku.

Jeśli wywołasz CL.exe z krótką nazwą pliku, kompilator może potrzebować pełnej nazwy ścieżki. Na przykład `cl -c myfile.cpp` może spowodować wygenerowanie kompilatora:

```
D:\<very-long-directory-path>\myfile.cpp
```
