---
description: 'Dowiedz się więcej na temat: Windows Sockets: konwertowanie ciągów'
title: 'Windows Sockets: konwertowanie ciągów'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: fe8607647192fadc7f0d5d32d7716c222ff9206f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118631"
---
# <a name="windows-sockets-converting-strings"></a>Windows Sockets: konwertowanie ciągów

Ten artykuł i dwa artykuły towarzyszące wyjaśniają kilka problemów dotyczących programowania Windows Sockets. W tym artykule omówiono konwersję ciągów. Inne problemy są zawarte w usłudze [Windows Sockets: blokowanie](../mfc/windows-sockets-blocking.md) i [Windows Sockets: porządkowanie bajtów](../mfc/windows-sockets-byte-ordering.md).

Jeśli używasz lub pochodzi z klasy [CAsyncSocket](../mfc/reference/casyncsocket-class.md), musisz samodzielnie zarządzać tymi problemami. Jeśli używasz lub dziedziczysz z klasy [CSocket](../mfc/reference/csocket-class.md), MFC zarządza nimi.

## <a name="converting-strings"></a>Konwertowanie ciągów

Jeśli komunikujesz się między aplikacjami, które używają ciągów przechowywanych w różnych formatach znaków dwubajtowych, takich jak Unicode lub zestawy znaków wielobajtowych (MBCS), lub między jednym z nich a aplikacją używającą ciągów znaków ANSI, musisz zarządzać konwersjami samodzielnie `CAsyncSocket` . `CArchive`Obiekt używany z `CSocket` obiektem zarządza tą konwersją za pomocą możliwości klasy [CString](../atl-mfc-shared/reference/cstringt-class.md). Aby uzyskać więcej informacji, zobacz specyfikację Windows Sockets, która znajduje się w Windows SDK.

Aby uzyskać więcej informacji, zobacz:

- [Windows Sockets: Używanie klasy CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: używanie gniazd z archiwami](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: Tło](../mfc/windows-sockets-background.md)

- [Windows Sockets: gniazda strumienia](../mfc/windows-sockets-stream-sockets.md)

- [Windows Sockets: gniazda datagramów](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)
