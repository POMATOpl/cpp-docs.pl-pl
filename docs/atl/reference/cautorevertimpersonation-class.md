---
description: 'Dowiedz się więcej na temat: Klasa CAutoRevertImpersonation'
title: Klasa CAutoRevertImpersonation
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: 48009a4d146866d36eebc75ada8f9ae12058287a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147085"
---
# <a name="cautorevertimpersonation-class"></a>Klasa CAutoRevertImpersonation

Ta klasa przywraca niepersonifikowanie obiektów [CAccessToken](../../atl/reference/caccesstoken-class.md) , gdy wykracza poza zakres.

## <a name="syntax"></a>Składnia

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Konstruuje `CAutoRevertImpersonation` obiekt|
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Niszczy obiekt i przywraca personifikację tokenu dostępu.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAutoRevertImpersonation:: Attach](#attach)|Automatyzuje rewersję tokenu dostępu do personifikacji.|
|[CAutoRevertImpersonation::D etach](#detach)|Anuluje rewersję automatycznej personifikacji.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Pobiera token dostępu bieżący skojarzony z tym obiektem.|

## <a name="remarks"></a>Uwagi

[Token dostępu](/windows/win32/SecAuthZ/access-tokens) jest obiektem opisującym kontekst zabezpieczeń procesu lub wątku i jest przypisywany do każdego użytkownika zalogowanego na komputerze z systemem Windows NT lub Windows 2000. Te tokeny dostępu mogą być reprezentowane z `CAccessToken` klasą.

Czasami konieczne jest personifikowanie tokenów dostępu. Ta klasa jest udostępniana jako wygoda, ale nie wykonuje personifikacji tokenów dostępu. wykonuje tylko automatyczną rewersję do stanu niepersonifikowanego. Wynika to z faktu, że personifikacja dostępu do tokenu może być wykonywana na kilka różnych sposobów.

Aby zapoznać się z wprowadzeniem do modelu kontroli dostępu w systemie Windows, zobacz [Access Control](/windows/win32/SecAuthZ/access-control) w Windows SDK.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsecurity. h

## <a name="cautorevertimpersonationattach"></a><a name="attach"></a> CAutoRevertImpersonation:: Attach

Automatyzuje rewersję tokenu dostępu do personifikacji.

```cpp
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametry

*Osobisty token dostępu*<br/>
Adres obiektu [CAccessToken](../../atl/reference/caccesstoken-class.md) , który ma zostać przywrócony automatycznie

### <a name="remarks"></a>Uwagi

Ta metoda powinna być używana tylko wtedy, gdy obiekt [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) został utworzony za pomocą wskaźnika o wartości null `CAccessToken` lub jeśli [odłączenie](#detach) zostało wcześniej wywołane. W przypadku prostych przypadków nie trzeba używać tej metody.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="cautorevertimpersonation"></a> CAutoRevertImpersonation::CAutoRevertImpersonation

Konstruuje `CAutoRevertImpersonation` obiekt.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametry

*Osobisty token dostępu*<br/>
Adres obiektu [CAccessToken](../../atl/reference/caccesstoken-class.md) , który ma zostać przywrócony automatycznie.

### <a name="remarks"></a>Uwagi

Rzeczywista personifikacja tokenu dostępu powinna być wykonywana niezależnie od i najlepiej przed utworzeniem `CAutoRevertImpersonation` obiektu. Ta personifikacja zostanie przywrócona automatycznie, gdy `CAutoRevertImpersonation` obiekt wykracza poza zakres.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="dtor"></a> CAutoRevertImpersonation:: ~ CAutoRevertImpersonation

Niszczy obiekt i przywraca personifikację tokenu dostępu.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Uwagi

Przywraca wszystkie personifikacje, które są obecnie stosowane dla obiektu [CAccessToken](../../atl/reference/caccesstoken-class.md) w konstrukcji lub za pomocą metody [Attach](#attach) . Jeśli nie `CAccessToken` jest skojarzona, destruktor nie ma wpływu.

## <a name="cautorevertimpersonationdetach"></a><a name="detach"></a> CAutoRevertImpersonation::D etach

Anuluje rewersję automatycznej personifikacji.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Wartość zwracana

Adres poprzednio skojarzonego [CAccessToken](../../atl/reference/caccesstoken-class.md)lub wartość null, jeśli nie istniały żadne skojarzenie.

### <a name="remarks"></a>Uwagi

Wywołanie **odłączenia** uniemożliwia `CAutoRevertImpersonation` obiektowi odwracanie wszelkich personifikacji obecnie obowiązujących dla obiektu [CAccessToken](../../atl/reference/caccesstoken-class.md) skojarzonego z tym obiektem. `CAutoRevertImpersonation` można następnie zniszczyć bez efektu ani ponownie skojarzyć z tym samym lub innym `CAccessToken` obiektem przy użyciu [dołączania](#attach).

## <a name="cautorevertimpersonationgetaccesstoken"></a><a name="getaccesstoken"></a> CAutoRevertImpersonation::GetAccessToken

Pobiera token dostępu bieżący skojarzony z tym obiektem.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Wartość zwracana

Adres poprzednio skojarzonego [CAccessToken](../../atl/reference/caccesstoken-class.md)lub wartość null, jeśli nie istniały żadne skojarzenie.

### <a name="remarks"></a>Uwagi

Jeśli ta metoda jest wywoływana dla celów, które obejmują rewersję personifikacji `CAccessToken` obiektu, należy zamiast tego użyć metody [odłączania](#detach) .

## <a name="see-also"></a>Zobacz też

[Przykład ATLSecurity](../../overview/visual-cpp-samples.md)<br/>
[Tokeny dostępu](/windows/win32/SecAuthZ/access-tokens)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
