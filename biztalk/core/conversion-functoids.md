---
title: 変換 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b042428f3a67227db6fb53966149458bc279926
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390247"
---
# <a name="conversion-functoids"></a>変換 Functoid

## <a name="overview"></a>概要
**変換**番号と、ASCII 値の間で変換して、基数 8 を 10 進数に変換し、16 進の基本 functoid を使用します。  
  
 すべての変換 functoid は、1 つの入力パラメーターを受け取ります。  
  
> [!NOTE]
>  基になる型システムでの変更により、**変換**このバージョンの BizTalk マッパーの functoid は、以前のバージョンで生成されたものよりもわずかに異なる結果を生成します。 たとえば、以前のバージョンの BizTalk マッパーの入力値-20 でに、 **16 進数**functoid 0xFFEC の出力が発生しました。 このバージョンでは、同じ入力値-20 0xFFFFFFEC の出力になります。  

## <a name="available-functoids"></a>使用可能な functoid  
 **変換**functoid には。 

* 値の ASCII 文字
* ASCII 文字
* 16 進数
* 8 進数

これらの functoid が説明されている[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 

## <a name="see-also"></a>参照  
 [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
