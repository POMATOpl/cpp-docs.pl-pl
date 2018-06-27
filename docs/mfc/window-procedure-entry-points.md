---
title: Punkty wejścia procedury okna | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 315526a8f95a1d62ac89f3a76fab492c9b136715
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956385"
---
# <a name="window-procedure-entry-points"></a>Punkty wejścia procedury okna
Aby chronić procedury okna MFC, statycznych łączy modułu, z implementacją procedury specjalne okno. Powiązanie odbywa się automatycznie, gdy moduł jest połączony z MFC. Tę procedurę okna używa makro AFX_MANAGE_STATE Aby poprawnie ustawić stan modułu skuteczne, a następnie wywołuje `AfxWndProc`, który z kolei deleguje do `WindowProc` funkcji członkowskiej klasy odpowiednie `CWnd`-pochodzi z obiektu.  
  
## <a name="see-also"></a>Zobacz też  
 [Zarządzanie danymi stanu modułów MFC](../mfc/managing-the-state-data-of-mfc-modules.md)

