---
title: "作成と送信ポート グループの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6dd1ac37-a6e4-4ea0-9eff-ee400b3f3d74
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 987b1e9fe780ad6841a13a477678d3b61556fac7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-configuring-send-port-groups"></a><span data-ttu-id="56515-102">送信ポート グループの作成および構成</span><span class="sxs-lookup"><span data-stu-id="56515-102">Creating and Configuring Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="56515-103">概要</span><span class="sxs-lookup"><span data-stu-id="56515-103">Overview</span></span>
<span data-ttu-id="56515-104">このセクションでは、BizTalk Server 管理コンソールを使用して送信ポート グループを BizTalk アプリケーションに追加する方法と、送信ポート グループを構成および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56515-104">This section provides instructions on using the BizTalk Server Administration console to add send port groups to a BizTalk application as well as to configure and delete send port groups.</span></span> <span data-ttu-id="56515-105">送信ポート グループは、送信ポートの名前付きコレクションです。送信ポート グループを使用すると、複数の送信先に同じメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="56515-105">A send port group is a named collection of send ports that can be used to send the same message to multiple destinations.</span></span> <span data-ttu-id="56515-106">送信ポート グループは、単独の送信ポートの場合と同様に、オーケストレーション ポートにバインドしたり、コンテンツ ベースのルーティング (CBR) に使用できます。</span><span class="sxs-lookup"><span data-stu-id="56515-106">You can bind send port groups to orchestration ports or use them for content-based routing (CBR) just as you can for a single send port.</span></span> <span data-ttu-id="56515-107">送信ポート グループの基礎知識については、次を参照してください。[送信ポートおよび送信ポート グループ](../core/send-ports-and-send-port-groups.md)です。</span><span class="sxs-lookup"><span data-stu-id="56515-107">For background information on send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56515-108">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="56515-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="56515-109">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="56515-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="56515-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="56515-110">Next steps</span></span>
  
-   [<span data-ttu-id="56515-111">送信ポート グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="56515-111">Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="56515-112">送信ポート、送信ポート グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="56515-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="56515-113">送信ポート、送信ポート グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="56515-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="56515-114">送信ポート グループのフィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="56515-114">Configure Filters for a Send Port Group</span></span>](../core/how-to-configure-filters-for-a-send-port-group.md)  
  
-   [<span data-ttu-id="56515-115">送信ポート グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="56515-115">Delete a Send Port Group</span></span>](../core/how-to-delete-a-send-port-group.md)