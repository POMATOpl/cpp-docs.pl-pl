---
description: 'Dowiedz się więcej na temat: Windows Sockets: Datagram Sockets'
title: 'Windows Sockets: gniazda do przesyłania datagramów'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 8de374d6e96348504d4b1fc126c1607c029cd6c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132980"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Sockets: gniazda do przesyłania datagramów

W tym artykule opisano gniazda datagramy, jeden z dwóch dostępnych typów gniazd systemu Windows. (Drugi typ to [gniazdo strumienia](../mfc/windows-sockets-stream-sockets.md)).

Gniazda datagramy obsługują dwukierunkowy przepływ danych, który nie jest gwarantowany lub nie jest nieduplikowany. Datagramy nie są również gwarantowane jako niezawodne; może się nie powieść. Dane datagramu mogą się pojawić z kolejnością i prawdopodobnie zduplikowane, ale granice rekordu w danych są zachowywane, o ile rekordy są mniejsze niż wewnętrzny limit rozmiaru odbiorcy. Użytkownik jest odpowiedzialny za zarządzanie sekwencjonowaniem i niezawodnością. (Niezawodność jest dobrym sposobem w przypadku sieci lokalnych [LAN], ale mniej tak, jak w przypadku sieci rozległych [WAN], takich jak Internet).

Datagramy są bezpołączeniowe, czyli nie jest ustanawiane żadne jawne połączenie; wysyłasz komunikat datagram do określonego gniazda i można odbierać komunikaty z określonego gniazda.

Przykładem gniazda datagramu jest aplikacja, która pozwala synchronizować zegary systemowe w sieci. Ilustruje to dodatkową możliwość gniazd datasockets w co najmniej niektórych ustawieniach: emitowanie komunikatów do dużej liczby adresów sieciowych.

Gniazda datagramy są lepsze niż gniazda strumienia dla danych zorientowanych na rekordy. Aby uzyskać więcej informacji na temat gniazd datasockets, zobacz specyfikację Windows Sockets dostępną w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows Sockets: Tło](../mfc/windows-sockets-background.md)
