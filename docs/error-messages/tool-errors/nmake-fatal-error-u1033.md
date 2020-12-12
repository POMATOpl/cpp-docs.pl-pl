---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1033'
title: Błąd krytyczny NMAKE U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: e616e98a21c92137fab4b167318a9305a2175bb2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272139"
---
# <a name="nmake-fatal-error-u1033"></a>Błąd krytyczny NMAKE U1033

Błąd składniowy: Nieoczekiwany element "String"

Ciąg nie jest częścią prawidłowej składni pliku reguł programu make.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Jeśli zestaw końcowy nawiasów ostrych ( **<<** ) dla pliku wbudowanego nie znajduje się na początku wiersza, wystąpi następujący błąd:

    ```
    syntax error : 'EOF' unexpected
    ```

1. Jeśli definicja makra w pliku reguł programu make zawiera znak równości ( **=** ) bez powyższej nazwy lub jeśli zdefiniowana nazwa jest makrem, które rozwijają się do niczego, wystąpi następujący błąd:

    ```
    syntax error : '=' unexpected
    ```

1. Jeśli średnik (**;**) w wierszu komentarza w TOOLS.INI nie znajduje się na początku wiersza, wystąpi następujący błąd:

    ```
    syntax error : ';' unexpected
    ```

1. Jeśli plik reguł programu make został sformatowany przez Edytor tekstów, może wystąpić następujący błąd:

    ```
    syntax error : ':' unexpected
    ```
