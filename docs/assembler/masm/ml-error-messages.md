---
description: 'Dowiedz się więcej o: komunikatach o błędach ML'
title: Komunikaty o błędach ML
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: 08f9a3ccd1bfe79195bf3ba9acf5b5347cc35a1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129704"
---
# <a name="ml-error-messages"></a>Komunikaty o błędach ML

Komunikaty o błędach generowane przez składniki MASM wchodzą w skład trzech kategorii:

- **Błędy krytyczne.** Wskazują one na poważny problem, który uniemożliwia wykonanie normalnego procesu przez narzędzie.

- **Błędy niekrytyczne.** Narzędzie może zakończyć proces. Jeśli tak się stanie, jego wynik nie będzie taki sam.

- **Ostrzeżeni.** Te komunikaty wskazują warunki, które mogą uniemożliwić uzyskanie żądanych wyników.

Wszystkie komunikaty o błędach przyjmują następującą formę:

> *Narzędzie*: *filename* (*line*): {*Error_type*} (*kod*): *Message_text*

gdzie:

*Spuninst*\
Program, który wysłał komunikat o błędzie.

*Nazwa pliku*\
Plik zawierający warunek generowania błędu.

*Liniow*\
Przybliżony wiersz, w którym występuje warunek błędu.

*Error_type*\
Błąd krytyczny, błąd lub ostrzeżenie.

*Kodu*\
Unikatowy kod błędu 5-lub 6-cyfrowy.

*Message_text*\
Krótki i ogólny opis warunku błędu.

## <a name="see-also"></a>Zobacz też

[Dokumentacja asemblera programu Microsoft Macro](microsoft-macro-assembler-reference.md)
