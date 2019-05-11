---
title: メッセージに動的に変換する式を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48387d97-9312-4df5-b614-727ea9035bf8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084d8144aae37f3036d17f574a7fb663755e0b26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333464"
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a>メッセージに動的に変換する式を使用する方法
オーケストレーションでメッセージを動的に変換する式を使用できます。 XLANG 内から呼び出せる変換メソッドを公開する、**メッセージの割り当て**図形の内部を**メッセージの構築**図形。 これは、同じメソッド時に呼び出される、**変換**図形が使用されますが、プログラムによって、オーケストレーション内で指定したマップを使用してメッセージを変換することができます。 これは、機能は、型に依存しないメッセージの処理を実行すると便利です。 たとえば、受信した受信メッセージによって提供されるパラメーターに基づく受信メッセージを変換する一連のマップから選択する必要があるビジネス プロセスがあれば、これを行う中に、式図形で変換メソッドを使用して、ビジネス プロセス全体をそのまま維持します。  
  
## <a name="transforming-messages"></a>メッセージの変換  
 次のサンプル コードを使用してプログラムでメッセージを変換することができます、**メッセージの割り当て**図形。  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 この例では、MyMapType は型の変数として宣言されて**System.Type**オーケストレーションします。 MyMapName は、BizTalk プロジェクトで既に作成されているマップの名前です。 別の BizTalk アセンブリ内にあるマップを参照する場合は、BizTalk プロジェクトでそのアセンブリを参照する必要があります。 MyInputMsg は送信元メッセージ、MyOutputMsg は変換先のメッセージ。 マップが複数のソースのメッセージを受け取る場合は、メッセージを変換する、次のサンプル コードを使用できます。  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  を複数のソースのメッセージがある場合は、マップに示されている入力メッセージ部分の番号に式の順序で配置する必要があります。  
  
> [!IMPORTANT]
>  動的式図形内のメッセージを変換する場合は、ユーザー コードのコンパイル済みのマップをキャッシュのキャッシュを記述し、式図形内のキャッシュを使用して、メッセージの変換を実行する前に、マップを取得することを勧めします。 マップをキャッシュしない場合は、共通言語ランタイム (CLR) 大幅に増大するメモリを確認できます。 動的マッピングは、.NET ランタイムが、オーケストレーションが完了するまでの各変換の大きなオブジェクト ヒープに配置されている .NET の証拠オブジェクトとこのオブジェクトとその結果が破棄されませんが、コード アクセス チェックを実行することが必要です。 そのため、これらの種類に同時に発生する変換の多くがある場合に、メモリ使用量が大幅に上昇、メモリ不足の例外にもつながりますを参照してください可能性があります。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション図形](../core/orchestration-shapes.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)