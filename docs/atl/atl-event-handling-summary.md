---
description: 'Dowiedz się więcej na temat: Podsumowanie obsługi zdarzeń ATL'
title: Podsumowanie obsługi zdarzeń ATL
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
ms.openlocfilehash: c041de6cbd0e0852d5ce0e51d892c21c7d9a23d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148658"
---
# <a name="atl-event-handling-summary"></a>Podsumowanie obsługi zdarzeń ATL

Ogólnie rzecz biorąc, obsługa zdarzeń COM to stosunkowo prosty proces. Istnieją trzy główne kroki:

- Zaimplementuj interfejs zdarzenia w obiekcie.

- Należy polecić Źródło zdarzenia, że obiekt chce otrzymywać zdarzenia.

- Jeśli obiekt nie musi już odbierać zdarzeń, należy wykonać niezalecanie źródła zdarzeń.

## <a name="implementing-the-interface"></a>Implementowanie interfejsu

Istnieją cztery główne sposoby implementacji interfejsu przy użyciu biblioteki ATL.

|Pochodny od|Odpowiednie dla typu interfejsu|Wymaga zaimplementowania wszystkich metod *|Wymaga biblioteki typów w czasie wykonywania|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|Interfejs|Tablic|Tak|Nie|
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Podwójne|Tak|Tak|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|Nie|Tak|
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|Nie|Nie|

\* W przypadku korzystania z klas obsługi ATL, nigdy nie jest wymagane, `IUnknown` Aby `IDispatch` ręcznie zaimplementować metody lub.

## <a name="advising-and-unadvising-the-event-source"></a>Doradzanie i niedoradzanie źródła zdarzeń

Istnieją trzy główne sposoby doradzania i niedoradzania źródła zdarzeń przy użyciu biblioteki ATL.

|Advise — funkcja|Unadvise — funkcja|Najbardziej odpowiednie do użycia z|Wymaga śledzenia pliku cookie|Komentarze|
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Tablice lub podwójne interfejsy|Tak|`AtlAdvise` jest globalną funkcją ATL. `CComPtrBase::Advise` jest używany przez [CComPtr](../atl/reference/ccomptr-class.md) i [CComQIPtr](../atl/reference/ccomqiptr-class.md).|
|[IDispEventSimpleImpl::D ispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::D ispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) lub [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Nie|Mniejsza liczba parametrów niż `AtlAdvise` ponieważ klasa bazowa wykonuje więcej pracy.|
|[CComCompositeControl:: AdviseSinkMap (TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl:: AdviseSinkMap (FAŁSZ)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|Kontrolki ActiveX w kontrolkach złożonych|Nie|`CComCompositeControl::AdviseSinkMap` zaleca wszystkie wpisy na mapie ujścia zdarzeń. Ta sama funkcja Niezaleca wpisów. Ta metoda jest wywoływana automatycznie przez `CComCompositeControl` klasę.|
|[CAxDialogImpl:: AdviseSinkMap (TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl:: AdviseSinkMap (FAŁSZ)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|Kontrolki ActiveX w oknie dialogowym|Nie|`CAxDialogImpl::AdviseSinkMap` doradza i niedoradza wszystkim kontrolkom ActiveX w zasobie okna dialogowego. Jest to wykonywane automatycznie.|

## <a name="see-also"></a>Zobacz też

[Obsługa zdarzeń](../atl/event-handling-and-atl.md)<br/>
[Obsługa interfejsu IDispEventImpl](../atl/supporting-idispeventimpl.md)
