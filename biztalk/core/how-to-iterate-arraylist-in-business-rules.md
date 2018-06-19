---
title: ビジネス ルールの ArrayList を反復処理する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 9010907cfe9fb6d79a8d9fcead533376b014640e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970792"
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a>ビジネス ルールの ArrayList を反復処理する方法
このセクションでは、メンバーを反復処理する、 **ArrayList**でビジネス ルール。  
  
 あると、 **ArrayList**の一連の**MyClass**オブジェクト。 ビジネス ルールは、次のようになります。  
  
## <a name="rule-a"></a>ルール A  
 IF 1==1  
  
 THEN Assert (ArrayList.GetEnumerator)  
  
 **IEnumerator**ために、型が作業メモリにアサートされるルールの条件 (1 = = 1) 常に true に評価します。  
  
## <a name="rule-b"></a>ルール B  
 IF IEnumerator.MoveNext  
  
 THEN    Assert (IEnumerator.get_Current)  
  
 Update (IEnumerator)  
  
 反復処理ルールとして、 **ArrayList**、各**MyClass**コレクション内のオブジェクトが作業メモリにアサートします。  
  
## <a name="rule-c"></a>ルール C  
 IF MyClass.MyProperty==2  
  
 \<操作を行います.\>  
  
 オブジェクトのプロパティの値が条件に一致する場合に、このルールは、アクションを実行します。