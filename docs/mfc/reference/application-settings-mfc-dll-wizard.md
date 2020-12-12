---
description: 'Dowiedz się więcej na temat: ustawienia aplikacji, Kreator biblioteki MFC DLL'
title: Ustawienia aplikacji, kreator biblioteki MFC DLL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.appset
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
ms.openlocfilehash: da9579ef9a834fa0c2362b1569c2efa808132faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322801"
---
# <a name="application-settings-mfc-dll-wizard"></a>Ustawienia aplikacji, kreator biblioteki MFC DLL

Użyj tej strony kreatora MFC DLL, aby zaprojektować i dodać podstawowe funkcje do nowego projektu MFC DLL.

## <a name="dll-type"></a>Typ biblioteki DLL

Wybierz typ pliku DLL, który chcesz utworzyć.

- **Zwykła Biblioteka MFC DLL przy użyciu udostępnionej biblioteki MFC DLL**

   Wybierz tę opcję, aby połączyć bibliotekę MFC z programem jako udostępnioną biblioteką DLL. Korzystając z tej opcji, nie można udostępniać obiektów MFC między biblioteką DLL i aplikacją wywołującą. Program wykonuje wywołania biblioteki MFC w czasie wykonywania. Ta opcja zmniejsza wymagania dotyczące dysku i pamięci programu, jeśli składa się z wielu plików wykonawczych, które używają biblioteki MFC. Programy Win32 i MFC umożliwiają wywoływanie funkcji w bibliotece DLL. Należy ponownie rozpowszechnić bibliotekę MFC DLL z tym typem projektu.

- **Zwykła Biblioteka MFC DLL ze statycznie połączonymi MFC**

   Wybierz tę opcję, aby połączyć program statycznie z biblioteką MFC w czasie kompilacji. Programy Win32 i MFC umożliwiają wywoływanie funkcji w bibliotece DLL. Chociaż ta opcja zwiększa rozmiar programu, nie trzeba ponownie rozpowszechniać biblioteki MFC DLL przy użyciu tego typu projektu. Nie można współużytkować obiektów MFC między biblioteką DLL i aplikacją wywołującą.

- **Biblioteka DLL rozszerzenia MFC**

   Wybierz tę opcję, jeśli chcesz, aby program przeczynił wywołania do biblioteki MFC w czasie wykonywania, i jeśli chcesz udostępnić obiekty MFC między biblioteką DLL a aplikacją wywołującą. Ta opcja zmniejsza wymagania dotyczące dysku i pamięci programu, jeśli składa się z wielu plików wykonywalnych, które używają biblioteki MFC. Tylko programy MFC mogą wywoływanie funkcji w bibliotece DLL. Należy ponownie rozpowszechnić bibliotekę MFC DLL z tym typem projektu.

## <a name="additional-features"></a>Dodatkowe funkcje

Określ, czy biblioteka MFC DLL powinna obsługiwać automatyzację i czy powinna obsługiwać Windows Sockets.

- **Automatyzacja**

   Wybierz **automatyzację** , aby umożliwić programowi manipulowanie obiektami zaimplementowanymi w innym programie. Wybranie **automatyzacji** udostępnia również program innym klientom automatyzacji. Aby uzyskać więcej informacji, zobacz [Automatyzacja](../../mfc/automation.md) .

- **Windows Sockets**

   Wybierz tę opcję, aby wskazać, że program obsługuje Windows Sockets. Windows Sockets umożliwia pisanie programów komunikujących się za pośrednictwem sieci TCP/IP.

   Po utworzeniu biblioteki MFC DLL z obsługą systemu Windows Sockets [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Inicjuje obsługę gniazd i plik nagłówkowy MFC stdafx. h obejmuje AfxSock. h.

## <a name="see-also"></a>Zobacz też

[Kreator biblioteki MFC DLL](../../mfc/reference/mfc-dll-wizard.md)<br/>
[Tworzenie projektu MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)
