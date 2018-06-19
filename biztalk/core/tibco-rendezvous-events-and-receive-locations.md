---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: b93e747cdc665fb5a8407ca2a3d052b880236378
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013041"
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO Rendezvous イベントと受信場所
TIBCO Rendezvous システムは、選択したサブジェクト名にメッセージを送信できます。 概念*イベント*の他の TIBCO Rendezvous プログラムでメッセージが生成されます。  
  
 次の手順は、受信場所のライフ サイクルについて説明しています。  
  
1.  受信場所が作成されます。  
  
2.  受信場所がホストに関連付けられます。  
  
3.  受信場所がオーケストレーションにバインドされます。  
  
4.  受信場所が有効化されます。  
  
5.  受信場所がメッセージを受信します。  
  
> [!IMPORTANT]
>  各受信場所には一意の名前が必要です。 2 つの受信場所が同じ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開で同じ名前を持つことはできません。  
  
> [!IMPORTANT]
>  お勧め強力なアクセス制御リスト (ACL) に設定することで、受信場所のドロップ場所。 たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)