---
description: 'Dowiedz się więcej na temat: Drukowanie programistyczne'
title: Drukowanie programowe
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
ms.openlocfilehash: c97a3938a97970e1479add4f62b68250845ba7e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154698"
---
# <a name="programmatic-printing"></a>Drukowanie programowe

Technologia OLE zapewniała metodę w celu jednoznacznego zidentyfikowania trwałych dokumentów ( `GetClassFile` ) i załadowania ich do skojarzonych z nimi kodów ( `CoCreateInstance` , `QueryInterface(IID_IPersistFile)` ,, `QueryInterface(IID_IPersistStorage)` `IPersistFile::Load` i `IPersistStorage::Load` ). Aby dodatkowo włączyć dokumenty drukowania, zawieranie dokumentów aktywnych (przy użyciu istniejącego projektu OLE, który nie został dostarczony ze standardem OLE 2,0) wprowadza podstawowy, standardowy interfejs drukowania, `IPrint` ogólnie dostępny za pośrednictwem dowolnego obiektu, który może ładować trwały stan typu dokumentu. Każdy widok aktywnego dokumentu może opcjonalnie obsługiwać `IPrint` interfejs, aby zapewnić te możliwości.

`IPrint`Interfejs jest zdefiniowany w następujący sposób:

```
interface IPrint : IUnknown
    {
    HRESULT SetInitialPageNum([in] LONG nFirstPage);
    HRESULT GetPageInfo(
        [out] LONG *pnFirstPage,
        [out] LONG *pcPages);
    HRESULT Print(
        [in] DWORD grfFlags,
        [in,out] DVTARGETDEVICE **pptd,
        [in,out] PAGESET ** ppPageSet,
        [in,out] STGMEDIUM **ppstgmOptions,
        [in] IContinueCallback* pCallback,
        [in] LONG nFirstPage,
        [out] LONG *pcPagesPrinted,
        [out] LONG *pnPageLast);
    };
```

Klienci i kontenery są używane po prostu, `IPrint::Print` Aby wymusić drukowanie dokumentu po jego załadowaniu, określeniu flag kontrolek drukowania, urządzenia docelowego, stron do drukowania i dodatkowych opcji. Klient może również kontrolować kontynuację drukowania za pomocą interfejsu `IContinueCallback` (patrz poniżej).

Ponadto program `IPrint::SetInitialPageNum` obsługuje możliwość drukowania szeregu dokumentów jako jednej przez bezproblemową liczbę stron, co umożliwia bezproblemowe korzystanie z kontenerów dokumentów aktywnych, takich jak Office Binder. `IPrint::GetPageInfo` sprawia, że wyświetlanie informacji o stronicowaniu jest proste, umożliwiając obiektowi wywołującemu pobranie numeru strony początkowej, który wcześniej przeszedł do `SetInitialPageNum` (lub wewnętrzny numer strony początkowej dokumentu) oraz liczbę stron w dokumencie.

Obiekty, które obsługują, `IPrint` są oznaczone w rejestrze z kluczem "drukowalny" przechowywanym w obiekcie CLSID obiektu:

HKEY_CLASSES_ROOT\CLSID\\ {...} \Printable

`IPrint` jest zwykle zaimplementowany dla tego samego obiektu, który obsługuje jeden `IPersistFile` lub `IPersistStorage` . Obiekty wywołujące zapewnią możliwość programowego drukowania trwałego stanu niektórych klas przez przeszukanie w rejestrze klucza "drukowalnego". Obecnie "drukowalne" oznacza obsługę co najmniej `IPrint` ; inne interfejsy mogą być zdefiniowane w przyszłości, a następnie dostępne w `QueryInterface` przypadku `IPrint` , gdy po prostu reprezentuje podstawowy poziom wsparcia.

Podczas procedury drukowania może być potrzebny klient lub kontener, który zainicjował drukowanie, aby kontrolować, czy drukowanie powinno być kontynuowane. Na przykład kontener może obsługiwać polecenie "Stop Print", które powinno przerwać zadanie drukowania tak szybko, jak to możliwe. Aby zapewnić obsługę tej możliwości, klient obiektu drukowalnego może zaimplementować mały obiekt ujścia powiadomień z interfejsem `IContinueCallback` :

```
interface IContinueCallback : IUnknown
    {
    HRESULT FContinue(void);
    HRESULT FContinuePrinting(
        [in] LONG cPagesPrinted,
        [in] LONG nCurrentPage,
        [in] LPOLESTR pszPrintStatus);
    };
```

Ten interfejs jest zaprojektowany tak, aby był przydatny jako ogólna funkcja wywołania zwrotnego kontynuacji, która uwzględnia różne procedury kontynuacji w Win32 API ( `AbortProc` na przykład do drukowania i `EnumMetafileProc` wyliczenia metaplików). Ten projekt interfejsu jest przydatny w wielu czasochłonnych procesach.

W najbardziej ogólnych przypadkach `IContinueCallback::FContinue` Funkcja jest wywoływana okresowo przez dowolny długi proces. Obiekt ujścia zwraca S_OK, aby kontynuować operację, i S_FALSE do zatrzymania procedury najszybciej, jak to możliwe.

`FContinue`nie jest jednak używany w kontekście `IPrint::Print` ; raczej drukowanie ma zastosowanie `IContinueCallback::FContinuePrint` . Każdy obiekt drukowania powinien okresowo wywoływać `FContinuePrinting` liczbę stron, które zostały wydrukowane, liczbę drukowanych stron i dodatkowy ciąg opisujący stan drukowania, który klient może wybrać do wyświetlenia użytkownikowi (na przykład "Strona 5 z 19").

## <a name="see-also"></a>Zobacz też

[Kontenery dokumentów aktywnych](../mfc/active-document-containers.md)
