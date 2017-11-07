---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 4e4209c75ca52585c0a11141dbe0d9841fa6a5ba
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="schema-generation-in-the-adapter"></a>アダプタでのスキーマの生成
TIBCO Rendezvous システムには、メッセージの種類のリポジトリは含まれていません。 すべてのメッセージの構築と解析は、Rendezvous アプリケーション レベルに組み込まれています。 この制限により、Microsoft BizTalk Adapter for TIBCO Rendezvous ではスキーマ生成機能を利用できません。  
  
## <a name="writing-schemas"></a>スキーマの記述  
 スキーマを記述して、使用する必要があります**既存項目の追加**オーケストレーションで使用できるは、インポートする Visual Studio でします。 スキーマは、BizTalk Server の開発ツールに必要で、Visual Studio での統合において非常に重要な役割を果たします。 BizTalk Server の開発者は、完全なスキーマを作成する必要はなく、最小限のスキーマやその中間のスキーマも作成できます。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)