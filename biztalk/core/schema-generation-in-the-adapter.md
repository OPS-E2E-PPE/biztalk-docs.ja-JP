---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 04db79d76850bf657dbd45e6c60e6fb7edbf1ffb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396950"
---
# <a name="schema-generation-in-the-adapter"></a>アダプタでスキーマの生成
TIBCO Rendezvous システムでは、メッセージの種類のリポジトリは含まれません。 すべてのメッセージの構築と解析が、Rendezvous アプリケーション レベルで埋め込まれています。 この制限により、Microsoft BizTalk Adapter for TIBCO Rendezvous はスキーマ生成機能を提供できません。  
  
## <a name="writing-schemas"></a>スキーマの記述  
 スキーマを記述し、使用する必要があります**既存項目の追加**Visual Studio でオーケストレーション用にインポートします。 スキーマは、BizTalk Server 開発ツールと Visual Studio での統合のために非常に重要です。 BizTalk Server の開発者は、完全なスキーマ、必要最低限のスキーマまたはとの間のどこかのバージョンの提供を選択できます。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)