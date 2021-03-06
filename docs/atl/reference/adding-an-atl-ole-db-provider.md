---
description: 'Dowiedz się więcej na temat: Dodawanie dostawcy ATL OLE DB'
title: Dodawanie dostawcy ATL OLE DB
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB, adding ATL OLE DB provider to projects
- ATL projects, adding ATL OLE DB providers
- ATL OLE DB providers
ms.assetid: 26fba1e3-880f-4bc6-90e5-2096a48a3a6c
ms.openlocfilehash: e60150e2d8dc57e16a55c75556d109583a95f054
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165670"
---
# <a name="adding-an-atl-ole-db-provider"></a>Dodawanie dostawcy ATL OLE DB

::: moniker range="msvc-160"

Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

::: moniker-end

::: moniker range="<=msvc-150"

Użyj tego kreatora, aby dodać dostawcę OLE DB ATL do projektu. Dostawca ATL OLE DB składa się z klas źródła danych, sesji, polecenia i zestawu wierszy. Projekt musi zostać utworzony jako aplikacja ATL COM.

## <a name="to-add-an-atl-ole-db-provider-to-your-project"></a>Aby dodać dostawcę OLE DB ATL do projektu

1. W **Widok klasy** kliknij prawym przyciskiem myszy projekt. W menu skrótów kliknij pozycję **Dodaj** , a następnie kliknij pozycję **Dodaj klasę**.

1. W folderze **Visual C++** kliknij dwukrotnie ikonę **dostawcy ATL OLE DB** lub wybierz ją, a następnie kliknij przycisk **Otwórz**.

   Zostanie otwarty Kreator dostawcy OLE DB ATL.

1. Zdefiniuj ustawienia zgodnie z opisem w [kreatorze OLE DB dostawcy ATL](../../atl/reference/atl-ole-db-provider-wizard.md).

1. Kliknij przycisk **Zakończ** , aby zamknąć kreatora, co spowoduje wstawienie nowo utworzonego kodu dostawcy OLE DB w projekcie.

::: moniker-end

## <a name="see-also"></a>Zobacz też

[Dodawanie funkcji za pomocą kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)
