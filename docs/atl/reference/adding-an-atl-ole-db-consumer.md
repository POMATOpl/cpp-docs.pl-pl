---
title: Dodawanie konsumenta ATL OLE DB
ms.date: 05/09/2019
helpviewer_keywords:
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: c298a841bf0d37f90bcd6b53bc0c6cdf501f4dd3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921155"
---
# <a name="adding-an-atl-ole-db-consumer"></a>Dodawanie konsumenta ATL OLE DB

::: moniker range="msvc-160"

Kreator użytkownika ATL OLE DB nie jest dostępny w programie Visual Studio 2019 i nowszych. Można nadal ręcznie dodawać funkcje. Aby uzyskać więcej informacji, zobacz [Tworzenie klienta bez korzystania z Kreatora](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="<=msvc-150"

Użyj tego kreatora, aby dodać klienta ATL OLE DB do projektu. Odbiorca ATL OLE DB składa się z klasy dostępu OLE DB i powiązań danych niezbędnych do uzyskania dostępu do źródła danych. Projekt musi zostać utworzony jako aplikacja ATL COM lub jako aplikacja MFC lub Win32, która zawiera obsługę ATL (automatycznie dodawany przez kreatora ATL OLE DB użytkownika).

> [!NOTE]
> Do projektu MFC można dodać klienta OLE DB. W takim przypadku Kreator OLE DB użytkownika ATL dodaje do projektu niezbędną obsługę COM. Przyjęto założenie, że podczas tworzenia projektu MFC zostało zaznaczone pole wyboru **kontrolki ActiveX** (na stronie **funkcje zaawansowane** Kreatora aplikacji projektu MFC), które jest domyślnie zaznaczone. Wybranie tej opcji zapewnia, że aplikacja wywołuje `CoInitialize` i `CoUninitialize` . Jeśli nie wybrano **formantów ActiveX** podczas tworzenia projektu MFC, należy wywołać `CoInitialize` i `CoUninitialize` w kodzie głównym.

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Aby dodać klienta ATL OLE DB do projektu

1. W **Widok klasy** kliknij prawym przyciskiem myszy projekt. W menu skrótów kliknij pozycję **Dodaj** , a następnie kliknij pozycję **Dodaj klasę** .

1. W folderze Visual C++ kliknij dwukrotnie ikonę **klienta ATL OLE DB** lub wybierz ją, a następnie kliknij przycisk **Otwórz** .

   Zostanie otwarty Kreator OLE DB użytkownika ATL.

1. Zdefiniuj ustawienia zgodnie z opisem w [Kreatorze ATL OLE DB klienta](../../atl/reference/atl-ole-db-consumer-wizard.md).

1. Kliknij przycisk **Zakończ** , aby zamknąć kreatora. Nowo utworzony kod klienta OLE DB zostanie wstawiony do projektu.

::: moniker-end

## <a name="see-also"></a>Zobacz także

[Dodawanie funkcji za pomocą kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)
