---
description: Dowiedz się więcej o typach komunikatów skojarzonych z User-Interface obiektami
title: Typy komunikatów związane z obiektami interfejsu użytkownika
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.uiobject.msgs
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
ms.openlocfilehash: 78ddb9e5290d17f92714d6b50a57ac097bbf104c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219281"
---
# <a name="message-types-associated-with-user-interface-objects"></a>Typy komunikatów związane z obiektami interfejsu użytkownika

W poniższej tabeli przedstawiono typy obiektów, z którymi pracujesz, oraz typy skojarzonych z nimi komunikatów.

### <a name="user-interface-objects-and-associated-messages"></a>Obiekty interfejsu użytkownika i skojarzone komunikaty

|Identyfikator obiektu|Komunikaty|
|---------------|--------------|
|Nazwa klasy reprezentująca okno zawierające|Komunikaty systemu Windows odpowiednie dla klasy pochodnej [CWnd](../../mfc/reference/cwnd-class.md): okno dialogowe, okno, okno potomne, okno potomne MDI lub górne okno ramek.|
|Identyfikator menu lub akceleratora|-Komunikat polecenia (wykonuje funkcję program).<br />-UPDATE_COMMAND_UI komunikat (dynamicznie aktualizuje element menu).|
|Identyfikator kontrolki|Kontrolowanie komunikatów powiadomień dla wybranego typu formantu.|

## <a name="see-also"></a>Zobacz też

[Mapowanie komunikatów do funkcji](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Dodawanie funkcji za pomocą kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Dodawanie klasy](../../ide/adding-a-class-visual-cpp.md)<br/>
[Dodawanie funkcji członkowskiej](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Dodawanie zmiennej członkowskiej](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Zastępowanie funkcji wirtualnej](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Procedura obsługi komunikatów MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Nawigacja w strukturze klas](../../ide/navigate-code-cpp.md)
