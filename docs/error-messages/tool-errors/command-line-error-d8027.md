---
description: 'Dowiedz się więcej na temat: Command-Line błędu D8027 wiersza polecenia'
title: Błąd D8027 wiersza polecenia
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: 80d0812571043249616108e99e763b105b527475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115654"
---
# <a name="command-line-error-d8027"></a>Błąd D8027 wiersza polecenia

nie można wykonać elementu "Component"

Kompilator nie może uruchomić danego składnika kompilatora lub konsolidatora.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Za mało pamięci, aby załadować składnik. Jeśli NMAKE wywołał kompilator, uruchom kompilator spoza pliku reguł programu make.

1. Bieżący system operacyjny nie może uruchomić składnika. Upewnij się, że ścieżka wskazuje pliki wykonywalne odpowiednie dla danego systemu operacyjnego.

1. Składnik został uszkodzony. Skopiuj składnik z dysków dystrybucji przy użyciu programu instalacyjnego.

1. Opcja została określona nieprawidłowo. Na przykład:

    ```
    cl /B1 file1.c
    ```
