---
description: Dowiedz się więcej o interfejsie ICommandSource
title: ICommandSource, interfejs
ms.date: 03/27/2019
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: 711baeccd76c88db365b465cbc3c4cc05048a0f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219593"
---
# <a name="icommandsource-interface"></a>ICommandSource, interfejs

Zarządza poleceniami wysyłanymi z obiektu źródłowego polecenia do kontrolki użytkownika.

## <a name="syntax"></a>Składnia

```cpp
interface class ICommandSource
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ICommandSource:: AddCommandHandler](#addcommandhandler)|Dodaje procedurę obsługi polecenia do obiektu źródłowego polecenia.|
|[ICommandSource:: AddCommandRangeHandler](#addcommandrangehandler)|Dodaje grupę obsługi poleceń do obiektu źródłowego polecenia.|
|[ICommandSource:: AddCommandRangeUIHandler](#addcommandrangeuihandler)|Dodaje grupę obsługi komunikatów poleceń interfejsu użytkownika do obiektu źródłowego polecenia.|
|[ICommandSource:: AddCommandUIHandler](#addcommandrangeuihandler)|Dodaje procedurę obsługi komunikatów interfejsu użytkownika do obiektu źródłowego polecenia.|
|[ICommandSource::P ostCommand](#postcommand)|Publikuje komunikat bez oczekiwania na jego przetworzenie.|
|[ICommandSource:: RemoveCommandHandler](#removecommandhandler)|Usuwa procedurę obsługi poleceń z obiektu źródłowego polecenia.|
|[ICommandSource:: RemoveCommandRangeHandler](#removecommandrangehandler)|Usuwa grupę programów obsługi poleceń z obiektu źródłowego polecenia.|
|[ICommandSource:: RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Usuwa grupę procedur obsługi komunikatów poleceń interfejsu użytkownika z obiektu źródłowego polecenia.|
|[ICommandSource:: RemoveCommandUIHandler](#removecommandrangeuihandler)|Usuwa procedurę obsługi komunikatów interfejsu użytkownika z obiektu źródłowego polecenia.|
|[ICommandSource:: SendCommand](#sendcommand)|Wysyła komunikat i czeka na jego przetwarzanie przed zwróceniem.|

### <a name="remarks"></a>Uwagi

W przypadku hostowania kontrolki użytkownika w widoku MFC [Klasa CWinFormsView](../../mfc/reference/cwinformsview-class.md) kieruje polecenia i aktualizuje komunikaty interfejsu użytkownika do kontrolki użytkownika, aby umożliwić obsługę poleceń MFC (na przykład elementów menu ramek i przycisków paska narzędzi). Implementując [Interfejs ICommandTarget](../../mfc/reference/icommandtarget-interface.md), nadajesz użytkownikowi kontrolę odwołania do `ICommandSource` obiektu.

Zapoznaj się z tematem [jak to zrobić: Dodawanie routingu poleceń do formantu Windows Forms,](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) aby zapoznać się z przykładem użycia `ICommandTarget` .

Aby uzyskać więcej informacji na temat korzystania z Windows Forms, zobacz [Korzystanie z kontrolki użytkownika formularza systemu Windows w MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Wymagania

**Nagłówek:** afxwinforms. h (zdefiniowany w zestawie atlmfc\lib\mfcmifc80.dll)

## <a name="icommandsourceaddcommandhandler"></a><a name="addcommandhandler"></a> ICommandSource:: AddCommandHandler

Dodaje procedurę obsługi polecenia do obiektu źródłowego polecenia.

```cpp
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametry

*cmdID*<br/>
Identyfikator polecenia.
*cmdHandler*<br/>
Dojście do metody obsługi poleceń.

### <a name="remarks"></a>Uwagi

Ta metoda dodaje procedurę obsługi poleceń cmdHandler do obiektu źródłowego polecenia i mapuje procedurę obsługi na cmdID.
Zapoznaj się z tematem [jak to zrobić: Dodawanie routingu poleceń do formantu Windows Forms,](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) aby zapoznać się z przykładem korzystania z AddCommandHandler.

## <a name="icommandsourceaddcommandrangehandler"></a><a name="addcommandrangehandler"></a> ICommandSource:: AddCommandRangeHandler

Dodaje grupę obsługi poleceń do obiektu źródłowego polecenia.

```cpp
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametry

*cmdIDMin*<br/>
Początkowy indeks zakresu identyfikatora polecenia.
*cmdIDMax*<br/>
Końcowy indeks zakresu identyfikatora polecenia.
*cmdHandler*<br/>
Dojście do metody obsługi komunikatów, do której są mapowane polecenia.

### <a name="remarks"></a>Uwagi

Ta metoda mapuje ciągły zakres identyfikatorów poleceń do obsługi jednego komunikatu i dodaje go do obiektu źródłowego polecenia. Służy do obsługi grupy powiązanych przycisków przy użyciu jednej metody.

## <a name="icommandsourceaddcommandrangeuihandler"></a><a name="addcommandrangeuihandler"></a> ICommandSource:: AddCommandRangeUIHandler

Dodaje grupę obsługi komunikatów poleceń interfejsu użytkownika do obiektu źródłowego polecenia.

```cpp
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametry

