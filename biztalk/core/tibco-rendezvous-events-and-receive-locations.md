---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: cd807abafe2cf8769bf4816143facdaf37607d5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400148"
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO Rendezvous イベントと受信場所
TIBCO Rendezvous システムは、選択したサブジェクト名にメッセージを送信できます。 概念*イベント*は他の TIBCO Rendezvous プログラムによるメッセージの生成。  
  
 次の手順は、受信場所のライフ サイクルについて説明しています。  
  
1.  受信場所が作成されます。  
  
2.  受信場所がホストに関連付けられます。  
  
3.  受信場所がオーケストレーションにバインドされます。  
  
4.  受信場所が有効化されます。  
  
5.  受信場所がメッセージを受信します。  
  
> [!IMPORTANT]
>  各受信場所には一意の名前が必要です。 2 つの受信場所が同じ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開で同じ名前を持つことはできません。  
> 
> [!IMPORTANT]
>  お勧め強力なアクセス制御リスト (ACL) に設定することで、受信場所のドロップ場所。 たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)