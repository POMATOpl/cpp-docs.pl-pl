---
description: 'Dowiedz się więcej na temat: __svm_skinit'
title: __svm_skinit
ms.date: 09/02/2019
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: dd35566664a6bff4a57ea986fc99ffcd731c79e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206269"
---
# <a name="__svm_skinit"></a>__svm_skinit

**Specyficzne dla firmy Microsoft**

Inicjuje ładowanie bezpiecznego oprogramowania, takiego jak monitor maszyny wirtualnej.

## <a name="syntax"></a>Składnia

```C
void __svm_skinit(
   int block_address
);
```

### <a name="parameters"></a>Parametry

*block_address*\
32-bitowy adres fizyczny 64-bitowego bloku modułu ładującego.

## <a name="remarks"></a>Uwagi

`__svm_skinit`Funkcja jest równoważna z `SKINIT` instrukcją maszyny. Ta funkcja jest częścią systemu zabezpieczeń, który używa procesora i moduł TPM (TPM) do sprawdzania i ładowania zaufanego oprogramowania, zwanego *jądrem zabezpieczeń* (SK). Przykładem jądra zabezpieczeń jest monitor maszyny wirtualnej. System zabezpieczeń weryfikuje składniki programu załadowane podczas procesu inicjowania. Chroni składniki przed naruszeniem przez przerwania, dostęp do urządzenia lub inny program, jeśli komputer jest wieloprocesorowy.

*Block_address* parametr określa adres fizyczny bloku 64 KB pamięci o nazwie *bezpieczny blok modułu ładującego (moduł* równoważenia obciążenia). Moduł równoważenia obciążenia zawiera program o nazwie *bezpiecznego modułu ładującego*. Ustanawia środowisko operacyjne dla komputera, a następnie ładuje jądro zabezpieczeń.

Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, wyszukaj frazę "rozgłośnuje programista architektury AMD64 2: Programowanie systemu" w witrynie [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__svm_skinit`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
