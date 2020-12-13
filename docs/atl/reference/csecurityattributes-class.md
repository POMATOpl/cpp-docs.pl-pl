---
description: 'Dowiedz się więcej na temat: Klasa CSecurityAttributes'
title: Klasa CSecurityAttributes
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: 8cb772e574aef4ad941feef1cb838fb91d937576
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140819"
---
# <a name="csecurityattributes-class"></a>Klasa CSecurityAttributes

Ta klasa jest cienkim otoką dla struktury atrybutów zabezpieczeń.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSecurityAttributes:: Set](#set)|Wywołaj tę metodę, aby ustawić atrybuty `CSecurityAttributes` obiektu.|

## <a name="remarks"></a>Uwagi

`SECURITY_ATTRIBUTES`Struktura zawiera [deskryptor zabezpieczeń](/windows/win32/api/winnt/ns-winnt-security_descriptor) używany do tworzenia obiektu i określa, czy dojście pobrane przez określenie tej struktury jest dziedziczenia.

Aby zapoznać się z wprowadzeniem do modelu kontroli dostępu w systemie Windows, zobacz [Access Control](/windows/win32/SecAuthZ/access-control) w Windows SDK.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsecurity. h

## <a name="csecurityattributescsecurityattributes"></a><a name="csecurityattributes"></a> CSecurityAttributes::CSecurityAttributes

Konstruktor.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Parametry

*rSecurityDescriptor*<br/>
Odwołanie do deskryptora zabezpieczeń.

*bInheritsHandle*<br/>
Określa, czy zwracany uchwyt jest dziedziczony podczas tworzenia nowego procesu. Jeśli ten element członkowski ma wartość true, nowy proces dziedziczy dojście.

## <a name="csecurityattributesset"></a><a name="set"></a> CSecurityAttributes:: Set

Wywołaj tę metodę, aby ustawić atrybuty `CSecurityAttributes` obiektu.

```cpp
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parametry

*rSecurityDescriptor*<br/>
Odwołanie do deskryptora zabezpieczeń.

*bInheritHandle*<br/>
Określa, czy zwracany uchwyt jest dziedziczony podczas tworzenia nowego procesu. Jeśli ten element członkowski ma wartość true, nowy proces dziedziczy dojście.

### <a name="remarks"></a>Uwagi

Ta metoda jest używana przez konstruktora do inicjowania `CSecurityAttributes` obiektu.

## <a name="see-also"></a>Zobacz też

[Przykład zabezpieczeń](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[deskryptor zabezpieczeń](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Funkcje globalne zabezpieczeń](../../atl/reference/security-global-functions.md)
