---
description: 'Dowiedz się więcej na temat: obsługi poleceń w dokumencie'
title: Obsługa poleceń w dokumencie
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
ms.openlocfilehash: 4d8252cb16eee0e1c5c802e5839ec925a7879cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248895"
---
# <a name="handling-commands-in-the-document"></a>Obsługa poleceń w dokumencie

Klasa dokumentu może również obsługiwać niektóre polecenia generowane przez elementy menu, przyciski paska narzędzi lub klawisze skrótów. Domyślnie program `CDocument` obsługuje polecenia Zapisz i Zapisz jako w menu plik przy użyciu serializacji. Inne polecenia, które mają wpływ na dane mogą również być obsługiwane przez funkcje składowe dokumentu. Na przykład w programie bazgrołów Klasa `CScribDoc` zawiera procedurę obsługi dla polecenia Edytuj Wyczyść wszystko, które usuwa wszystkie dane przechowywane w dokumencie. Dokumenty mogą zawierać mapy komunikatów, ale w przeciwieństwie do widoków dokumenty nie mogą obsługiwać standardowych komunikatów systemu Windows — tylko **WM_COMMAND** komunikatów lub "polecenia".

## <a name="see-also"></a>Zobacz też

[Używanie dokumentów](using-documents.md)
