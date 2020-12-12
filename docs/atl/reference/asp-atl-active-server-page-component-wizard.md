---
description: 'Dowiedz się więcej na temat: ASP, Kreator składnika strony Active Server ATL'
title: Środowisko ASP, Kreator składnika strony Active Server ATL
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: e9cc11cf60c3a87d6891c98a72eb240729d1a739
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165540"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>Środowisko ASP, Kreator składnika strony Active Server ATL

Ta strona kreatora wieloskładnikowej strony Active Server ATL służy do określania ustawień opcjonalnych do obsługi informacji i stanu związanych ze składnikiem ASP.

- **Metody opcjonalne**

   Dodaje opcjonalne metody ASP, **OnStartPage** i **OnEndPage** do obiektu. Należy wybrać tę opcję, aby ustawić wszystkie obiekty wewnętrzne stron Active Server. Domyślnie jest to zaznaczone.

- **OnStartPage/OnEndPage**

   Metoda [OnStartPage](/previous-versions//ms691624\(v=vs.85\)) jest wywoływana za pierwszym razem, gdy skrypt próbuje uzyskać dostęp do obiektu. Metoda **OnEndPage** jest wywoływana, gdy obiekt kończy przetwarzanie skryptu.

- **Obiekt wewnętrzny**

   Musisz wybrać opcję **OnStartPage/OnEndPage** , aby ustawić dowolne obiekty wewnętrzne ASP.

|Opcja|Opis|
|------------|-----------------|
|**Żądanie**|Zapewnia dostęp do obiektu **żądania** wewnętrznego stron Active Server. Obiekt request służy do przekazywania żądania HTTP.|
|**Odpowiedź**|Zapewnia dostęp do obiektu wewnętrznej **odpowiedzi** stron Active Server. W odpowiedzi na żądanie obiekt Response wysyła informacje do przeglądarki, aby wyświetlić użytkownika.|
|**Sesja**|Zapewnia dostęp do obiektu wewnętrznej **sesji** stron Active Server. Obiekt **Session** zachowuje informacje o bieżącej sesji użytkownika, w tym o przechowywaniu i pobieraniu informacji o stanie.|
|**Aplikacja**|Zapewnia dostęp do obiektu **aplikacji** wewnętrznej Active Server Pages. Obiekt **aplikacji** zarządza stanem, który jest współużytkowany przez wiele obiektów ASP.|
|**Server** (Serwer)|Zapewnia dostęp do obiektu **serwera** wewnętrznego stron Active Server. Obiekt **serwer** umożliwia tworzenie innych obiektów ASP.|

## <a name="see-also"></a>Zobacz też

[Kreator składników stron Active Server Page ATL](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[Składnik strony Active Server ATL](../../atl/reference/adding-an-atl-active-server-page-component.md)
