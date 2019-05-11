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
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="6a6ad-101">アダプタでスキーマの生成</span><span class="sxs-lookup"><span data-stu-id="6a6ad-101">Schema Generation in the Adapter</span></span>
<span data-ttu-id="6a6ad-102">TIBCO Rendezvous システムでは、メッセージの種類のリポジトリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="6a6ad-102">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="6a6ad-103">すべてのメッセージの構築と解析が、Rendezvous アプリケーション レベルで埋め込まれています。</span><span class="sxs-lookup"><span data-stu-id="6a6ad-103">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="6a6ad-104">この制限により、Microsoft BizTalk Adapter for TIBCO Rendezvous はスキーマ生成機能を提供できません。</span><span class="sxs-lookup"><span data-stu-id="6a6ad-104">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="6a6ad-105">スキーマの記述</span><span class="sxs-lookup"><span data-stu-id="6a6ad-105">Writing Schemas</span></span>  
 <span data-ttu-id="6a6ad-106">スキーマを記述し、使用する必要があります**既存項目の追加**Visual Studio でオーケストレーション用にインポートします。</span><span class="sxs-lookup"><span data-stu-id="6a6ad-106">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="6a6ad-107">スキーマは、BizTalk Server 開発ツールと Visual Studio での統合のために非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="6a6ad-107">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="6a6ad-108">BizTalk Server の開発者は、完全なスキーマ、必要最低限のスキーマまたはとの間のどこかのバージョンの提供を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6a6ad-108">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a6ad-109">参照</span><span class="sxs-lookup"><span data-stu-id="6a6ad-109">See Also</span></span>  
 [<span data-ttu-id="6a6ad-110">作業の開始</span><span class="sxs-lookup"><span data-stu-id="6a6ad-110">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)