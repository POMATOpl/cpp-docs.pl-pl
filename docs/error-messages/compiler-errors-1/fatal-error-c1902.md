---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1902'
title: Błąd krytyczny C1902
ms.date: 11/04/2016
f1_keywords:
- C1902
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
ms.openlocfilehash: e41f1d6fa9e15f9ed748b6e916ef8d8dd314b3f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276091"
---
# <a name="fatal-error-c1902"></a>Błąd krytyczny C1902

niezgodność Menedżera bazy danych programu; Sprawdź instalację

Plik bazy danych programu (. pdb) został utworzony przy użyciu nowszej wersji mspdb *XXX*. dll niż kompilator znaleziony w systemie. Ten błąd zazwyczaj wskazuje, że brakuje mspdbsrv.exe lub mspdbcore.dll lub mają różne wersje niż mspdb *XXX*. dll. (Symbol zastępczy *XXX* w nazwie pliku mspdb *XXX*. dll zmienia się wraz z każdą wersją produktu. Na przykład w programie Visual Studio 2015 nazwa pliku jest mspdb140.dll.)

Upewnij się, że w systemie są zainstalowane zgodne wersje mspdbsrv.exe, mspdbcore.dll i mspdb *XXX*. dll. Upewnij się, że niezgodne wersje nie zostały skopiowane do katalogu, który zawiera narzędzia kompilatora i łączy dla platformy docelowej. Na przykład pliki mogły zostać skopiowane, aby można było wywołać kompilator lub narzędzie do łączenia z wiersza polecenia bez odpowiednio ustawić zmiennej środowiskowej **Path** .
