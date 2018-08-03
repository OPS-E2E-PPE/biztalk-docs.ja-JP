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
ms.openlocfilehash: 48c6db99d656274f89ee5866f772db163de26c31
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976547"
---
# <a name="how-to-add-constant-values"></a>定数値を追加する方法
マップをテストする際、テスト中に使用する定数値を設定する場合があります。  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a>送信元または送信先のスキーマ ツリー ノードの定数値を設定します。  
  
1. 送信元スキーマ ツリーまたは送信先スキーマ ツリーのレコードまたはフィールドを選択します。  
  
2. [プロパティ] ウィンドウで、**全般**カテゴリを使用して、**値**プロパティを選択したレコードまたはフィールドの値を入力します。  
  
   > [!NOTE]
   >  レコードを含む値を関連付けることができますのみその**コンテンツ**プロパティに設定**テキストのみ**または**Mixed**します。  
  
   設定した場合、送信元スキーマ内のノードの**値**プロパティを**\<空\>**、送信元スキーマの生成されたインスタンス メッセージには、それぞれに空の値が含まれています。ノードです。  
  
   送信先スキーマのフィールドをすべては使用しないことがあります。つまり、送信先スキーマのフィールドには、受信リンクが指定されないものもあります。 マップのテスト操作をこのような場合に、提供する、エラーをスローします、 **TestMap 入力の検証**または**TestMap 出力の検証**プロパティに設定されます**True**します。 このような場合、マップのテスト エラーを回避するには、設定、**値**定数の値にノードのプロパティまたは**\<空\>**。 使用**\<空\>** 未使用の送信先スキーマのフィールドの任意のデータを設定したくない場合。  
  
## <a name="see-also"></a>参照  
[マップの検証とテスト](../core/how-to-configure-map-validation-and-test-parameters.md)