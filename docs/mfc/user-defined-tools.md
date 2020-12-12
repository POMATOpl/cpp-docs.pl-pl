---
description: 'Dowiedz się więcej o programie: Narzędzia zdefiniowane przez użytkownika'
title: Narzędzia zdefiniowane przez użytkownika
ms.date: 11/19/2018
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 4cccd0a68751a2f196c8c2e652088e8939e3f162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263637"
---
# <a name="user-defined-tools"></a>Narzędzia zdefiniowane przez użytkownika

MFC obsługuje narzędzia zdefiniowane przez użytkownika. Narzędzie zdefiniowane przez użytkownika to specjalne polecenie, które wykonuje zewnętrzny, określony przez użytkownika program. Aby zarządzać narzędziami zdefiniowanymi przez użytkownika, można użyć procesu dostosowywania. Nie można jednak użyć tego procesu, jeśli obiekt aplikacji nie pochodzi od [klasy CWinAppEx](../mfc/reference/cwinappex-class.md). Aby uzyskać więcej informacji na temat dostosowywania, zobacz [Dostosowywanie dla MFC](../mfc/customization-for-mfc.md).

Jeśli włączono obsługę narzędzi zdefiniowanych przez użytkownika, w oknie dialogowym dostosowanie zostanie automatycznie wykorzystana karta **Narzędzia** . Na poniższej ilustracji przedstawiono stronę **Narzędzia** .

![Karta narzędzia w oknie dialogowym Dostosowywanie](../mfc/media/custdialogboxtoolstab.png "Karta narzędzia w oknie dialogowym Dostosowywanie") <br/>
Karta narzędzi okna dialogowego dostosowywania

## <a name="enabling-user-defined-tools-support"></a>Włączanie obsługi narzędzi zdefiniowanych przez użytkownika

Aby włączyć narzędzia zdefiniowane przez użytkownika w aplikacji, wywołaj [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools). Należy jednak najpierw zdefiniować kilka stałych w plikach zasobów aplikacji, aby użyć ich jako parametrów dla tego wywołania.

W edytorze zasobów Utwórz fikcyjne polecenie, które używa odpowiedniego identyfikatora polecenia. W poniższym przykładzie użyto `ID_TOOLS_ENTRY` jako identyfikatora polecenia. Ten identyfikator polecenia oznacza lokalizację w jednym lub kilku menu, w których struktura wstawi narzędzia zdefiniowane przez użytkownika.

Należy ustawić kilka kolejnych identyfikatorów w tabeli ciągów, aby przedstawić narzędzia zdefiniowane przez użytkownika. Liczba wyznaczonych ciągów jest równa maksymalnej liczbie narzędzi użytkownika, które użytkownicy mogą definiować. W poniższym przykładzie są one nazwane `ID_USER_TOOL1` przez `ID_USER_TOOL10` .

Możesz zaoferować użytkownikom sugestie dotyczące wybranych katalogów i argumentów dla programów zewnętrznych, które będą wywoływane jako narzędzia. W tym celu Utwórz dwa menu podręczne w edytorze zasobów. W poniższym przykładzie są one nazwane `IDR_MENU_ARGS` i `IDR_MENU_DIRS` . Dla każdego polecenia w tych menu Zdefiniuj ciąg w tabeli ciągów aplikacji. Identyfikator zasobu ciągu musi być równy IDENTYFIKATORowi polecenia.

Możesz również utworzyć klasę pochodną z [klasy CUserTool](../mfc/reference/cusertool-class.md) , aby zastąpić implementację domyślną. W tym celu Przekaż informacje o środowisku uruchomieniowym klasy pochodnej jako czwarty parametr w CWinAppEx:: EnableUserTools, a nie RUNTIME_CLASS ([Klasa CUserTool](../mfc/reference/cusertool-class.md)).

Po zdefiniowaniu odpowiednich stałych Wywołaj [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) , aby włączyć narzędzia zdefiniowane przez użytkownika.

Następujące wywołanie metody pokazuje, jak używać tych stałych:

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

W tym przykładzie karta Tools zostanie uwzględniona w oknie dialogowym **dostosowywania** . Struktura zamieni wszystkie polecenia, które są zgodne z IDENTYFIKATORem polecenia `ID_TOOLS_ENTRY` w dowolnym menu z zestawem aktualnie zdefiniowanych narzędzi użytkownika za każdym razem, gdy użytkownik otworzy to menu. Identyfikatory poleceń w `ID_USER_TOOL1` `ID_USER_TOOL10` programie są zastrzeżone do użycia dla narzędzi zdefiniowanych przez użytkownika. Klasa [CUserTool](../mfc/reference/cusertool-class.md) obsługuje wywołania do narzędzi użytkownika. Karta narzędzia okna dialogowego **Dostosowywanie** zawiera przyciski z prawej strony pola pozycji argumentu i katalogu, aby uzyskać dostęp do menu **IDR_MENU_ARGS** i **IDR_MENU_DIRS**. Gdy użytkownik wybierze polecenie z jednego z tych menu, struktura dołącza do odpowiedniego pola tekstowego ciąg o IDENTYFIKATORze zasobu równy IDENTYFIKATORowi polecenia.

### <a name="including-predefined-tools"></a>Dołączanie wstępnie zdefiniowanych narzędzi

Jeśli chcesz wstępnie zdefiniować niektóre narzędzia do uruchamiania aplikacji, musisz zastąpić metodę [obiektu CFrameWnd:: LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) głównego okna aplikacji. W tej metodzie należy wykonać następujące czynności.

##### <a name="to-add-new-tools-in-loadframe"></a>Aby dodać nowe narzędzia w LoadFrame

1. Uzyskaj wskaźnik do obiektu [klasy CUserToolsManager](../mfc/reference/cusertoolsmanager-class.md) przez wywołanie metody [CWinAppEx:: GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager).

1. Dla każdego narzędzia, które chcesz utworzyć, wywołaj [CUserToolsManager:: CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool). Ta metoda zwraca wskaźnik do obiektu [klasy CUserTool](../mfc/reference/cusertool-class.md) i dodaje nowo utworzone narzędzie użytkownika do wewnętrznej kolekcji narzędzi. Jeśli podano informacje o środowisku uruchomieniowym klasy pochodnej [klasy CUserTool](../mfc/reference/cusertool-class.md) jako czwarty parametr [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager:: CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) spowoduje wystąpienie i zwrócenie wystąpienia tej klasy.

1. Dla każdego narzędzia Ustaw jego etykietę tekstową przez ustawienie `CUserTool::m_strLabel` i ustaw jego polecenie, wywołując metodę `CUserTool::SetCommand` . Domyślna implementacja [klasy CUserTool](../mfc/reference/cusertool-class.md) automatycznie pobiera dostępne ikony z programu, który jest określony w wywołaniu `SetCommand` .

## <a name="see-also"></a>Zobacz też

[Dostosowywanie na potrzeby MFC](../mfc/customization-for-mfc.md)<br/>
[Klasa CUserTool](../mfc/reference/cusertool-class.md)<br/>
[Klasa CUserToolsManager](../mfc/reference/cusertoolsmanager-class.md)<br/>
[Klasa CWinAppEx](../mfc/reference/cwinappex-class.md)
