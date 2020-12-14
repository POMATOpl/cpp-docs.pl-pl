---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1070'
title: Błąd krytyczny NMAKE U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: a3d0ee448062fec8a024501b0c08d5f0466d974b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283527"
---
# <a name="nmake-fatal-error-u1070"></a>Błąd krytyczny NMAKE U1070

cykl w definicji makra "Macroname"

Dana definicja makra zawiera makro, którego definicja zawierała podane makro. Definicje makr cyklicznych są nieprawidłowe.

## <a name="example"></a>Przykład

Następujące definicje makr

```
ONE=$(TWO)
TWO=$(ONE)
```

Przyczyna następującego błędu:

```
cycle in macro definition 'TWO'
```
