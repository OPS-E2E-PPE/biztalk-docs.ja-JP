---
title: ビジネス ルールの ArrayList の繰り返し処理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9753ce1208312ade51950cd36a1df4210d763268
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384883"
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a>ビジネス ルールの ArrayList の繰り返し処理する方法
このセクションがのメンバーを反復処理の例では、 **ArrayList**でビジネス ルール。  
  
 あると、 **ArrayList**のコレクションを持つ**MyClass**オブジェクト。 ビジネス ルールは、次のようになります。  
  
## <a name="rule-a"></a>ルール A  
 場合 1 1 = =  
  
 (ArrayList.GetEnumerator) ことをアサートします。  
  
 **IEnumerator**のため、型が、作業メモリにアサートされるルールの条件 (1 1 = =) 常に true に評価されます。  
  
## <a name="rule-b"></a>ルール B  
 IF IEnumerator.MoveNext  
  
 THEN    Assert (IEnumerator.get_Current)  
  
 更新プログラム (IEnumerator)  
  
 反復処理ルールとして、 **ArrayList**、それぞれ**MyClass**コレクション内のオブジェクトが作業メモリにアサートされます。  
  
## <a name="rule-c"></a>ルール C  
 IF MyClass.MyProperty==2  
  
 \<処理を実行しています.\>  
  
 このルールは、オブジェクトのプロパティの値が条件に一致したときにアクションを実行します。