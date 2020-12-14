---
description: 'Dowiedz się więcej na temat: _amsg_exit'
title: _amsg_exit
ms.date: 11/04/2016
api_name:
- _amsg_exit
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: d00283f3222a217db8337129f66b377f7c0d494e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211404"
---
# <a name="_amsg_exit"></a>_amsg_exit

Emituje określony komunikat o błędzie środowiska uruchomieniowego, a następnie kończy działanie aplikacji z kodem błędu 255.

## <a name="syntax"></a>Składnia

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>Parametry

*rterrnum*<br/>
Numer identyfikacyjny komunikatu o błędzie środowiska uruchomieniowego zdefiniowanego przez system.

## <a name="remarks"></a>Uwagi

Ta funkcja emituje komunikat o błędzie środowiska uruchomieniowego do **stderr** dla aplikacji konsolowych lub wyświetla komunikat w oknie komunikatu dla aplikacji systemu Windows. W trybie debugowania można wybrać opcję wywołania debugera przed wyjściem.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|_amsg_exit|wewnętrzny. h|
