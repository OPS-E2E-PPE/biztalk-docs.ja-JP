---
title: "BizTalk Server 管理コンソールへの SQL アダプタの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3510fb31bffe4c5823593fac34d5d5f1d5849c65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="13dd9-102">BizTalk Server 管理コンソールへの SQL アダプタの追加</span><span class="sxs-lookup"><span data-stu-id="13dd9-102">Adding the SQL Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="13dd9-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で BizTalk WCF カスタム ポートまたは WCF SQL ポートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="13dd9-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SQL port.</span></span> <span data-ttu-id="13dd9-104">使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF カスタム ポートを経由は WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="13dd9-104">If you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="13dd9-105">ただし、使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF-SQL ポートを介して、WCF-SQL アダプターを追加する必要があります最初、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="13dd9-105">However, if you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-SQL port, you must first add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="13dd9-106">このトピックは、WCF SQL アダプターを追加する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="13dd9-106">This topic shows you how to add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="13dd9-107">これらの手順に従う場合は、WCF カスタム ポートを構成する必要はありません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="13dd9-107">You do not need to follow these steps if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="add-the-sql-adapter"></a><span data-ttu-id="13dd9-108">SQL アダプタを追加します。</span><span class="sxs-lookup"><span data-stu-id="13dd9-108">Add the SQL Adapter</span></span>  
  
1.  <span data-ttu-id="13dd9-109">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="13dd9-109">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="13dd9-110">展開して、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="13dd9-110">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3.  <span data-ttu-id="13dd9-111">右クリック**アダプター**、 をポイント**新規**を選択して**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="13dd9-111">Right-click **Adapters**, point to **New**, and select **Adapter**.</span></span>  
  
     <span data-ttu-id="13dd9-112">![アダプタの追加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="13dd9-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4.  <span data-ttu-id="13dd9-113">**アダプター プロパティ**] ダイアログ ボックスで、アダプターとの間の名前を入力、**アダプター**一覧で、[ **WCF-SQL**です。</span><span class="sxs-lookup"><span data-stu-id="13dd9-113">In the **Adapter Properties** dialog box, enter a name for the adapter, and from the **Adapter** list, select **WCF-SQL**.</span></span>  
  
     <span data-ttu-id="13dd9-114">![WCF &#45; を追加します。Biztalk SQL アダプター](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span><span class="sxs-lookup"><span data-stu-id="13dd9-114">![Add WCF&#45;SQL adapter to BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span></span>  
  
5.  <span data-ttu-id="13dd9-115">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13dd9-115">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13dd9-116">参照</span><span class="sxs-lookup"><span data-stu-id="13dd9-116">See Also</span></span>  
 [<span data-ttu-id="13dd9-117">SQL アダプタを BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="13dd9-117">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)