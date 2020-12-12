---
description: 'Dowiedz się więcej na temat: SEGMENT'
title: SEGMENT
ms.date: 12/16/2019
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: aeb99080043cbfb13fdec1c2e82df3a6d16b306d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97125596"
---
# <a name="segment"></a>SEGMENT

Definiuje segment *programu o nazwie* z atrybutami segmentu

## <a name="syntax"></a>Składnia

>  **segment** nazw ⟦**ReadOnly**⟧ ⟦*align*⟧ ⟦*Połącz*⟧ ⟦*Użyj*⟧ ⟦*cechy*⟧ **alias (**_String_**)** ⟦__"__*Class*__"__⟧ \
> *zatwierdzeni*\
>  **koniec** nazwy

#### <a name="parameters"></a>Parametry

*dostosowania*\
Zakres adresów pamięci, z którego można wybrać adres początkowy segmentu. Typ wyrównania może mieć jedną z następujących wartości:

|Typ wyrównania|Adres początkowy|
|----------------|----------------------|
|**BYTE**|Adres następnego dostępnego bajtu.|
|**SŁOW**|Adres następnego dostępnego wyrazu (2 bajty na słowo).|
|**DWORD**|Następny dostępny podwójny adres wyrazu (4 bajty na podwójny wyraz).|
|**KONTROL**|Adres następnego dostępnego akapitu (16 bajtów na akapit).|
|**STRONIC**|Następny dostępny adres strony (256 bajtów na stronę).|
|**Wyrównaj**(*n*)|Następny dostępny *n* adres bajtowy. Aby uzyskać więcej informacji, zobacz sekcję Uwagi.|

Jeśli ten parametr nie jest określony, **para** jest używana domyślnie.

*Połącz* (tylko 32-bitowe MASM) \
**Publiczne**, **stos**, **Common**, **pamięć**, **pod**<em>adresem</em>, **prywatny**

*Użyj* (32-bitowy MASM tylko) \
**USE16**, **USE32**, **Flat**

*elementy*\
**Informacje**, **Odczyt**, **zapis**, **wykonywanie**, **udostępnianie**, **nopage**, **nocache** i **DISCARD**

Są one obsługiwane tylko w przypadku formatu COFF i odpowiadają charakterystykom sekcji COFF o podobnej nazwie (na przykład **współdzielona** odnosi się do IMAGE_SCN_MEM_SHARED). Odczyt ustawia flagę IMAGE_SCN_MEM_READ. Przestarzała flaga READONLY spowodowała, że sekcja czyści flagę IMG_SCN_MEM_WRITE. Jeśli są ustawione jakiekolwiek *Właściwości* , właściwości domyślne nie są używane i są stosowane tylko flagi określone przez programistę.

_parametry_\
Ten ciąg jest używany jako nazwa sekcji w emitowanym obiekcie COFF.  Tworzy wiele sekcji o tej samej nazwie zewnętrznej z odrębnymi nazwami segmentów MASM.

Nieobsługiwane w przypadku **/OMF**.

*określonej*\
Określa, jak segmenty mają być połączone i uporządkowane w zmontowanym pliku. Typowe wartości to, `'DATA'` , `'CODE'` , `'CONST'` i `'STACK'`

## <a name="remarks"></a>Uwagi

Dla `ALIGN(n)` , *n* może być dowolną potęgą od 1 do 8192; nie jest obsługiwana w przypadku **/OMF**.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
