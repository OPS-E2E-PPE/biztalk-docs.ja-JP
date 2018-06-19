---
title: Functoid のインデックスを作成 |Microsoft ドキュメント
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
ms.openlocfilehash: a22881e7694fee872b7820b8b99157ef2cf20170
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972584"
---
# <a name="index-functoid"></a>インデックス Functoid
**インデックス**functoid では、一連のレコードの特定のレコードから情報を選択することができます。 各**インデックス**functoid が 1 つのフィールドから情報を収集します。  
  
 一般的に、1 つの入力ファイルには、特定のレコードが複数含まれます。 たとえば、気象レポートで、 **DailySummary**要素が何度も発生する可能性があります。 **DailySummary**要素は、気温、大気圧、風速の属性を含めることがあります。 次のコードは、気象レポートの例です。  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 基になるスキーマで、 **Max Occurs**プロパティを**DailySummary**レコードを定期的またはループ レコードを示すためにバインド解除済みに設定します。 BizTalk マッパーでは、このレコードはループとしてコンパイルされます。  
  
 最初の 2 つの気象情報を収集する場合を考えます**DailySummary**天気予報のレコードです。 BizTalk マッパーで各属性、 **DailySummary**に、入力方向の送信元スキーマのレコードを接続することができます、**インデックス**functoid です。 各**インデックス**functoid を指定できます、 **DailySummary**レコードから情報を描画する: 最初または 2 番目です。 **インデックス**functoid を送信先スキーマの適切なフィールドに接続できます。  
  
 次に示します**インデックス**functoid をこのように使用します。  
  
 ![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")  
インデックス Functoid の例  
  
 最初の日付の日単位の概要情報を取得するには、上の設定の 3 つ**インデックス**functoid がある、インデックスの値を 1 に設定します。 2 日目の毎日の概要情報を取得するには、下に 3 つの設定**インデックス**functoid がある、インデックスの値を 2 に設定します。  
  
 **インデックス**functoid を使用して、**構成\<Functoid\> Functoid**ダイアログ ボックスを入力パラメーターを設定します。 最初の入力パラメーターが、送信元スキーマのループ レコード内のフィールドを示します。 2 番目以降の入力パラメーターでは、特定のレコードを指定します。 入れ子になった繰り返し構造内のレコードを選択するために、複数のインデックス値を指定できます。 最も内側の構造のインデックス値が 2 番目のパラメーターです。 内側から 2 つ目の構造のインデックス値が 3 番目のパラメーターで、以降も同様です。 たとえばを前述の**DailySummary**内だったレコードの**WeeklyData**レコード。 取得する、**圧力**最初から**DailySummary** 、2 番目の**WeeklyData**、2 番目のパラメーター 1 になり、3 番目のパラメーターが 2 になります。  
  
 この例では通知、**圧力**フィールドが繰り返されない。 インデックスが無効になる場合は、フィールドが繰り返すには、— カウントで開始、**圧力**フィールドではなく、**日ごとのサマリー**です。  
  
> [!NOTE]
>  一般的にインデックス シーケンスの入力パラメーターは定数ですが、送信元スキーマのノードからのリンクを使用することもできます。 このリンクが 1 番目の入力パラメーターの親ではないループ レコードからのリンクの場合、インデックス シーケンスの入力値は、入力インスタンス メッセージのノードの最初のインスタンスから取得されます。  
  
> [!NOTE]
>  通常、インデックス シーケンスの入力値は、送信元ドキュメントの現在のコンテキストに関するものです。  
  
> [!IMPORTANT]
>  **インデックス**functoid が、フィールド レベルからルート ノード直下の第 1 レベルの親ノードがある多くのインデックス値が必要です。 たとえば、複数の気象レポート インスタンス メッセージでは、2 つのインデックス値が必要です。 単一の気象レポート インスタンス メッセージでは、必要なインデックス値は 1 つだけです。 必要な数のインデックス値の設定に失敗した、**インデックス**functoid の最初の入力パラメーターに一致する送信元インスタンス メッセージの最初のノードに基づいて出力を作成する、**インデックス**functoid です。  
  
## <a name="see-also"></a>参照  
 [インデックス Functoid をマップに追加する方法](../core/how-to-add-index-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)