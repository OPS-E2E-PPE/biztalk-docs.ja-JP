---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: c3fe43f5ec5f69c84d9f679325a7437d84f2b7d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338930"
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a>TIBCO Rendezvous の送信ポートを作成する方法
次の手順を実行して、作成、送信ポートを使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCORV`します。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO Rendezvous**します。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  **送信パイプライン**ドロップダウン リストで、 **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。 **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  
  
    6.  クリックして**構成**送信ポートを構成します。  
  
4.  **TIBCO Rendezvous トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  プロパティを入力します。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、TIBCO Rendezvous システムを表すように作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用**、**はい**します。  
  
    4.  **[OK]** をクリックします。  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)