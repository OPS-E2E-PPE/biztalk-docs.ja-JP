---
redirect_url: /biztalk/core/using-tibco-rendezvous-send-ports-from-biztalk-server/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 81e597ead592d001c53c4a360f5d5ca8d3981ac2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401650"
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a>TIBCO Rendezvous から BizTalk Server を使用してメッセージを送信するには
Microsoft BizTalk Adapter for TIBCO Rendezvous は、非同期 API (Transport.Send) を使用します。 メッセージ コンテキスト プロパティを使用して、このアダプターが送信するメッセージの種類を指定できます。  
  
- **構造化された**:アダプターは、BizTalk Server から受信した XML データに基づいて、TIBRVMSG_MSG 構造化されたメッセージを生成します。 (*)  
  
  BizTalk Server が 127 文字を超える名前を持つフィールドのあるメッセージを送信した場合、BizTalk Adapter for TIBCO Rendezvous は、TIBCO Rendezvous の最大フィールド名サイズ (127 文字) に名前を切り捨てます。  
  
  `reply subject name` プロパティが指定されている場合、このプロパティを使用して TIBCO Rendezvous メッセージの返信の件名が設定されます。 受信ポートが応答を待機して BizTalk Server に転送するように設定されているか、その他の TIBCO Rendezvous プログラムが応答を処理すると想定されています。  
  
  トリプレット (サービス、デーモン、およびネットワーク) がトランスポートの構成を形成します。 トランスポートの構成が空白の場合 (既定)、メッセージは既定のトランスポート オブジェクトを介して送信されます。  
  
  コード ページを指定しない場合、このアダプターは UTF-8 エンコーディング (コード ページ 65001) を使用します。 伝送側では、認定済みメッセージはサポートされません。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)