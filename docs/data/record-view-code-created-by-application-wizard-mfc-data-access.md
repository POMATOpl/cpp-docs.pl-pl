---
description: 'Dowiedz się więcej na temat: kod widoku rekordu utworzony przez Kreatora aplikacji (dostęp do danych MFC)'
title: Kod widoku rekordu utworzony przez Kreatora aplikacji (dostęp do danych MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: b0fa7a4960096f11ab66194fa6e41be60b45d4c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332435"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Kod widoku rekordu utworzony przez Kreatora aplikacji (dostęp do danych MFC)

[Kreator aplikacji MFC](../mfc/reference/database-support-mfc-application-wizard.md) zastępuje `OnInitialUpdate` funkcje widoku i `OnGetRecordset` elementów członkowskich. Po utworzeniu przez strukturę okna, dokumentu i widoku ramki jest on wywoływany `OnInitialUpdate` w celu zainicjowania widoku. `OnInitialUpdate` uzyskuje wskaźnik do zestawu rekordów z dokumentu. Wywołanie klasy bazowej [CView:: OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) otwiera zestaw rekordów. Poniższy kod przedstawia ten proces dla `CRecordView` :

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

Gdy zestaw rekordów zostanie otwarty, wybiera rekordy. [CRecordset:: Open](../mfc/reference/crecordset-class.md#open) sprawia, że pierwszy rekord bieżącego rekordu, a DDX przenosi dane z elementów członkowskich danych pola zestawu rekordów do odpowiednich kontrolek formularza w widoku. Aby uzyskać więcej informacji na temat RFX, zobacz [wymiany pól rekordów (RFX)](../data/odbc/record-field-exchange-rfx.md). Aby uzyskać więcej informacji na temat DDX, zobacz temat [wymiana i walidacja danych w oknie dialogowym](../mfc/dialog-data-exchange-and-validation.md). Aby uzyskać informacje na temat procesu tworzenia dokumentu/widoku, zobacz [Używanie klas do pisania aplikacji dla systemu Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

> [!NOTE]
> Należy dać użytkownikom końcowym możliwość odświeżania formantów widoku rekordów z zestawu rekordów. Bez tej możliwości, jeśli użytkownik zmieni wartość kontrolki na niedozwoloną wartość, użytkownik może zostać trwale zablokowany w bieżącym rekordzie. Aby odświeżyć kontrolki, należy wywołać `CWnd` funkcję członkowską [UpdateData](../mfc/reference/cwnd-class.md#updatedata) z parametrem false.

## <a name="see-also"></a>Zobacz też

[Korzystanie z widoku rekordu](../data/using-a-record-view-mfc-data-access.md)
