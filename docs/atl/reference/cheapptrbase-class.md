---
description: 'Dowiedz się więcej na temat: Klasa CHeapPtrBase'
title: Klasa CHeapPtrBase
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: 6186f68066f4c159c16c458f9f00725478aa98a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141638"
---
# <a name="cheapptrbase-class"></a>Klasa CHeapPtrBase

Ta klasa stanowi podstawę dla kilku klas wskaźników sterty inteligentnej.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ obiektu, który ma być przechowywany na stercie.

*Alokator*<br/>
Klasa alokacji pamięci do użycia. Domyślnie procedury CRT są używane do przydzielania i wolnej pamięci.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Wywołaj tę metodę, aby przydzielić pamięć.|
|[CHeapPtrBase:: Attach](#attach)|Wywołaj tę metodę, aby przejąć na własność istniejący wskaźnik.|
|[CHeapPtrBase::D etach](#detach)|Wywołaj tę metodę, aby zwolnić własność wskaźnika.|
|[CHeapPtrBase:: Free](#free)|Wywołaj tę metodę, aby usunąć obiekt wskazywany przez `CHeapPtrBase` .|
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Wywołaj tę metodę, aby ponownie przydzielić pamięć.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHeapPtrBase:: operator T *](#operator_t_star)|Operator rzutowania.|
|[CHeapPtrBase:: operator &](#operator_amp)|Operator &.|
|[CHeapPtrBase:: operator->](#operator_ptr)|Operator wskaźnika do składowej.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CHeapPtrBase:: m_pData](#m_pdata)|Zmienna elementu członkowskiego danych wskaźnika.|

## <a name="remarks"></a>Uwagi

Ta klasa stanowi podstawę dla kilku klas wskaźników sterty inteligentnej. Klasy pochodne, na przykład [CHeapPtr](../../atl/reference/cheapptr-class.md) i [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), Dodaj własne konstruktory i operatory. Zapoznaj się z tymi klasami, aby poznać Przykłady implementacji.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcore. h

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a> CHeapPtrBase::AllocateBytes

Wywołaj tę metodę, aby przydzielić pamięć.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametry

*nBytes*<br/>
Liczba bajtów pamięci do przydzielenia.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli pamięć została przypisana pomyślnie, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

W kompilacjach debugowania wystąpi błąd potwierdzenia, jeśli zmienna członkowska [CHeapPtrBase:: m_pData](#m_pdata) aktualnie wskazuje istniejącą wartość; oznacza to, że nie jest równa NULL.

## <a name="cheapptrbaseattach"></a><a name="attach"></a> CHeapPtrBase:: Attach

Wywołaj tę metodę, aby przejąć na własność istniejący wskaźnik.

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>Parametry

*pData*<br/>
Obiekt przejdzie na `CHeapPtrBase` własność tego wskaźnika.

### <a name="remarks"></a>Uwagi

Gdy `CHeapPtrBase` obiekt przejmuje własność wskaźnika, automatycznie usunie wskaźnik i wszystkie przydzieloną dane, gdy wykracza poza zakres.

W kompilacjach debugowania wystąpi błąd potwierdzenia, jeśli zmienna członkowska [CHeapPtrBase:: m_pData](#m_pdata) aktualnie wskazuje istniejącą wartość; oznacza to, że nie jest równa NULL.

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a> CHeapPtrBase:: ~ CHeapPtrBase

Destruktor.

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby.

## <a name="cheapptrbasedetach"></a><a name="detach"></a> CHeapPtrBase::D etach

Wywołaj tę metodę, aby zwolnić własność wskaźnika.

```
T* Detach() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca kopię wskaźnika.

### <a name="remarks"></a>Uwagi

Zwalnia własność wskaźnika, ustawia zmienną członkowską [CHeapPtrBase:: m_pData](#m_pdata) na null i zwraca kopię wskaźnika.

## <a name="cheapptrbasefree"></a><a name="free"></a> CHeapPtrBase:: Free

Wywołaj tę metodę, aby usunąć obiekt wskazywany przez `CHeapPtrBase` .

```cpp
void Free() throw();
```

### <a name="remarks"></a>Uwagi

Obiekt wskazywany przez `CHeapPtrBase` jest zwolniony, a zmienna członkowska [CHeapPtrBase:: m_pData](#m_pdata) ma wartość null.

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a> CHeapPtrBase:: m_pData

Zmienna elementu członkowskiego danych wskaźnika.

```
T* m_pData;
```

### <a name="remarks"></a>Uwagi

Ta zmienna członkowska zawiera informacje o wskaźniku.

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a> CHeapPtrBase:: operator &amp;

Operator &.

```
T** operator&() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca adres obiektu wskazywanego przez `CHeapPtrBase` obiekt.

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a> CHeapPtrBase:: operator-&gt;

Operator wskaźnika do składowej.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość zmiennej składowej [CHeapPtrBase:: m_pData](#m_pdata) .

### <a name="remarks"></a>Uwagi

Użyj tego operatora, aby wywołać metodę w klasie wskazywanej przez `CHeapPtrBase` obiekt. W kompilacjach debugowania wystąpi błąd potwierdzenia, jeśli `CHeapPtrBase` punkty mają wartość null.

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a> CHeapPtrBase:: operator T *

Operator rzutowania.

```
operator T*() const throw();
```

### <a name="remarks"></a>Uwagi

Zwraca [CHeapPtrBase:: m_pData](#m_pdata).

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a> CHeapPtrBase::ReallocateBytes

Wywołaj tę metodę, aby ponownie przydzielić pamięć.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametry

*nBytes*<br/>
Nowa ilość pamięci do przydzielenia w bajtach.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli pamięć została przypisana pomyślnie, w przeciwnym razie false.

## <a name="see-also"></a>Zobacz też

[Klasa CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Klasa CComHeapPtr](../../atl/reference/ccomheapptr-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
