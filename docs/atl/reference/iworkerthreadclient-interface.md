---
description: Dowiedz się więcej o interfejsie IWorkerThreadClient
title: IWorkerThreadClient, interfejs
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: fb9113c9380453dad9f647fa2f5a2095ff12cea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157987"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient, interfejs

`IWorkerThreadClient` jest interfejsem implementowanym przez klientów klasy [CWorkerThread](../../atl/reference/cworkerthread-class.md) .

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
__interface IWorkerThreadClient
```

## <a name="members"></a>Elementy członkowskie

### <a name="methods"></a>Metody

|Nazwa|Opis|
|-|-|
|[Funkcja](#closehandle)|Zaimplementuj tę metodę, aby zamknąć dojście skojarzone z tym obiektem.|
|[Wykonaj polecenie](#execute)|Zaimplementuj tę metodę, aby wykonać kod, gdy dojście skojarzone z tym obiektem zostanie zasygnalizowane.|

## <a name="remarks"></a>Uwagi

Zaimplementuj ten interfejs, jeśli masz kod, który musi zostać wykonany w wątku roboczym w odpowiedzi na dojście zostanie zasygnalizowane.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlutil. h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a> IWorkerThreadClient:: CloseHandle

Zaimplementuj tę metodę, aby zamknąć dojście skojarzone z tym obiektem.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>Parametry

*hHandle*<br/>
Uchwyt, który ma zostać zamknięty.

### <a name="return-value"></a>Wartość zwracana

Zwróć S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Dojście przesłane do tej metody zostało wcześniej skojarzone z tym obiektem przez wywołanie [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Przykład

Poniższy kod pokazuje prostą implementację programu `IWorkerThreadClient::CloseHandle` .

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a> IWorkerThreadClient:: Execute

Zaimplementuj tę metodę, aby wykonać kod, gdy dojście skojarzone z tym obiektem zostanie zasygnalizowane.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parametry

*dwParam*<br/>
Parametr użytkownika.

*hObject*<br/>
Uchwyt, który został zasygnalizowani.

### <a name="return-value"></a>Wartość zwracana

Zwróć S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Dojście i wskaźnik DWORD przekazano do tej metody, które zostały wcześniej skojarzone z tym obiektem przez wywołanie [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Przykład

Poniższy kod pokazuje prostą implementację programu `IWorkerThreadClient::Execute` .

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>Zobacz też

[Klasy](../../atl/reference/atl-classes.md)<br/>
[Klasa CWorkerThread](../../atl/reference/cworkerthread-class.md)
