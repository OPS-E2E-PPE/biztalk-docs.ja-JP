---
title: "変換 Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192db4b03f80674f2eb90be2255a8682454bde2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="conversion-functoids"></a>変換 Functoid

## <a name="overview"></a>概要
**変換**functoid を使用して番号と、ASCII の同等の間で変換して、基数 8 ベースの 10 個の番号に変換および 16 進の基本します。  
  
 すべての変換 Functoid は単一の入力パラメーターを使用します。  
  
> [!NOTE]
>  基になる型システムでの変更により、**変換**このバージョンの BizTalk マッパーの functoid は、以前のバージョンで作成されるものよりも若干異なる結果を生成します。 たとえば、以前のバージョンの BizTalk マッパー、入力値-20 を**16 進**0xFFEC の出力に functoid が発生しました。 今回のバージョンでは、同じ入力値 -20 で 0xFFFFFFEC という出力になります。  

## <a name="available-functoids"></a>使用可能な functoid  
 **変換**functoid には。 

* 値の ASCII 文字化
* 文字の ASCII 値算出
* 16 進数
* 8 進変換

これらの functoid が説明されている[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 

## <a name="see-also"></a>参照  
 [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
