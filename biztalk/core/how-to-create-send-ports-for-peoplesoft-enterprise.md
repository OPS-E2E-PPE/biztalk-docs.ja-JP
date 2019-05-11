---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 8f129c36e2f6765c76d76ee891ee297c0ccfeffe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338912"
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a>PeopleSoft Enterprise の送信ポートを作成する方法
BizTalk Server 管理コンソールを使用して送信ポートを作成する次の手順に従います。  
  
## <a name="creating-a-send-port"></a>送信ポートの作成  
  
#### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`します。  
  
    2.  **型**ドロップダウン リストで、 **PeopleSoft**します。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  
  
    6.  クリックして**構成**送信ポートを構成します。  
  
4.  **PeopleSoft トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイル。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用**、**はい**します。  
  
    4.  **[OK]** をクリックします。  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)