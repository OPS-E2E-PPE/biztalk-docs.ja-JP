---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: a0c6ba9e0d90170bf4f5e7c2a76ae8829a1506ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385420"
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a>TIBCO Enterprise Message Service の送信ポートを作成する方法
送信ポートを作成する次の手順に従います。  
  
## <a name="creating-a-send-port"></a>送信ポートの作成  
  
#### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCOEMS`します。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO EMS**します。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  
  
    6.  クリックして**構成**送信ポートを構成します。  
  
4.  **TIBCO EMS トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  入力**メッセージの処理**、**サーバー接続の定義**、**トランザクションのサポート**、 **Username**、および**パスワード**します。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、TIBCO EMS システムを表すよう作成した関連アプリケーションを選択します。  
  
    3.  **SSO を使用**、**はい**します。  
  
    4.  **[OK]** をクリックします。  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
  [TIBCO Enterprise Message Service 送信ハンドラーの作成](../core/creating-tibco-enterprise-message-service-send-handlers.md)