---
description: 'Dowiedz się więcej na temat: MAPI'
title: MAPI
ms.date: 11/04/2016
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
ms.openlocfilehash: 634d5d0b2dbbc8a262f624be2b7e294ef6069b96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280810"
---
# <a name="mapi"></a>MAPI

W tym artykule opisano interfejs programowania aplikacji (MAPI) usługi Microsoft Messaging dla deweloperów aplikacji komunikatów klientów. MFC dostarcza obsługę podzestawu interfejsu MAPI w klasie `CDocument` , ale nie hermetyzuje całego interfejsu API. Aby uzyskać więcej informacji, zobacz [Obsługa MAPI w MFC](mapi-support-in-mfc.md).

MAPI to zestaw funkcji używanych przez aplikacje obsługujące pocztę i wiadomości e-mail do tworzenia, manipulowania, przesyłania i przechowywania wiadomości e-mail. Zapewnia deweloperom aplikacji narzędzia do definiowania przeznaczenia i zawartości wiadomości e-mail oraz zapewnia im elastyczność zarządzania przechowywanymi wiadomościami e-mail. Interfejs MAPI udostępnia również wspólny interfejs, za pomocą którego deweloperzy aplikacji mogą tworzyć aplikacje obsługujące pocztę i obsługę poczty niezależnie od systemu obsługi komunikatów.

Klienci obsługi komunikatów zapewniają interfejs ludzki do interakcji z systemem Microsoft Windows Messaging system (WMS). Ta interakcja zazwyczaj obejmuje żądania usług od dostawców zgodnych z interfejsem MAPI, takich jak magazyny komunikatów i książki adresowe.

Aby uzyskać więcej informacji o interfejsie MAPI, zapoznaj się z artykułami w sekcji Przewodnik po stronie Win32 Messaging (MAPI) Windows SDK.

## <a name="in-this-section"></a>W tej sekcji

[Obsługa MAPI w MFC](mapi-support-in-mfc.md)

## <a name="see-also"></a>Zobacz też

[CDocument:: OnFileSendMail](reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument:: OnUpdateFileSendMail](reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument::OnFileSendMail](reference/coledocument-class.md#onfilesendmail)
