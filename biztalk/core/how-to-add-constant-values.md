---
title: 定数値を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f46bf66e-caf2-4352-930f-c3c43a5717c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6510c278be4f64814dd690d275e42c6739587e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387236"
---
# <a name="how-to-add-constant-values"></a>定数値を追加する方法
マップをテストするときに、テスト中に使用する定数値を設定するが場合があります。  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a>送信元または送信先のスキーマ ツリー ノードの定数値を設定します。  
  
1. 送信元または送信先スキーマ ツリーで、レコードまたはフィールドを選択します。  
  
2. [プロパティ] ウィンドウで、**全般**カテゴリを使用して、**値**プロパティを選択したレコードまたはフィールドの値を入力します。  
  
   > [!NOTE]
   >  レコードを含む値を関連付けることができますのみその**コンテンツ**プロパティに設定**テキストのみ**または**Mixed**します。  
  
   設定した場合、送信元スキーマ内のノードの**値**プロパティを**\<空\>**、送信元スキーマの生成されたインスタンス メッセージには、それぞれに空の値が含まれています。ノードです。  
  
   場合によっては、ターゲット スキーマのすべてのフィールドを使用しない、つまり、ターゲット スキーマのフィールドのいくつか必要はありません受信リンク。 マップのテスト操作をこのような場合に、提供する、エラーをスローします、 **TestMap 入力の検証**または**TestMap 出力の検証**プロパティに設定されます**True**します。 このような場合、マップのテスト エラーを回避するには、設定、**値**定数の値にノードのプロパティまたは**\<空\>**。 使用**\<空\>** 未使用の送信先スキーマのフィールドの任意のデータを設定したくない場合。  
  
## <a name="see-also"></a>参照  
[マップの検証とテスト](../core/how-to-configure-map-validation-and-test-parameters.md)