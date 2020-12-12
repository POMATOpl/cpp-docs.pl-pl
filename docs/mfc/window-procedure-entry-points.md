---
description: 'Dowiedz się więcej o: punkty wejścia procedury okna'
title: Punkty wejścia procedury okna
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 2c2e5dc5d37a2e6f187e694d39205c4cd95b3810
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214484"
---
# <a name="window-procedure-entry-points"></a>Punkty wejścia procedury okna

Aby chronić procedury okna MFC, moduł łączy statycznych z implementacją specjalnej procedury okna. Połączenie odbywa się automatycznie, gdy moduł jest połączony z MFC. Ta procedura okna używa makra AFX_MANAGE_STATE, aby prawidłowo ustawić obowiązujący stan modułu, a następnie wywołuje `AfxWndProc` , co z kolei deleguje do `WindowProc` funkcji składowej odpowiedniego `CWnd` obiektu pochodnego.

## <a name="see-also"></a>Zobacz też

[Zarządzanie danymi stanu modułów MFC](../mfc/managing-the-state-data-of-mfc-modules.md)
