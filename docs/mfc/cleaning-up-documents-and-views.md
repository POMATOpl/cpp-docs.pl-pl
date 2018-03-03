---
title: "Oczyszczanie dokumentów i widoków | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a95193d5ca3df890c9c97f458b76413e588bc59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-documents-and-views"></a>Oczyszczanie dokumentów i widoków
Gdy dokument jest zamykany, struktura najpierw wywołuje jego [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) funkcję elementu członkowskiego. Jeśli przydzielone wszystkie pamięci na stercie w trakcie operacji dokumentu `DeleteContents` jest najlepszym miejscem, aby zwolnić go.  
  
> [!NOTE]
>  Nie należy deallocate dane dokumentu w destruktorze dokumentu. W przypadku aplikacji SDI obiektu dokumentu może zostać użyty ponownie.  
  
 Można zastąpić destruktora widoku, aby zwolnić wszystkie przydzielone na stercie pamięci.  
  
## <a name="see-also"></a>Zobacz też  
 [Inicjowanie i oczyszczanie dokumentów i widoków](../mfc/initializing-and-cleaning-up-documents-and-views.md)

