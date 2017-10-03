---
title: "手順 4: ソリューションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f0ae6cb124ea9d8710797790b9176289faafc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-solution"></a>手順 4: ソリューションをテストします。
このトピックでは、FILE 受信ポートに関連付けられているフォルダーにダミー要求メッセージをドロップして、ソリューションをテストします。 呼び出す場合にのみダミー要求メッセージをドロップするで説明したよう、 **Wcf-webhttp**ポートを送信します。 次のようなダミー要求メッセージを作成できます。  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1.  BizTalk Server 管理コンソールから起動**BizTalk アプリケーション 1**です。 これによって、前の手順で作成したすべてのポートが起動されます。  
  
2.  Windows エクスプローラーを開き、FILE 受信場所と関連付けた場所に移動します。 この場所で、ダミー要求メッセージをコピーします。  
  
3.  ファイルがない場合は、REST インターフェイスからの応答メッセージを使用する FILE 送信ポートと関連付けた場所を調べます。 XML 応答メッセージが含まれます。 XML メッセージを開き、送れた米国航空会社のフライトの詳細を見ます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)