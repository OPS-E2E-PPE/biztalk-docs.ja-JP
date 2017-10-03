---
title: "TIBCO Enterprise Message Service の送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- ports, send
- send ports, creating
ms.assetid: 6e569244-494e-4db4-8030-eda3b390d073
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfadeb3306687bfcbea27c0df41973b12b003563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a>TIBCO Enterprise Message Service の送信ポートを作成する方法
送信ポートを作成するには、次の手順を実行します。  
  
## <a name="creating-a-send-port"></a>送信ポートの作成  
  
#### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO EMS**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。  
  
    6.  をクリックして**構成**送信ポートを構成します。  
  
4.  **TIBCO EMS トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  入力**メッセージ処理**、**サーバー接続の定義**、**トランザクション サポート**、 **Username**、および**パスワード**です。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、TIBCO EMS システムを表すよう作成した関連アプリケーションを選択します。  
  
    3.  **SSO を使用する****はい**です。  
  
    4.  **[OK]**をクリックします。  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [送信ポートの TIBCO Enterprise Message Service トランスポート プロパティの設定](../core/setting-tibco-enterprise-message-service-transport-properties-for-the-send-port.md)   
 [TIBCO Enterprise Message Service 送信ハンドラーを作成します。](../core/creating-tibco-enterprise-message-service-send-handlers.md)