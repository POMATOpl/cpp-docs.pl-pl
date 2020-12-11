---
description: 'Dowiedz się więcej o: obsługa MFC w projektach ATL'
title: Obsługa MFC w projektach ATL
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 8614bfdd5320e0ecdf34cc96251fa8a20f2dede9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157922"
---
# <a name="mfc-support-in-atl-projects"></a>Obsługa MFC w projektach ATL

W przypadku wybrania opcji **Obsługa MFC** w Kreatorze projektu ATL, projekt deklaruje aplikację jako obiekt aplikacji MFC (Klasa). Projekt inicjuje bibliotekę MFC i tworzy wystąpienie klasy ( *Projname*), która pochodzi od [CWinApp](../../mfc/reference/cwinapp-class.md).

Ta opcja jest dostępna tylko dla projektów bibliotek DLL ATL, które nie są atrybutami.

```
class CProjNameApp : public CWinApp
{
public:

// Overrides
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)
END_MESSAGE_MAP()

CProjNameApp theApp;

BOOL CProjNameApp::InitInstance()
{
    return CWinApp::InitInstance();

}

int CProjNameApp::ExitInstance()
{
    return CWinApp::ExitInstance();

}
```

Można wyświetlić klasy obiektów aplikacji i jej `InitInstance` `ExitInstance` funkcje oraz w widok klasy.

## <a name="see-also"></a>Zobacz też

[Dodawanie klasy](../../ide/adding-a-class-visual-cpp.md)<br/>
[Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)<br/>
[Domyślne konfiguracje projektu ATL](../../atl/reference/default-atl-project-configurations.md)
