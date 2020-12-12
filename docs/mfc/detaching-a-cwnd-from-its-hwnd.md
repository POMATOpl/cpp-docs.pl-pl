---
description: 'Dowiedz się więcej na temat: odłączanie CWnd od jego HWND'
title: Odłączanie obiektu CWnd od jego właściwości HWND
ms.date: 11/04/2016
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: a3bb1c50b769724ff9ea0f7cdcd2d1fa92cb3a84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327809"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Odłączanie obiektu CWnd od jego właściwości HWND

Jeśli zachodzi potrzeba obejścia `HWND` relacji między obiektem, MFC udostępnia kolejną `CWnd` funkcję członkowską, [Odłącz](reference/cwnd-class.md#detach), która rozłącza obiekt okna języka C++ z okna systemu Windows. Zapobiega to zniszczeniu okna systemu Windows, gdy obiekt zostanie zniszczony.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Tworzenie okien](creating-windows.md)

- [Sekwencja niszczenia okna](window-destruction-sequence.md)

- [Alokowanie i dealokowanie pamięci okna](allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Zobacz też

[Obiekty okna](window-objects.md)
