---
description: 'Dowiedz się więcej o: nieoczekiwany (CRT)'
title: nieoczekiwany (CRT)
ms.date: 11/04/2016
api_name:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 73c632c4dd5bfedbb1c3724e60786b348f77f0be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186639"
---
# <a name="unexpected-crt"></a>nieoczekiwany (CRT)

Wywołania **zakończone** lub funkcja jest określana za pomocą **set_unexpected**.

## <a name="syntax"></a>Składnia

```C
void unexpected( void );
```

## <a name="remarks"></a>Uwagi

**Nieoczekiwana** procedura nie jest używana z bieżącą implementacją obsługi wyjątków C++. **nieoczekiwane** wywołania **kończą** się domyślnie. To zachowanie domyślne można zmienić, pisząc funkcję niestandardowej zakończenia i wywołując **set_unexpected** z nazwą funkcji jako argumentem. **nieoczekiwane** wywołania ostatnią funkcję podaną jako argument **set_unexpected**.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**oczekiwan**|\<eh.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Procedury obsługi wyjątków](../../c-runtime-library/exception-handling-routines.md)<br/>
[przerwij](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[kończyć](terminate-crt.md)<br/>
