---
title: Szczegóły obsługi ATL dodanej przez kreatora ATL
ms.date: 08/20/2019
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: aeac01ce58deb429f14058c06524dff53abde060
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924443"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Szczegóły obsługi ATL dodanej przez kreatora ATL

::: moniker range=">=msvc-160"

Po [dodaniu obsługi ATL do istniejącego pliku wykonywalnego MFC lub dll](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), program Visual Studio domyślnie dodaje plik nagłówka o nazwie *Framework. h* , który `#include` zawiera `#define` dyrektywy preprocesora, aby umożliwić korzystanie z ATL w projekcie. Nie dodano żadnych dodatkowych plików ani klas, jak zostało to zrobione w poprzednich wersjach programu Visual Studio.

::: moniker-end

::: moniker range="<=msvc-150"

Po [dodaniu obsługi ATL do istniejącego pliku wykonywalnego MFC lub dll](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual Studio wprowadza następujące zmiany do istniejącego projektu MFC (w tym przykładzie projekt jest wywoływany `MFCEXE` ):

- Dodawane są dwa nowe pliki (plik. idl i plik. RGS służące do zarejestrowania serwera).

- W głównym pliku nagłówkowym i implementacji aplikacji (Mfcexe. h i Mfcexe. cpp) zostanie dodana nowa klasa (pochodna od `CAtlMFCModule` ). Oprócz nowej klasy kod jest dodawany do `InitInstance` rejestracji. Kod jest również dodawany do `ExitInstance` funkcji do odwoływania obiektu klasy. W pliku nagłówkowym, na koniec, dwa nowe pliki nagłówkowe (Initguid. h i Mfcexe_i. c) są zawarte w pliku implementacji, deklarując i inicjując nowe identyfikatory GUID dla `CAtlMFCModule` klasy pochodnej.

- Aby zarejestrować serwer prawidłowo, wpis dla nowego pliku. RGS jest dodawany do pliku zasobów projektu.

::: moniker-end

## <a name="notes-for-dll-projects"></a>Uwagi dotyczące projektów bibliotek DLL

Po dodaniu obsługi ATL do projektu MFC DLL, pojawią się pewne różnice. Kod jest dodawany do `DLLRegisterServer` funkcji i `DLLUnregisterServer` w celu zarejestrowania i WYREJESTROWANIA biblioteki DLL. Kod jest również dodawany do [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) i [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).

## <a name="see-also"></a>Zobacz także

[Obsługa ATL w projekcie MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Dodawanie funkcji za pomocą kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Dodawanie klasy](../../ide/adding-a-class-visual-cpp.md)<br/>
[Dodawanie funkcji członkowskiej](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Dodawanie zmiennej członkowskiej](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Zastępowanie funkcji wirtualnej](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Procedura obsługi komunikatów MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Nawigacja w strukturze klas](../../ide/navigate-code-cpp.md)
