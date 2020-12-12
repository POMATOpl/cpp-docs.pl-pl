---
description: 'Dowiedz się więcej o: LNK4092 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4092 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 6ef835981a8ed7921147697d6ed9fc79ceeb7033
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210013"
---
# <a name="linker-tools-warning-lnk4092"></a>Ostrzeżenie LNK4092 narzędzi konsolidatora

udostępniona zapisywalna sekcja "sekcja" zawiera relokacje; obraz może nie działać poprawnie

Konsolidator emituje to ostrzeżenie za każdym razem, gdy istnieje sekcja udostępniona, aby ostrzec o potencjalnie poważnym problemie.

Jednym ze sposobów udostępniania danych między wieloma procesami jest oznaczenie sekcji jako "Shared". Jednak oznaczenie sekcji jako udostępnionej może spowodować problemy. Na przykład masz bibliotekę DLL, która zawiera deklaracje podobne do sekcji danych udostępnionych:

```
int var = 1;
int *pvar = &var;
```

Nie można rozpoznać konsolidatora `pvar` , ponieważ jego wartość zależy od lokalizacji, w której Biblioteka DLL jest załadowana w pamięci, więc umieszcza rekord relokacji w bibliotece DLL. Gdy biblioteka DLL jest załadowana do pamięci, adres `var` może zostać rozwiązany i `pvar` przypisany. Jeśli inny proces ładuje tę samą bibliotekę DLL, ale nie może załadować jej pod tym samym adresem, relokacja dla adresu `var` zostanie zaktualizowana dla drugiego procesu, a przestrzeń adresowa pierwszego procesu wskaże nieprawidłowy adres.
