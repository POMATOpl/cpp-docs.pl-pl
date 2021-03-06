---
description: 'Dowiedz się więcej o: Tworzenie dostawcy'
title: Tworzenie dostawcy
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
ms.openlocfilehash: 2b5a00f0a873575d9fe7b2b177bb34a6c74e193e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305443"
---
# <a name="creating-the-provider"></a>Tworzenie dostawcy

::: moniker range="msvc-160"

Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

::: moniker-end

::: moniker range="<=msvc-150"

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>Aby utworzyć dostawcę OLE DB przy użyciu kreatora dostawcy ATL OLE DB

1. Kliknij prawym przyciskiem myszy projekt.

1. W menu skrótów kliknij polecenie **Dodaj**, a następnie kliknij przycisk **Dodaj klasę**.

1. W oknie dialogowym **Dodaj klasę** w obszarze **zainstalowane** > **Visual C++** > **biblioteki ATL** wybierz ikonę **dostawca OLEDB ATL** , a następnie kliknij przycisk **Otwórz**.

1. W **Kreatorze dostawcy OLE DB ATL** wpisz krótką nazwę dostawcy w polu **krótka nazwa** . W poniższych tematach użyto krótkiej nazwy *niestandardowej*, ale można użyć innej nazwy. Pozostałe pola nazw wypełniają się zgodnie z wprowadzaną nazwą.

1. W razie konieczności Edytuj pozostałe pola nazw. Oprócz nazw obiektów i plików można edytować następujące elementy:

   - **Coclass**: Nazwa wykorzystywana przez model com do tworzenia dostawcy.

   - **ProgID**: identyfikator programistyczny, który jest ciągiem tekstowym, który może być użyty zamiast identyfikatora GUID.

   - **Wersja**: używany z identyfikatorem ProgID i klasą coclass w celu wygenerowania identyfikatora programistycznego zależnego od wersji.

1. Kliknij przycisk **Finish** (Zakończ).

::: moniker-end

## <a name="see-also"></a>Zobacz też

[Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)
