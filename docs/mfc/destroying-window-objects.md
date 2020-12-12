---
description: 'Dowiedz się więcej o: niszczenie obiektów okien'
title: Likwidowanie obiektów okien
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: c2837ba6b9f568d7f6ab0175ae3ad99c31ccdc7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327819"
---
# <a name="destroying-window-objects"></a>Likwidowanie obiektów okien

Należy zachować ostrożność przy użyciu własnych okien podrzędnych, aby zniszczyć obiekt okna języka C++, gdy użytkownik zakończy pracę z oknem. Jeśli te obiekty nie zostaną zniszczone, aplikacja nie odzyska swojej pamięci. Na szczęście środowisko zarządza zniszczeniem okna oraz tworzeniem okien ramowych, widoków i okien dialogowych. W przypadku tworzenia dodatkowych okien użytkownik jest odpowiedzialny za ich zniszczenie.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Sekwencja niszczenia okna](window-destruction-sequence.md)

- [Alokowanie i dealokowanie pamięci okna](allocating-and-deallocating-window-memory.md)

- [Odłączanie obiektu CWnd od jego właściwości HWND](detaching-a-cwnd-from-its-hwnd.md)

- [Ogólna Sekwencja tworzenia okna](general-window-creation-sequence.md)

- [Niszczenie okien ramowych](destroying-frame-windows.md)

## <a name="see-also"></a>Zobacz też

[Obiekty okna](window-objects.md)
