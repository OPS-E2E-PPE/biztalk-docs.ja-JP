---
title: BizTalk Server 管理コンソールへの SQL アダプタの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22297a5e41d82004852e3cba7e11041d774238c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370060"
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="31960-102">BizTalk Server 管理コンソールへの SQL アダプタの追加</span><span class="sxs-lookup"><span data-stu-id="31960-102">Adding the SQL Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="31960-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Biztalk WCF カスタム ポートまたは WCF SQL ポートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="31960-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SQL port.</span></span> <span data-ttu-id="31960-104">使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="31960-104">If you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="31960-105">ただし、使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF SQL ポートを経由する WCF-SQL アダプターを最初に追加する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="31960-105">However, if you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-SQL port, you must first add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="31960-106">このトピックでは、WCF-SQL アダプターを追加する方法、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="31960-106">This topic shows you how to add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="31960-107">WCF カスタム ポートを構成する場合は、これらの手順を実行する必要はありません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="31960-107">You do not need to follow these steps if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="add-the-sql-adapter"></a><span data-ttu-id="31960-108">SQL アダプタを追加します。</span><span class="sxs-lookup"><span data-stu-id="31960-108">Add the SQL Adapter</span></span>  
  
1. <span data-ttu-id="31960-109">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="31960-109">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="31960-110">展開、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="31960-110">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3. <span data-ttu-id="31960-111">右クリック**アダプター**、 をポイント**新規**、選択と**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="31960-111">Right-click **Adapters**, point to **New**, and select **Adapter**.</span></span>  
  
    <span data-ttu-id="31960-112">![アダプターを追加する](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="31960-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="31960-113">**アダプター プロパティ**] ダイアログ ボックスに、アダプターの場合との間の名前を入力、**アダプター**一覧で、[ **WCF-SQL**します。</span><span class="sxs-lookup"><span data-stu-id="31960-113">In the **Adapter Properties** dialog box, enter a name for the adapter, and from the **Adapter** list, select **WCF-SQL**.</span></span>  
  
    <span data-ttu-id="31960-114">![WCF の追加&#45;biztalk SQL アダプター](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span><span class="sxs-lookup"><span data-stu-id="31960-114">![Add WCF&#45;SQL adapter to BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span></span>  
  
5. <span data-ttu-id="31960-115">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="31960-115">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31960-116">参照</span><span class="sxs-lookup"><span data-stu-id="31960-116">See Also</span></span>  
 [<span data-ttu-id="31960-117">SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="31960-117">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)