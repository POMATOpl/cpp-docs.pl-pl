---
description: 'Dowiedz się więcej o programie: kolejność opcji CL'
title: Kolejność opcji CL (C++) — Visual Studio
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: bc0290164ff40cf45d8d0a1e9f07e683e408c251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226418"
---
# <a name="order-of-cl-options"></a>Kolejność opcji CL

Opcje mogą znajdować się w dowolnym miejscu w wierszu polecenia CL, z wyjątkiem opcji/link, która musi wystąpić jako Ostatnia. Kompilator rozpoczyna się od opcji określonych w [zmiennej środowiskowej CL](cl-environment-variables.md) , a następnie odczytuje wiersz polecenia od lewej do prawej — pliki poleceń przetwarzania w kolejności, w jakiej napotkają. Każda opcja ma zastosowanie do wszystkich plików w wierszu polecenia. Jeśli CL napotykają opcje powodujące konflikt, użyje prawej opcji.

## <a name="see-also"></a>Zobacz też

[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
