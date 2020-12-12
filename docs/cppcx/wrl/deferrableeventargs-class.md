---
description: 'Dowiedz się więcej na temat: Klasa DeferrableEventArgs'
title: DeferrableEventArgs — klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 23dae7fef88ff7978790e79a0486a83815467f5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272932"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs — klasa

Klasa szablonu używana dla typów argumentów zdarzeń dla odroczeń.

## <a name="syntax"></a>Składnia

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>Parametry

*TEventArgsInterface*<br/>
Typ interfejsu, który deklaruje argumenty dla odroczonego zdarzenia.

*TEventArgsClass*<br/>
Klasa implementująca *TEventArgsInterface*.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

| Nazwa | Opis |
|--|--|
| [DeferrableEventArgs:: getodroczenie](#getdeferral) | Pobiera odwołanie do obiektu [odroczenia](/uwp/api/windows.foundation.deferral) , który reprezentuje odroczone zdarzenie. |
| [DeferrableEventArgs:: InvokeAllFinished](#invokeallfinished) | Wywołuje się, by wskazać, że wszystkie przetwarzanie do obsługi zdarzenia odroczonego zostało zakończone. |

## <a name="remarks"></a>Uwagi

Wystąpienia tej klasy są przekazane do obsługi zdarzeń dla zdarzeń odroczonych. Parametry szablonu reprezentują interfejs, który definiuje szczegóły argumentów zdarzeń dla określonego typu zdarzenia odroczonego i klasy implementującej ten interfejs.

Klasa jest wyświetlana jako pierwszy argument programu obsługi zdarzeń odroczonego zdarzenia. Metodę [Getodroczenia](#getdeferral) można wywołać, aby uzyskać obiekt [odroczenia](/uwp/api/windows.foundation.deferral) , z którego można uzyskać wszystkie informacje o odroczonym zdarzeniu. Po zakończeniu obsługi zdarzeń należy wywołać metodę Complete dla obiektu odroczenia. Następnie należy wywołać [InvokeAllFinished](#invokeallfinished) na końcu metody obsługi zdarzeń, co gwarantuje, że ukończenie wszystkich odroczonych zdarzeń zostanie prawidłowo przekazane.

## <a name="requirements"></a>Wymagania

**Nagłówek:** Event. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="deferrableeventargsgetdeferral"></a><a name="getdeferral"></a> DeferrableEventArgs:: getodroczenie

Pobiera odwołanie do obiektu [odroczenia](/uwp/api/windows.foundation.deferral) , który reprezentuje odroczone zdarzenie.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>Parametry

*wynika*<br/>
Wskaźnik, który będzie odwoływać się do obiektu [odroczenia](/uwp/api/windows.foundation.deferral) po zakończeniu wywołania.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

## <a name="deferrableeventargsinvokeallfinished"></a><a name="invokeallfinished"></a> DeferrableEventArgs:: InvokeAllFinished

Wywołuje się, by wskazać, że wszystkie przetwarzanie do obsługi zdarzenia odroczonego zostało zakończone.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>Uwagi

Należy wywołać tę metodę po wywołaniu źródła zdarzenia [InvokeAll —](eventsource-class.md#invokeall). Wywołanie tej metody zapobiega podejmowaniu dalszych odroczeń i wymusza wykonywanie procedury obsługi uzupełniania, jeśli nie wykonano żadnych odroczeń.
