---
description: 'Dowiedz się więcej na temat: Dodawanie obsługi ATL do projektu MFC'
title: Dodawanie obsługi ATL do projektu MFC
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 1d02bd6e63a01334fcb9a907dc9ea4fe78ff4a48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248245"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>Dodawanie obsługi ATL do projektu MFC

Jeśli utworzono już aplikację opartą na MFC, możesz łatwo dodać obsługę Active Template Library (ATL) przy użyciu środowiska IDE.

> [!NOTE]
> Ta obsługa dotyczy tylko prostych obiektów COM dodanych do pliku wykonywalnego MFC lub projektu DLL. Można dodać inne obiekty COM (w tym kontrolki ActiveX) do projektów MFC, ale obiekty mogą nie działać zgodnie z oczekiwaniami.

::: moniker range=">=msvc-160"

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy węzeł projektu.

1. W menu skrótów kliknij polecenie **Dodaj**, a następnie kliknij pozycję **nowy element**.

1. Wybierz **ATL** w lewym okienku, a następnie wybierz opcję **Obsługa ATL** w środkowym okienku.

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-add-atl-support-to-your-mfc-project"></a>Aby dodać obsługę ATL do projektu MFC

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy węzeł projektu.

1. W menu skrótów kliknij polecenie **Dodaj**, a następnie kliknij przycisk **Dodaj klasę**.

1. W lewym okienku wybierz pozycję **ATL** , a następnie wybierz pozycję **Dodaj obsługę ATL do projektu MFC** w środkowym okienku.

::: moniker-end

Aby uzyskać więcej informacji o tym, jak dodawanie obsługi ATL zmienia kod projektu MFC, zobacz [szczegóły obsługi ATL dodanej przez kreatora ATL](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)

## <a name="see-also"></a>Zobacz też

[Dodawanie klasy](../../ide/adding-a-class-visual-cpp.md)<br/>
[Dodawanie funkcji za pomocą kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Dodawanie funkcji członkowskiej](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Dodawanie zmiennej członkowskiej](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Zastępowanie funkcji wirtualnej](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Procedura obsługi komunikatów MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Nawigacja w strukturze klas](../../ide/navigate-code-cpp.md)
