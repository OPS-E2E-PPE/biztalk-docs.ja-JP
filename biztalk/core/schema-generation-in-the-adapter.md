---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 4e4209c75ca52585c0a11141dbe0d9841fa6a5ba
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24016021"
---
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="6b368-101">アダプタでのスキーマの生成</span><span class="sxs-lookup"><span data-stu-id="6b368-101">Schema Generation in the Adapter</span></span>
<span data-ttu-id="6b368-102">TIBCO Rendezvous システムには、メッセージの種類のリポジトリは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="6b368-102">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="6b368-103">すべてのメッセージの構築と解析は、Rendezvous アプリケーション レベルに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="6b368-103">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="6b368-104">この制限により、Microsoft BizTalk Adapter for TIBCO Rendezvous ではスキーマ生成機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="6b368-104">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="6b368-105">スキーマの記述</span><span class="sxs-lookup"><span data-stu-id="6b368-105">Writing Schemas</span></span>  
 <span data-ttu-id="6b368-106">スキーマを記述して、使用する必要があります**既存項目の追加**オーケストレーションで使用できるは、インポートする Visual Studio でします。</span><span class="sxs-lookup"><span data-stu-id="6b368-106">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="6b368-107">スキーマは、BizTalk Server の開発ツールに必要で、Visual Studio での統合において非常に重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="6b368-107">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="6b368-108">BizTalk Server の開発者は、完全なスキーマを作成する必要はなく、最小限のスキーマやその中間のスキーマも作成できます。</span><span class="sxs-lookup"><span data-stu-id="6b368-108">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b368-109">参照</span><span class="sxs-lookup"><span data-stu-id="6b368-109">See Also</span></span>  
 [<span data-ttu-id="6b368-110">作業の開始</span><span class="sxs-lookup"><span data-stu-id="6b368-110">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)