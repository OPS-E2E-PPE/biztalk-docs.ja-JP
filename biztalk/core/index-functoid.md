---
title: Functoid のインデックス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Index functoids, about Index functoids
- Index functoids
ms.assetid: 0c8ba427-881c-4b1f-92b9-61992d2a29df
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 826f1464b78027faf268ddce7dfea97271ff8698
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332090"
---
# <a name="index-functoid"></a>インデックス Functoid
**インデックス**functoid では、一連のレコードの特定のレコードから情報を選択することができます。 各**インデックス**functoid は、1 つのフィールドから情報を収集します。  
  
 特定のレコードでは、入力ファイルで何度も通常発生します。 たとえば、天気予報で、 **DailySummary**要素が何度も発生する可能性があります。 **DailySummary**要素には、温度、大気圧、風速の属性が含まれます。 次のコードは、気象レポートの例です。  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 基になるスキーマで、 **Max Occurs**プロパティを**DailySummary**レコードを定期的またはループ レコードを示すバインド解除済みに設定します。 BizTalk マッパーは、このレコードをループとしてコンパイルします。  
  
 最初の 2 つの気象情報を収集したいとします**DailySummary**天気予報のレコード。 BizTalk マッパーで各属性を**DailySummary**に着信、送信元スキーマのレコードを接続することができます、**インデックス**functoid。 各**インデックス**functoid を指定できます、 **DailySummary**レコードから情報を描画する: 最初または 2 回目です。 **インデックス**functoid を送信先スキーマの適切なフィールドに接続できます。  
  
 次に示します**インデックス**functoid がこの方法で使用します。  
  
 ![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")  
インデックス Functoid の例  
  
 3 つの上にある設定を最初の日の概要情報を取得する**インデックス**functoid がある、インデックスの値を 1 に設定します。 下に 3 つの設定、2 日目の概要情報を取得する**インデックス**functoid がある、インデックスの値を 2 に設定します。  
  
 **インデックス**functoid を使用して、**構成\<Functoid\> Functoid**  ダイアログ ボックスの入力パラメーターを設定します。 最初の入力パラメーターは、送信元スキーマのループ レコード内のフィールドを識別します。 2 番目以降の入力パラメーターは、特定のレコードを指定します。 入れ子になった繰り返し構造内のレコードを選択する複数のインデックス値を指定することができます。 最も内側の構造のインデックス値は、2 番目のパラメーターです。 [次へ] の最も外側の構造のインデックス値は、3 番目のパラメーターしには。 たとえば、ものとします前に、 **DailySummary**内だったレコードの**WeeklyData**レコード。 取得する、**圧力**最初から**DailySummary** 、2 番目の**WeeklyData**、2 番目のパラメーターは 1 になり、3 番目のパラメーター 2 になります。  
  
 この例では通知、**圧力**フィールドが繰り返されない。 インデックスはオフであり、フィールドが繰り返す場合-カウントで開始、**圧力**フィールド、なく**の日次サマリー**。  
  
> [!NOTE]
>  インデックス シーケンスの入力パラメーターは定数では通常、送信元スキーマ ノードからのリンクを使用することができます。 このリンク最初の入力パラメーターの親ではないループ レコードからの場合、インデックス シーケンスの入力値、入力インスタンス メッセージ内のノードの最初のインスタンスに由来します。  
  
> [!NOTE]
>  インデックス シーケンスの入力の値は常にソース ドキュメント内の現在のコンテキストに関連します。  
  
> [!IMPORTANT]
>  **インデックス**functoid が、フィールド レベルからのルート ノード直下の第 1 レベルの親ノードがある多くのインデックス値が必要です。 たとえば、複数の気象レポート インスタンス メッセージで 2 つのインデックス値が必要です。 1 つの気象レポート インスタンス メッセージで、1 つだけのインデックス値が必要です。 必要な数のインデックス値の設定に失敗した、**インデックス**functoid の最初の入力パラメーターに一致する送信元インスタンス メッセージの最初のノードに基づいて出力を作成し、**インデックス**functoid。  
  
## <a name="see-also"></a>参照  
 [マップにインデックス Functoid を追加する方法](../core/how-to-add-index-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)