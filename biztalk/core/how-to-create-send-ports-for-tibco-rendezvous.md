---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 44da7839f0bee96db332dada214bdbc503067f56
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013161"
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a>TIBCO Rendezvous の送信ポートを作成する方法
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して送信ポートを作成するには、次の手順を実行します。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCORV`です。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO Rendezvous**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  **送信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。 **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。  
  
    6.  をクリックして**構成**送信ポートを構成します。  
  
4.  **TIBCO Rendezvous トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  プロパティを入力します。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、TIBCO Rendezvous システムを表すように作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用する****はい**です。  
  
    4.  **[OK]** をクリックします。  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)