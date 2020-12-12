---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1001'
title: Błąd krytyczny NMAKE U1001
ms.date: 11/04/2016
f1_keywords:
- U1001
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
ms.openlocfilehash: 8c1f5ca791ec736942414b698ee0aa95299eddad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173132"
---
# <a name="nmake-fatal-error-u1001"></a>Błąd krytyczny NMAKE U1001

Błąd składniowy: niedozwolony znak "Character" w makrze

Dany znak pojawia się w makrze, ale nie jest literą, cyfrą lub podkreśleniem.

Ten błąd może być spowodowany brakiem dwukropka w rozwinięciu makra:

```
syntax error : illegal character '=' in macro
```
