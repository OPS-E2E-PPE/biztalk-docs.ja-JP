---
title: ループ アクティビティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cf2b768deca72b281bc189431b01f5e63a4887
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005073"
---
# <a name="looping-activities"></a>ループ アクティビティ
ループ アクティビティとは、オーケストレーション内でループ処理されるアクションのことです。 オーケストレーション内でループ処理されるアクションからイベントをキャプチャできます。 この操作を行うには、アクティビティをもう 1 つ作成し、ループ内の新しいアクティビティ マイルストーンとデータのすべてをマップします。 ループ内でのデータ処理は、スケジュールされた実行ごとに 1 回以上行われるので、この操作が必要です。 次の図は、この状況の例を示しています。  
  
 ![](../core/media/handlingloops2.gif "handlingloops2")  
  
 ループ内で処理される複数の行項目を含む購買発注書がある場合に、図に示すようにのような質問「どの注文書は、100 ドルの価格がある」でしょうか。 あいまいになります。 質問を明確にすると、次のようになります。  
  
- 価格が 100 ドルの品目があるのはどの注文書か  
  
- 合計/最低/最高 100 ドルの価格があるのはどの注文書か  
  
  明確な質問を作成するには、注文書とは別のものとして品目を考える必要があります。 追跡プロファイル エディターでは、ルート アクティビティ (注文書など) はループの外側のすべてのアクションにマップされます。 子アクティビティ (品目など) は、ループ内のアクションにマップされます。  
  
  ルート アクティビティの ActivityID としてペイロード項目を使用する必要があります。 ループ内のメッセージの一部でこのペイロード項目を使用可能にします。 アクティビティを子アクティビティの下に表示されるリレーションシップ ノードにマップして、ルート アクティビティとして名前を付けます。  
  
## <a name="see-also"></a>参照  
 [イベント ストリームを使用した BAM アクティビティを実装します。](../core/implementing-bam-activities-with-event-streams.md)