*cmdIDMin*<br/>
Początkowy indeks zakresu identyfikatora polecenia.
*cmdIDMax*<br/>
Końcowy indeks zakresu identyfikatora polecenia.
*cmdHandler*<br/>
Dojście do metody obsługi komunikatów, do której są mapowane polecenia.

### <a name="remarks"></a>Uwagi

Ta metoda mapuje ciągły zakres identyfikatorów poleceń do procedury obsługi komunikatów jednego interfejsu użytkownika i dodaje ją do obiektu źródłowego polecenia. Służy do obsługi grupy powiązanych przycisków przy użyciu jednej metody.

## <a name="icommandsourceaddcommanduihandler"></a><a name="addcommanduihandler"></a> ICommandSource:: AddCommandUIHandler

Dodaje procedurę obsługi komunikatów interfejsu użytkownika do obiektu źródłowego polecenia.

```cpp
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametry

*cmdID*<br/>
Identyfikator polecenia.
*cmdUIHandler*<br/>
Dojście do metody obsługi komunikatów polecenia interfejsu użytkownika.

### <a name="remarks"></a>Uwagi

Ta metoda dodaje procedurę obsługi komunikatów interfejsu użytkownika cmdHandler do obiektu źródłowego polecenia i mapuje procedurę obsługi na cmdID.

## <a name="icommandsourcepostcommand"></a><a name="postcommand"></a> ICommandSource::P ostCommand

Publikuje komunikat bez oczekiwania na jego przetworzenie.

```cpp
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parametry

*dotyczące*<br/>
Identyfikator polecenia wiadomości do opublikowania.

### <a name="remarks"></a>Uwagi

Ta metoda asynchronicznie zapisuje komunikat mapowany do identyfikatora określonego przez polecenie. Wywołuje CWnd::P ostMessage, aby umieścić komunikat w kolejce komunikatów okna, a następnie zwraca bez oczekiwania na odpowiednie okno do przetworzenia komunikatu.

## <a name="icommandsourceremovecommandhandler"></a><a name="removecommandhandler"></a> ICommandSource:: RemoveCommandHandler

Usuwa procedurę obsługi poleceń z obiektu źródłowego polecenia.

```cpp
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametry

*cmdID*<br/>
Identyfikator polecenia.

### <a name="remarks"></a>Uwagi

Ta metoda usuwa procedurę obsługi poleceń zamapowana do cmdID z obiektu źródłowego polecenia.

## <a name="icommandsourceremovecommandrangehandler"></a><a name="removecommandrangehandler"></a> ICommandSource:: RemoveCommandRangeHandler

Usuwa grupę programów obsługi poleceń z obiektu źródłowego polecenia.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametry

*cmdIDMin*<br/>
Początkowy indeks zakresu identyfikatora polecenia.
*cmdIDMax*<br/>
Końcowy indeks zakresu identyfikatora polecenia.

### <a name="remarks"></a>Uwagi

Ta metoda usuwa grupę programów obsługi komunikatów, mapowanych na identyfikatory poleceń określonych przez cmdIDMin i cmdIDMax, z obiektu źródłowego polecenia.

## <a name="icommandsourceremovecommandrangeuihandler"></a><a name="removecommandrangeuihandler"></a> ICommandSource:: RemoveCommandRangeUIHandler

Usuwa grupę procedur obsługi komunikatów poleceń interfejsu użytkownika z obiektu źródłowego polecenia.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametry

*cmdIDMin*<br/>
Początkowy indeks zakresu identyfikatora polecenia.
*cmdIDMax*<br/>
Końcowy indeks zakresu identyfikatora polecenia.

### <a name="remarks"></a>Uwagi

Ta metoda usuwa grupę obsługi komunikatów poleceń interfejsu użytkownika, zamapowane na identyfikatory poleceń określone przez cmdIDMin i cmdIDMax, z obiektu źródłowego polecenia.

## <a name="icommandsourceremovecommanduihandler"></a><a name="removecommanduihandler"></a> ICommandSource:: RemoveCommandUIHandler

Usuwa procedurę obsługi komunikatów interfejsu użytkownika z obiektu źródłowego polecenia.

```cpp
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametry

*cmdID*<br/>
Identyfikator polecenia.

### <a name="remarks"></a>Uwagi

Ta metoda usuwa procedurę obsługi komunikatów interfejsu użytkownika zamapowana do cmdID z obiektu źródłowego polecenia.

## <a name="icommandsourcesendcommand"></a><a name="sendcommand"></a> ICommandSource:: SendCommand

Wysyła komunikat i czeka na jego przetwarzanie przed zwróceniem.

```cpp
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parametry

*dotyczące*<br/>
Identyfikator polecenia wiadomości do wysłania.

### <a name="remarks"></a>Uwagi

Ta metoda synchronicznie wysyła komunikat mapowany do identyfikatora określonego przez polecenie. Wywołuje CWnd:: SendMessage, aby umieścić komunikat w kolejce komunikatów okna i czekać, aż ta procedura okna przetworzy komunikat przed zwróceniem.

## <a name="see-also"></a>Zobacz też

[Instrukcje: Dodawanie routingu poleceń do kontrolki Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget, interfejs](../../mfc/reference/icommandtarget-interface.md)
