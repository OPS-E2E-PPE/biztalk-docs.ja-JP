---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2fbc1b4c16f94ef9397ff50a4e6d44d6aab051a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334233"
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a>TIBCO Enterprise Message Service 用の送信パイプラインを設定する方法
Microsoft の BizTalk Adapter for TIBCO Enterprise Message Service では、送信 XMLTransmit および XMLReceive を選択して、受信パイプラインをそれぞれことが必要です。  
  
### <a name="to-set-pipelines"></a>パイプラインを設定するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCOEMS`します。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO EMS**します。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  
  
4.  **[OK]** をクリックします。  
  
