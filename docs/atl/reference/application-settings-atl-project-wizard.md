---
description: 'Dowiedz się więcej na temat: ustawienia aplikacji, Kreator projektu ATL'
title: Ustawienia aplikacji, kreator projektów ATL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.atl.com.appset
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
ms.openlocfilehash: 7805fcb8760035ac232a36a42a1cf34273ee42a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158948"
---
# <a name="application-settings-atl-project-wizard"></a>Ustawienia aplikacji, kreator projektów ATL

Na stronie **Ustawienia aplikacji** Kreatora projektu ATL można zaprojektować i dodać podstawowe funkcje do nowego projektu ATL.

## <a name="server-type"></a>Typ serwera

Wybierz jeden z trzech typów serwerów:

- **Biblioteka dołączana dynamicznie (DLL)**

   Wybierz, aby utworzyć serwer w procesie.

- **Plik wykonywalny (EXE)**

   Wybierz opcję utworzenia lokalnego serwera poza procesem. Ta opcja nie zezwala na obsługę MFC ani COM+ 1,0. Nie pozwala na scalanie kodu proxy/stub.

- **Usługa (EXE)**

   Wybierz, aby utworzyć aplikację systemu Windows, która jest uruchamiana w tle podczas uruchamiania systemu Windows. Ta opcja nie umożliwia obsługi MFC ani COM+ 1,0 ani nie pozwala na scalanie kodu proxy/stub.

## <a name="additional-options"></a>Opcje dodatkowe

> [!NOTE]
> Wszystkie dodatkowe opcje są dostępne tylko dla projektów bibliotek DLL.

- **Zezwalaj na scalanie kodu proxy/szczątkowego**

   Zaznacz pole wyboru **Zezwalaj na scalanie kodu proxy/stub** jako wygodę, gdy jest wymagane kierowanie interfejsów. Ta opcja powoduje umieszczenie serwera proxy i kodu zastępczego MIDL w tym samym pliku wykonywalnym, co serwer programu.

- **Obsługa MFC**

   Wybierz, aby określić, czy obiekt obejmuje obsługę MFC. Ta opcja łączy projekt z bibliotekami MFC, aby można było uzyskać dostęp do dowolnych klas i funkcji, które zawierają.

- **Obsługa modelu COM+ 1,0**

   Wybierz, aby zmodyfikować ustawienia kompilacji projektu w celu obsługi składników modelu COM+ 1,0. Oprócz standardowej listy bibliotek Kreator dodaje biblioteki Comsvcs. lib specyficzne dla składnika modelu COM+ 1,0

   Ponadto mtxex.dll jest opóźnione ładowanie w systemie hosta podczas uruchamiania aplikacji.

- **Obsługa rejestratora składników**

   Jeśli projekt ATL zawiera obsługę składników modelu COM+ 1,0, można ustawić tę opcję. Rejestrator składnika umożliwia obiektowi modelu COM+ 1,0 uzyskanie listy składników, rejestrowanie składników lub Wyrejestrowywanie składników (pojedynczo lub wszystkie jednocześnie).

## <a name="see-also"></a>Zobacz też

[Kreator projektu ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)<br/>
[Domyślne konfiguracje projektu ATL](../../atl/reference/default-atl-project-configurations.md)
