---
description: Dowiedz się więcej o interfejsie ICommandTarget
title: ICommandTarget, interfejs
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: 6deb11ecca94160ea19225fb955826845a4cdefa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219580"
---
# <a name="icommandtarget-interface"></a>ICommandTarget, interfejs

Udostępnia kontrolkę użytkownika z interfejsem do odbierania poleceń z obiektu źródłowego polecenia.

## <a name="syntax"></a>Składnia

```
interface class ICommandTarget
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ICommandTarget:: Initialize](#initialize)|Inicjuje obiekt docelowy polecenia.|

## <a name="remarks"></a>Uwagi

W przypadku hostowania kontrolki użytkownika w widoku MFC [CWinFormsView](../../mfc/reference/cwinformsview-class.md) kieruje polecenia i zaktualizuje komunikaty interfejsu użytkownika do kontrolki użytkownika, aby umożliwić obsługę poleceń MFC (na przykład elementów menu ramek i przycisków paska narzędzi). Implementując `ICommandTarget` , nadajesz użytkownikowi kontrolę odwołania do obiektu [ICommandSource](../../mfc/reference/icommandsource-interface.md) .

Zapoznaj się z tematem [jak to zrobić: Dodawanie routingu poleceń do formantu Windows Forms,](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) aby zapoznać się z przykładem użycia `ICommandTarget` .

Aby uzyskać więcej informacji na temat korzystania z Windows Forms, zobacz [Korzystanie z kontrolki użytkownika formularza systemu Windows w MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwinforms. h (zdefiniowany w zestawie atlmfc\lib\mfcmifc80.dll)

## <a name="icommandtargetinitialize"></a><a name="initialize"></a> ICommandTarget:: Initialize

Inicjuje obiekt docelowy polecenia.

```cpp
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parametry

*cmdSource*<br/>
Uchwyt do obiektu źródłowego polecenia.

### <a name="remarks"></a>Uwagi

W przypadku hostowania kontrolki użytkownika w widoku MFC CWinFormsView kieruje polecenia i zaktualizuje komunikaty interfejsu użytkownika do kontrolki użytkownika, aby umożliwić obsługę poleceń MFC.

Ta metoda inicjuje obiekt docelowy polecenia i kojarzy go z określonym obiektem źródłowym polecenia cmdSource. Powinien być wywoływany w implementacji klasy kontrolki użytkownika. Podczas inicjalizacji należy zarejestrować programy obsługi poleceń z obiektem źródłowym polecenia przez wywołanie ICommandSource:: AddCommandHandler w implementacji inicjowania. Zapoznaj się z tematem jak to zrobić: Dodawanie routingu poleceń do formantu Windows Forms, aby zapoznać się z przykładem użycia metody Initialize w tym celu.

## <a name="see-also"></a>Zobacz też

[Instrukcje: Dodawanie routingu poleceń do kontrolki Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource, interfejs](../../mfc/reference/icommandsource-interface.md)
