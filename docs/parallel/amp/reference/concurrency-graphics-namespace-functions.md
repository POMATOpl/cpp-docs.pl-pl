---
title: "Funkcje przestrzeń nazw CONCURRENCY::Graphics | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::fast_math::copy_async
- amp_graphics/Concurrency::fast_math::copy
dev_langs: C++
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7338e634c7ce10b06e7b599494ed934942febe42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="concurrencygraphics-namespace-functions"></a>Funkcje przestrzeń nazw CONCURRENCY::Graphics
|||  
|-|-|  
|[Kopiuj](#copy)|[copy_async —](#copy_async)|  
  
##  <a name="copy"></a>copy — funkcja (Namespace Concurrency::graphics)  
 Kopiuje tekstury źródła do buforu docelowego lub kopiuje bufor źródłowy do bufor docelowy. Formularz ogólny tej funkcji jest `copy(src, dest)`.  
  
```  
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type>  
>  
void copy (
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size,  
    _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>void copy(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture,  
    void>::type 
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>Parametry  
 `_Copy_extent`  
 Zakres sekcji tekstury do skopiowania.  
  
 `_Dst`  
 Obiekt przeznaczony do skopiowania do.  
  
 `_Dst_byte_size`  
 Liczba bajtów w lokalizacji docelowej.  
  
 `_Dst_type`  
 Typ obiektu docelowego.  
  
 `_Dst_offset`  
 Przesunięcie do miejsca docelowego, od którego należy zacząć kopiowanie.  
  
 `InputIterator`  
 Typ wejściowy interator.  
  
 `OutputIterator`  
 Typ iteratora danych wyjściowych.  
  
 `_Src`  
 Aby obiekt do skopiowania.  
  
 `_Src_byte_size`  
 Liczba bajtów w źródle.  
  
 `_Src_type`  
 Typ obiektu źródłowego.  
  
 `_Src_offset`  
 Przesunięcie do źródło, z którego należy zacząć kopiowanie.  
  
 `first`  
 Iterator początek w kontenerze źródła.  
  
 `last`  
 Końcowy iteratora w kontenerze źródła.  
  
##  <a name="copy_async"></a>copy_async — funkcja (Namespace Concurrency::graphics)  
 Asynchronicznie kopiuje tekstury źródła do bufor docelowy, lub kopiuje bufor źródłowy do bufor docelowy, a następnie zwraca [completion_future](completion-future-class.md) obiekt, który może być obsługiwane. Nie można skopiować danych, gdy kod działa z akceleratora. Formularz ogólny tej funkcji jest `copy(src, dest)`.  
  
```  
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type &_Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>Parametry  
 `_Copy_extent`  
 Zakres sekcji tekstury do skopiowania.  
  
 `_Dst`  
 Obiekt przeznaczony do skopiowania do.  
  
 `_Dst_byte_size`  
 Liczba bajtów w lokalizacji docelowej.  
  
 `_Dst_type`  
 Typ obiektu docelowego.  
  
 `_Dst_offset`  
 Przesunięcie do miejsca docelowego, od którego należy zacząć kopiowanie.  
  
 `InputIterator`  
 Typ wejściowy interator.  
  
 `OutputIterator`  
 Typ iteratora danych wyjściowych.  
  
 `_Src`  
 Aby obiekt do skopiowania.  
  
 `_Src_byte_size`  
 Liczba bajtów w źródle.  
  
 `_Src_type`  
 Typ obiektu źródłowego.  
  
 `_Src_offset`  
 Przesunięcie do źródło, z którego należy zacząć kopiowanie.  
  
 `first`  
 Iterator początek w kontenerze źródła.  
  
 `last`  
 Końcowy iteratora w kontenerze źródła.  

## <a name="requirements"></a>Wymagania  
 **Nagłówek:** amp_graphics.h  
  
 **Namespace:** Concurrency::graphics 

## <a name="see-also"></a>Zobacz też  
 [Concurrency::graphics, przestrzeń nazw](concurrency-graphics-namespace.md)
