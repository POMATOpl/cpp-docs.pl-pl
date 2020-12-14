---
description: 'Dowiedz się więcej o: Wstawianie formularza do projektu'
title: Wstawianie formularza do projektu
ms.date: 11/04/2016
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
ms.openlocfilehash: d0c67532261e4c5a5740f4ff07543f141b34d7a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220490"
---
# <a name="inserting-a-form-into-a-project"></a>Wstawianie formularza do projektu

Formularze zapewniają wygodny kontener dla kontrolek. Możesz łatwo wstawić formularz oparty na MFC do swojej aplikacji, o ile aplikacja obsługuje biblioteki MFC.

### <a name="to-insert-a-form-into-your-project"></a>Aby wstawić formularz do projektu

1. W obszarze Widok klasy wybierz projekt, do którego chcesz dodać formularz, a następnie kliknij prawym przyciskiem myszy.

1. W menu skrótów kliknij pozycję **Dodaj** , a następnie kliknij pozycję **Dodaj klasę**.

   Jeśli **nowy formularz** nie jest dostępny, projekt może opierać się na Active Template Library (ATL). Aby dodać formularz do projektu ATL, należy [określić niektóre ustawienia](../atl/reference/application-settings-atl-project-wizard.md) podczas pierwszego tworzenia projektu.

1. W folderze **MFC** kliknij pozycję **Klasa MFC**.

1. Za pomocą kreatora klas MFC, Utwórz nową klasę pochodną od [CFormView](reference/cformview-class.md).

Visual C++ dodaje formularz do aplikacji, otwierając go w edytorze okien dialogowych, aby można było rozpocząć dodawanie kontrolek i pracować nad jej ogólnym projektem.

Może być konieczne wykonanie następujących dodatkowych czynności (nie dotyczy aplikacji opartych na oknach dialogowych):

1. Przesłoń `OnUpdate` funkcję członkowską.

1. Zaimplementuj funkcję członkowską, aby przenieść dane z widoku do dokumentu.

1. Utwórz `OnPrint` funkcję członkowską.

## <a name="see-also"></a>Zobacz też

[Widoki formularzy](form-views-mfc.md)
