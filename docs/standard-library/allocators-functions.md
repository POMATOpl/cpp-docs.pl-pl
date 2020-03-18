---
title: '&lt;przydzielania&gt; makra'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::ALLOCATOR_DECL
- allocators/std::CACHE_CHUNKLIST
- allocators/std::CACHE_FREELIST
- allocators/std::CACHE_SUBALLOC
- allocators/std::SYNC_DEFAULT
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
helpviewer_keywords:
- std::ALLOCATOR_DECL [C++]
- std::CACHE_CHUNKLIST [C++]
- std::CACHE_FREELIST [C++]
- std::CACHE_SUBALLOC [C++]
- std::SYNC_DEFAULT [C++]
ms.openlocfilehash: 5355661e370daf8826541c036f7301e5c25788d7
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416929"
---
# <a name="ltallocatorsgt-macros"></a>&lt;przydzielania&gt; makra

||||
|-|-|-|
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|

## <a name="allocator_decl"></a>ALLOCATOR_DECL

Daje szablon klasy alokatora.

```cpp
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```

### <a name="remarks"></a>Uwagi

Makro daje definicję szablonu `template <class Type> class name {.....}` i specjalizację `template <> class name<void> {.....}`, które razem definiują szablon klasy alokatora, który korzysta z filtru synchronizacji `sync` i pamięci podręcznej typu `cache`.

W przypadku kompilatorów, które mogą skompilować ponownie powiązanie, wynikowa definicja szablonu wygląda następująco:

```cpp
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };
```

W przypadku kompilatorów, które nie mogą skompilować ponownie powiązania, wynikowa definicja szablonu wygląda następująco:

```cpp
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```

## <a name="cache_chunklist"></a>CACHE_CHUNKLIST

Daje `stdext::allocators::cache_chunklist<sizeof(Type)>`.

```cpp
#define CACHE_CHUNKLIST <cache_class>
```

### <a name="remarks"></a>Uwagi

## <a name="cache_freelist"></a>CACHE_FREELIST

Daje `stdext::allocators::cache_freelist<sizeof(Type), max>`.

```cpp
#define CACHE_FREELIST(max) <cache_class>
```

### <a name="remarks"></a>Uwagi

## <a name="cache_suballoc"></a>CACHE_SUBALLOC

Daje `stdext::allocators::cache_suballoc<sizeof(Type)>`.

```cpp
#define CACHE_SUBALLOC <cache_class>
```

### <a name="remarks"></a>Uwagi

## <a name="sync_default"></a>SYNC_DEFAULT

Zwraca filtr synchronizacji.

```cpp
#define SYNC_DEFAULT <sync_template>
```

### <a name="remarks"></a>Uwagi

Jeśli kompilator obsługuje Kompilowanie aplikacji wielowątkowych i wielowątkowych, w przypadku aplikacji jednowątkowych makro daje `stdext::allocators::sync_none`; we wszystkich innych przypadkach daje `stdext::allocators::sync_shared`.

## <a name="see-also"></a>Zobacz też

[\<przydzielania >](../standard-library/allocators-header.md)
