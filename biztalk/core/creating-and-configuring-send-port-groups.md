---
title: 作成と送信ポート グループの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dd1ac37-a6e4-4ea0-9eff-ee400b3f3d74
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 882322d6f8197868ee81e95e3a7809d15266356d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389968"
---
# <a name="creating-and-configuring-send-port-groups"></a><span data-ttu-id="3d6c9-102">作成と送信ポート グループの構成</span><span class="sxs-lookup"><span data-stu-id="3d6c9-102">Creating and Configuring Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="3d6c9-103">概要</span><span class="sxs-lookup"><span data-stu-id="3d6c9-103">Overview</span></span>
<span data-ttu-id="3d6c9-104">このセクションでは、BizTalk Server 管理コンソールを使用して追加する手順を送信ポート グループを構成および削除と、BizTalk アプリケーションを送信ポート グループを提供します。</span><span class="sxs-lookup"><span data-stu-id="3d6c9-104">This section provides instructions on using the BizTalk Server Administration console to add send port groups to a BizTalk application as well as to configure and delete send port groups.</span></span> <span data-ttu-id="3d6c9-105">送信ポート グループは、複数の送信先に同じメッセージを送信するために使用する送信ポートの名前付きコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3d6c9-105">A send port group is a named collection of send ports that can be used to send the same message to multiple destinations.</span></span> <span data-ttu-id="3d6c9-106">送信ポート グループをオーケストレーション ポートにバインドしたり、コンテンツ ベースのルーティング (CBR) を使用することが 1 つの送信ポートと同様です。</span><span class="sxs-lookup"><span data-stu-id="3d6c9-106">You can bind send port groups to orchestration ports or use them for content-based routing (CBR) just as you can for a single send port.</span></span> <span data-ttu-id="3d6c9-107">送信ポート グループの背景については、次を参照してください。[送信ポートと送信ポート グループ](../core/send-ports-and-send-port-groups.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d6c9-107">For background information on send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d6c9-108">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="3d6c9-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="3d6c9-109">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3d6c9-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="3d6c9-110">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3d6c9-110">Next steps</span></span>
  
-   [<span data-ttu-id="3d6c9-111">送信ポート グループの作成</span><span class="sxs-lookup"><span data-stu-id="3d6c9-111">Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="3d6c9-112">送信ポート グループへの送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="3d6c9-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="3d6c9-113">送信ポート グループから送信ポートを削除する</span><span class="sxs-lookup"><span data-stu-id="3d6c9-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="3d6c9-114">送信ポート グループのフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="3d6c9-114">Configure Filters for a Send Port Group</span></span>](../core/how-to-configure-filters-for-a-send-port-group.md)  
  
-   [<span data-ttu-id="3d6c9-115">送信ポート グループの削除</span><span class="sxs-lookup"><span data-stu-id="3d6c9-115">Delete a Send Port Group</span></span>](../core/how-to-delete-a-send-port-group.md)