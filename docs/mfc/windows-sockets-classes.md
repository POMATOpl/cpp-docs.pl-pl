---
description: 'Dowiedz się więcej na temat: klasy Windows Sockets'
title: Klasy Windows Sockets
ms.date: 11/04/2016
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 03d8ddae0bb511e52b0ea7ed2b3754184ed6ebc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118644"
---
# <a name="windows-sockets-classes"></a>Klasy Windows Sockets

Windows Sockets zapewniają niezależny od protokołu sieciowego sposób komunikacji między dwoma komputerami. Te gniazda można synchronicznie (program czeka na zakończenie komunikacji) lub asynchronicznie (program kontynuuje działanie w trakcie komunikacji).

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)<br/>
Hermetyzuje interfejs API Windows Sockets w elastycznej otoki.

[CSocket](../mfc/reference/csocket-class.md)<br/>
Streszczenie wyższego poziomu pochodne `CAsyncSocket` . Działa synchronicznie.

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Udostępnia `CFile` interfejs do gniazda systemu Windows.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../mfc/class-library-overview.md)
