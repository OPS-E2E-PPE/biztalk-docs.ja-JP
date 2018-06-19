---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: dc9746babaa80520b2a99948c5796c9b064899e0
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015585"
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a>TIBCO Enterprise Message Service 用の送信パイプラインを設定する方法
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service では、送信パイプラインに XMLTransmit、受信パイプラインに XMLReceive をそれぞれ選択する必要があります。  
  
### <a name="to-set-pipelines"></a>パイプラインを設定するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO EMS**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。  
  
4.  **[OK]** をクリックします。  
  
