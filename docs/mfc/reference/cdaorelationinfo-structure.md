---
description: Dowiedz się więcej o strukturze CDaoRelationInfo —
title: CDaoRelationInfo — Struktura
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: efcc880d30dd18108005d9c4f265238b81551532
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222245"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo — Struktura

`CDaoRelationInfo`Struktura zawiera informacje o relacji zdefiniowanej między polami dwóch tabel w obiekcie [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) .

## <a name="syntax"></a>Składnia

```cpp
struct CDaoRelationInfo
{
    CDaoRelationInfo();                     // Constructor
    CString m_strName;                      // Primary
    CString m_strTable;                     // Primary
    CString m_strForeignTable;              // Primary
    long m_lAttributes;                     // Secondary
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary
    short m_nFields;                        // Secondary
    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu relacji. Aby uzyskać więcej informacji, zobacz temat "Nazwa właściwości" w pomocy DAO.

*m_strTable*<br/>
Nazwa główna tabeli w relacji.

*m_strForeignTable*<br/>
Nazywa tabelę obcą w relacji. Tabela obca jest tabelą używaną do przechowywania kluczy obcych. Ogólnie rzecz biorąc, można użyć tabeli obcej do ustanowienia lub wymuszenia integralności referencyjnej. Tabela obca zazwyczaj znajduje się na wielu stronach relacji jeden-do-wielu. Przykłady tabel obcych zawierają tabele zawierające kody dla województw amerykańskich lub kanadyjskich lub zamówień klientów.

*m_lAttributes*<br/>
Zawiera informacje o typie relacji. Wartość tego elementu członkowskiego może być dowolna z następujących:

- `dbRelationUnique` Relacja to jeden do jednego.

- `dbRelationDontEnforce` Relacja nie jest wymuszana (bez integralności referencyjnej).

- `dbRelationInherited` Relacja istnieje w nieaktualnej bazie danych, która zawiera dwie dołączone tabele.

- `dbRelationLeft` Relacja to lewe sprzężenie. Lewe sprzężenie zewnętrzne zawiera wszystkie rekordy z pierwszej (lewej strony) dwóch tabel, nawet jeśli nie ma pasujących wartości dla rekordów w drugiej tabeli (po prawej stronie).

- `dbRelationRight` Relacja jest odpowiednim sprzężeniem. Prawe sprzężenie zewnętrzne zawiera wszystkie rekordy z drugiej strony (po prawej stronie) dwóch tabel, nawet jeśli nie ma pasujących wartości dla rekordów w pierwszej tabeli (po lewej stronie).

- `dbRelationUpdateCascade` Aktualizacje będą kaskadowo.

- `dbRelationDeleteCascade` Usunięcia zostaną kaskadowo.

*m_pFieldInfos*<br/>
Wskaźnik do tablicy struktur [CDaoRelationFieldInfo —](../../mfc/reference/cdaorelationfieldinfo-structure.md) . Tablica zawiera jeden obiekt dla każdego pola w relacji. `m_nFields`Element członkowski danych daje liczbę elementów tablicy.

*m_nFields*<br/>
Liczba `CDaoRelationFieldInfo` obiektów w `m_pFieldInfos` elemencie członkowskim danych.

## <a name="remarks"></a>Uwagi

Odwołania do podstawowych i pomocniczych powyżej wskazują, jak informacje są zwracane przez funkcję składową [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) w klasie `CDaoDatabase` .

Obiekty relacji nie są reprezentowane przez klasę MFC. Zamiast tego obiekt DAO, który jest obiektem MFC `CDaoDatabase` klasy, przechowuje kolekcję obiektów relacji: `CDaoDatabase` dostarcza funkcje członkowskie do uzyskiwania dostępu do niektórych poszczególnych elementów informacji o relacji lub można uzyskać do nich dostęp jednocześnie przy użyciu `CDaoRelationInfo` obiektu przez wywołanie `GetRelationInfo` funkcji członkowskiej zawierającego obiekt bazy danych.

Informacje pobierane przez funkcję członkowską [CDaoDatabase:: GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) są przechowywane w `CDaoRelationInfo` strukturze. `CDaoRelationInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoRelationInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[CDaoRelationFieldInfo —, struktura](../../mfc/reference/cdaorelationfieldinfo-structure.md)
