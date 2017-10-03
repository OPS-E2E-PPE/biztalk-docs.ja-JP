---
title: "メッセージを動的に変換する式を使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48387d97-9312-4df5-b614-727ea9035bf8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9d16c38fefb4e2732bd05f7c3489acaa8ca645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a>メッセージを動的に変換する式の使用方法
式を使用して、オーケストレーション内のメッセージを動的に変換できます。 XLANG 内から呼び出すことができる変換メソッドを公開する、**メッセージの割り当て**図形の内側、**メッセージの構築**図形です。 これは、同じときに呼び出される、**変換**図形は使用しますが、プログラムによって、オーケストレーション内で指定したマップを使用してメッセージを変換することができます。 これは、種類に関係なくメッセージ処理を行う場合に便利です。 たとえば、あるビジネス プロセスで、受け取った受信メッセージで指定されているパラメーターに基づいて一連のマップの中から受信メッセージの変換用のマップを選択する必要がある場合、式図形内で変換メソッドを使用すると、ビジネス プロセス全体を維持したままこれを実現することができます。  
  
## <a name="transforming-messages"></a>メッセージの変換  
 次のサンプル コードを使用してプログラムからのメッセージを変換することができます、**メッセージの割り当て**図形。  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 この例では、MyMapType は型の変数として宣言されて**System.Type**オーケストレーションでします。 MyMapName は、BizTalk プロジェクトで作成済みのマップの名前です。 別の BizTalk アセンブリにあるマップを参照する場合は、そのアセンブリを BizTalk プロジェクト内で参照する必要があります。 MyInputMsg は変換元のメッセージ、MyOutputMsg は変換先のメッセージです。 変換元メッセージの複数指定が可能なマップの場合は、次のサンプル コードを使用してメッセージを変換できます。  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  変換元メッセージが複数ある場合、それらのメッセージは、マップで指定されている入力メッセージ部分の番号の順に式に配置する必要があります。  
  
> [!IMPORTANT]
>  式図形内のメッセージを動的に変換する場合は、コンパイル済みのマップをキャッシュするためのキャッシュをユーザー コード内に記述し、そのキャッシュを式図形で使用してメッセージ変換の実行前にマップを取得することをお勧めします。 マップをキャッシュしないと、共通言語ランタイム (CLR) のメモリ使用量が大幅に増加する可能性があります。 動的マッピングを行うには .NET ランタイムでコード アクセス チェックを実行する必要があるため、変換ごとに .NET Evidence objec (.NET の Evidence オブジェクト) が Large Object Heap (ラージ オブジェクト ヒープ) に配置されることになり、オーケストレーションが完了するまで破棄されません。 したがって、このような種類の変換が同時に多数発生すると、メモリ使用量が大幅に増加する可能性があり、ひいてはメモリ不足の例外が発生する可能性もあります。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション図形](../core/orchestration-shapes.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)