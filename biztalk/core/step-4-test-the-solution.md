---
title: 手順 4:ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56869aa22ab54efe78838403ae060154b98a001a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392472"
---
# <a name="step-4-test-the-solution"></a>手順 4:ソリューションをテストします。
このトピックの「ファイルと関連付けられているフォルダーにダミー要求メッセージを削除することにより、ソリューションをテストするポートが表示されます。 呼び出すためにのみダミー要求メッセージをドロップする前述のように、 **Wcf-webhttp**ポートを送信します。 次のようなダミー要求メッセージを作成できます。  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1.  BizTalk Server 管理コンソールから開始**BizTalk アプリケーション 1**します。 これは、前の手順で作成したすべてのポートを開始します。  
  
2.  Windows エクスプ ローラーを開き、ファイルと関連付けた場所に移動して受信場所。 この場所で、ダミーの要求メッセージをコピーします。  
  
3.  ファイルが、REST インターフェイスから応答メッセージを処理する FILE 送信ポートと関連付けられている場所を確認します。 XML 応答メッセージを含めることが必要があります。 遅延は米国航空の実行からのフライトの詳細を表示する XML メッセージを開きます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)