---
description: 'Dowiedz się więcej na temat: Klasa COleMessageFilter'
title: Klasa COleMessageFilter
ms.date: 11/04/2016
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
ms.openlocfilehash: f0ab1d473704f5355933c04072a195c12fb71c73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226899"
---
# <a name="colemessagefilter-class"></a>Klasa COleMessageFilter

Zarządza współbieżnością wymaganą przez interakcję aplikacji OLE.

## <a name="syntax"></a>Składnia

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|Konstruuje `COleMessageFilter` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Umieszcza aplikację w stanie zajętym.|
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Włącza i wyłącza okno dialogowe, które pojawia się, gdy wywoływana aplikacja jest zajęta.|
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Włącza i wyłącza okno dialogowe, które pojawia się, gdy wywołana aplikacja nie odpowiada.|
|[COleMessageFilter::EndBusyState](#endbusystate)|Kończy stan zajętości aplikacji.|
|[COleMessageFilter::OnMessagePending](#onmessagepending)|Wywoływane przez platformę, aby przetwarzać komunikaty, gdy wywołanie OLE jest w toku.|
|[COleMessageFilter:: register](#register)|Rejestruje filtr komunikatów za pomocą bibliotek DLL systemu OLE.|
|[COleMessageFilter:: odwołaj](#revoke)|Odwołuje rejestrację filtru komunikatów za pomocą bibliotek DLL systemu OLE.|
|[COleMessageFilter::SetBusyReply](#setbusyreply)|Określa, czy zajęte odpowiedzi aplikacji na wywołanie OLE.|
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Określa, jak długo aplikacja czeka na odpowiedź na wywołanie OLE.|
|[COleMessageFilter::SetRetryReply](#setretryreply)|Określa odpowiedź aplikacji wywołującej na zajętą aplikację.|

## <a name="remarks"></a>Uwagi

`COleMessageFilter`Klasa jest przydatna w edycji wizualnej serwera i aplikacji kontenerów, a także aplikacji automatyzacji OLE. W przypadku aplikacji serwerowych, które są wywoływane, ta klasa może służyć do tworzenia aplikacji w taki sposób, aby wywołania przychodzące z innych aplikacji kontenera zostały anulowane lub ponowione później. Tej klasy można również użyć do określenia akcji, która ma zostać podjęta przez aplikację wywołującą, gdy wywoływana aplikacja jest zajęta.

Typowym zastosowaniem jest w przypadku aplikacji serwerowych wywoływanie [BeginBusyState](#beginbusystate) i [EndBusyState](#endbusystate) , gdy będzie to niebezpieczne dla dokumentu lub innego obiektu dostępnego dla OLE, który ma zostać zniszczony. Te wywołania są wykonywane w [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle) podczas aktualizacji interfejsu użytkownika.

Domyślnie `COleMessageFilter` obiekt jest przypisywany po zainicjowaniu aplikacji. Można go pobrać za pomocą [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

Jest to Klasa zaawansowana; rzadko trzeba będzie bezpośrednio korzystać z niego.

Aby uzyskać więcej informacji, zobacz artykuł [serwery: implementowanie serwera](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Afxole. h

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a> COleMessageFilter::BeginBusyState

Wywołaj tę funkcję, aby rozpocząć stan zajętości.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>Uwagi

Działa w połączeniu z [EndBusyState](#endbusystate) w celu kontrolowania stanu zajętości aplikacji. Funkcja [SetBusyReply](#setbusyreply) określa odpowiedź aplikacji na wywoływanie aplikacji, gdy jest zajęta.

`BeginBusyState`Wywołania i `EndBusyState` zwiększają i zmniejszają odpowiednio licznik, który określa, czy aplikacja jest zajęta. Na przykład dwa wywołania do `BeginBusyState` i jedno wywołanie w celu `EndBusyState` w dalszym ciągu powodują utratę stanu zajętości. Aby anulować stan zajęty, należy wywołać `EndBusyState` tę samą liczbę razy `BeginBusyState` .

Domyślnie struktura wprowadza stan zajętości podczas przetwarzania bezczynnego, która jest wykonywana przez [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Gdy aplikacja obsługuje powiadomienia ON_COMMANDUPDATEUI, wywołania przychodzące są obsługiwane później, po zakończeniu przetwarzania bezczynności.

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a> COleMessageFilter::COleMessageFilter

Tworzy obiekt `COleMessageFilter`.

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a> COleMessageFilter::EnableBusyDialog

Włącza i wyłącza okno dialogowe zajęty, które jest wyświetlane po wygaśnięciu opóźnienia oczekującego komunikatu (zobacz [SetRetryReply](#setretryreply)) podczas wywołania OLE.

```cpp
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>Parametry

*bEnableBusy*<br/>
Określa, czy okno dialogowe "zajęte" jest włączone czy wyłączone.

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a> COleMessageFilter::EnableNotRespondingDialog

Włącza i wyłącza okno dialogowe "nie odpowiada", które jest wyświetlane w przypadku oczekiwania na klawiaturę lub komunikat myszy podczas wywołania OLE, a połączenie przekroczyło limit czasu.

```cpp
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>Parametry

*bEnableNotResponding*<br/>
Określa, czy okno dialogowe "nie odpowiada" jest włączone lub wyłączone.

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a> COleMessageFilter::EndBusyState

Wywołaj tę funkcję, aby zakończyć stan zajętości.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>Uwagi

Działa w połączeniu z [BeginBusyState](#beginbusystate) w celu kontrolowania stanu zajętości aplikacji. Funkcja [SetBusyReply](#setbusyreply) określa odpowiedź aplikacji na wywoływanie aplikacji, gdy jest zajęta.

`BeginBusyState`Wywołania i `EndBusyState` zwiększają i zmniejszają odpowiednio licznik, który określa, czy aplikacja jest zajęta. Na przykład dwa wywołania do `BeginBusyState` i jedno wywołanie w celu `EndBusyState` w dalszym ciągu powodują utratę stanu zajętości. Aby anulować stan zajęty, należy wywołać `EndBusyState` tę samą liczbę razy `BeginBusyState` .

Domyślnie struktura wprowadza stan zajętości podczas przetwarzania bezczynnego, która jest wykonywana przez [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Gdy aplikacja obsługuje powiadomienia ON_UPDATE_COMMAND_UI, wywołania przychodzące są obsługiwane po zakończeniu przetwarzania bezczynności.

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a> COleMessageFilter::OnMessagePending

Wywoływane przez platformę, aby przetwarzać komunikaty, gdy wywołanie OLE jest w toku.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>Parametry

*pMsg*<br/>
Wskaźnik na komunikat oczekujący.

### <a name="return-value"></a>Wartość zwracana

Niezerowe po powodzeniu; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Gdy aplikacja wywołująca oczekuje na zakończenie wywołania, struktura wywołuje `OnMessagePending` wskaźnik do oczekującego komunikatu. Domyślnie architektura wysyła WM_PAINT wiadomości, dzięki czemu aktualizacje okna mogą wystąpić w trakcie wywołania, które trwa długo.

Filtr komunikatów należy zarejestrować, aby [zarejestrować](#register) się, zanim stanie się aktywny.

## <a name="colemessagefilterregister"></a><a name="register"></a> COleMessageFilter:: register

Rejestruje filtr komunikatów za pomocą bibliotek DLL systemu OLE.

```
BOOL Register();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe po powodzeniu; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Filtr komunikatów nie działa, jeśli nie jest zarejestrowany w bibliotekach DLL systemu. Zazwyczaj kod inicjalizacji aplikacji rejestruje filtr komunikatów aplikacji. Każdy inny filtr komunikatów zarejestrowany przez aplikację powinien zostać odwołany przed zakończeniem działania przez wywołanie do [odwołania](#revoke).

Domyślny filtr komunikatów struktury jest automatycznie rejestrowany podczas inicjowania i odwoływany po zakończeniu.

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a> COleMessageFilter:: odwołaj

Odwołuje poprzednią rejestrację wykonywaną przez wywołanie do [rejestracji](#register).

```cpp
void Revoke();
```

### <a name="remarks"></a>Uwagi

Filtr komunikatów powinien zostać odwołany przed zakończeniem działania programu.

Domyślny filtr komunikatów, który jest tworzony i rejestrowany automatycznie przez platformę, również jest automatycznie odwołany.

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a> COleMessageFilter::SetBusyReply

Ta funkcja ustawia "zajęta odpowiedź" aplikacji.

```cpp
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>Parametry

*nBusyReply*<br/>
Wartość z `SERVERCALL` wyliczenia, która jest zdefiniowana w COMPOBJ. H. Może mieć jedną z następujących wartości:

- SERVERCALL_ISHANDLED aplikacja może akceptować wywołania, ale może zakończyć się niepowodzeniem podczas przetwarzania określonego wywołania.

- SERVERCALL_REJECTED prawdopodobnie aplikacja nigdy nie będzie mogła przetworzyć wywołania.

- SERVERCALL_RETRYLATER aplikacja jest tymczasowo w stanie, w którym nie może przetworzyć wywołania.

### <a name="remarks"></a>Uwagi

Funkcje [BeginBusyState](#beginbusystate) i [EndBusyState](#endbusystate) kontrolują stan zajętości aplikacji.

Gdy aplikacja została zajęta przy użyciu wywołania `BeginBusyState` , reaguje na wywołania z bibliotek DLL systemu OLE o wartość określoną przez ostatnie ustawienie `SetBusyReply` . Aplikacja wywołująca używa tej zajętej odpowiedzi, aby określić akcję do wykonania.

Domyślnie jest SERVERCALL_RETRYLATER zajęta odpowiedź. Ta odpowiedź powoduje, że aplikacja wywołująca ponawia próbę wywołania tak szybko, jak to możliwe.

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a> COleMessageFilter::SetMessagePendingDelay

Określa, jak długo aplikacja wywołująca czeka na odpowiedź z wywołanej aplikacji przed podjęciem dalszych działań.

```cpp
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>Parametry

*nTimeout*<br/>
Liczba milisekund opóźnienia oczekiwania komunikatu.

### <a name="remarks"></a>Uwagi

Ta funkcja działa w połączeniu z [SetRetryReply](#setretryreply).

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a> COleMessageFilter::SetRetryReply

Określa akcję aplikacji wywołującej, gdy odbierze zajętą odpowiedź z wywoływanej aplikacji.

```cpp
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>Parametry

*nRetryReply*<br/>
Liczba milisekund między ponownymi próbami.

### <a name="remarks"></a>Uwagi

Gdy wywołana aplikacja wskazuje, że jest zajęta, aplikacja wywołująca może zdecydować się na poczekanie, aż serwer przestanie być zajęty, ponowić próbę od razu lub aby ponowić próbę po upływie określonego interwału. Może również zdecydować się na całkowite anulowanie wywołania.

Odpowiedź obiektu wywołującego jest kontrolowana przez funkcje `SetRetryReply` i [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply` Określa, jak długo aplikacja wywołująca powinna czekać między ponownymi próbami dla danego wywołania. `SetMessagePendingDelay` Określa, jak długo aplikacja wywołująca czeka na odpowiedź z serwera przed podjęciem dalszych działań.

Zazwyczaj wartości domyślne są akceptowalne i nie trzeba ich zmieniać. Platforma ponawia próbę wywołania co *nRetryReply* milisekundy do momentu przełączenia lub opóźnienia oczekiwania na komunikat. Wartość 0 dla *nRetryReply* określa natychmiastową ponowną próbę i-1 określa anulowanie wywołania.

Po wygaśnięciu opóźnień oczekiwanych przez komunikat okno dialogowe "zajęte" (zobacz [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) jest wyświetlane, aby użytkownik mógł anulować lub ponowić próbę wywołania. Wywołaj [EnableBusyDialog](#enablebusydialog) , aby włączyć lub wyłączyć to okno dialogowe.

Gdy w trakcie wywołania zostanie wyświetlona odpowiedź z klawiatury lub myszy, a wywołanie przekroczyło limit czasu (przekroczenie opóźniania komunikatów), wyświetlane jest okno dialogowe "nie odpowiada". Wywołaj [EnableNotRespondingDialog](#enablenotrespondingdialog) , aby włączyć lub wyłączyć to okno dialogowe. Zazwyczaj ten stan działalności wskazuje, że wystąpił problem i użytkownik otrzymuje cierpliwy.

Gdy okna dialogowe są wyłączone, bieżąca "odpowiedź na ponowienie" jest zawsze używana dla wywołań zajętych aplikacji.

## <a name="see-also"></a>Zobacz też

[Klasa CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
