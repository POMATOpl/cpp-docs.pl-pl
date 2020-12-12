---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1311'
title: Błąd krytyczny C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: d6049bfedd01be02e8b3f26163fe062e9023bd78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177747"
---
# <a name="fatal-error-c1311"></a>Błąd krytyczny C1311

Format COFF statycznie nie może zainicjować "var" z liczbą bajtów adresu

Adres, którego wartość nie jest znana w czasie kompilacji, nie może być statycznie przypisany do zmiennej, której typ ma magazyn mniejszy niż 4 bajty.

Ten błąd może wystąpić w kodzie, który jest w inny sposób prawidłowym językiem C++.

Poniższy przykład pokazuje jeden warunek, który może powodować C1311.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
