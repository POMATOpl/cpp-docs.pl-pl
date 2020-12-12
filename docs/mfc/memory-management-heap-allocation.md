---
description: 'Dowiedz się więcej o: zarządzanie pamięcią: Alokacja sterty'
title: 'Zarządzanie pamięcią: alokacja stosu'
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
ms.openlocfilehash: bb9035d1346f1d3bbff53a03da9b4cf1d946a7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259659"
---
# <a name="memory-management-heap-allocation"></a>Zarządzanie pamięcią: alokacja stosu

Stos jest zarezerwowany dla potrzeb alokacji pamięci programu. Jest to obszar poza kodem programu i stosem. W przypadku typowych programów C użycie funkcji **malloc** i **Free** umożliwia przydzielanie i cofanie alokacji pamięci sterty. Wersja debugowania MFC zawiera zmodyfikowane wersje operatorów wbudowanych języka C++ **`new`** oraz **`delete`** przydzielanie i cofanie alokacji obiektów w pamięci sterty.

Gdy używasz funkcji **`new`** i **`delete`** zamiast opcji **malloc** i **Free**, możesz skorzystać z ulepszeń debugowania zarządzania pamięcią w bibliotece klas, co może być przydatne w wykrywaniu przecieków pamięci. Podczas kompilowania programu przy użyciu wersji MFC, standardowe wersje **`new`** **`delete`** operatorów i zapewniają efektywny sposób przydzielania i cofania alokacji pamięci (wersja wersji MFC nie udostępnia zmodyfikowanych wersji tych operatorów).

Należy zauważyć, że łączny rozmiar obiektów przydzielonych na stercie jest ograniczony tylko przez dostępną pamięć wirtualną systemu.

## <a name="see-also"></a>Zobacz też

[Zarządzanie pamięcią](memory-management.md)
