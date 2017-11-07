---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: bcccc92430a73685ced9ad7259d8ec57dfc450b8
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-limitations"></a>TIBCO Rendezvous の制限事項
TIBCO Rendezvous では、フィールド名が一意であるとは限りません。 TIBCO Rendezvous メッセージに 2 つの同じフィールド名がある場合、生成される XML は無効になります。  
  
 他にも次の制限があります。  
  
-   フィールドを並べ替えることはできません。  
  
-   TIBCO Rendezvous のドキュメントによると、サブジェクト名には印刷できない文字を使用できないことになっていますが、そのような文字を使用することはできます。 BizTalk Adapter for TIBCO Rendezvous では印刷できない文字が入ったサブジェクト名をサポートしていません。  
  
-   デーモンへのセキュリティで保護された接続はサポートされていません。  
  
-   カスタム データ型はサポートされていません。  
  
-   認定メッセージングは送信側ではサポートされていません。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)