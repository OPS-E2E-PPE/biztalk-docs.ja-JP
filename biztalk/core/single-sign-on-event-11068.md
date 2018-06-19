---
title: 'シングル サインオン: イベント 11068 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be824a9205d81aaaeb9fd87129133b94b4f2e379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277810"
---
# <a name="single-sign-on-event-11068"></a><span data-ttu-id="994c8-102">シングル サインオン: イベント 11068</span><span class="sxs-lookup"><span data-stu-id="994c8-102">Single Sign-On: Event 11068</span></span>
## <a name="details"></a><span data-ttu-id="994c8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="994c8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="994c8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="994c8-104">Product Name</span></span>|<span data-ttu-id="994c8-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="994c8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="994c8-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="994c8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="994c8-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="994c8-107">Event ID</span></span>|<span data-ttu-id="994c8-108">11068</span><span class="sxs-lookup"><span data-stu-id="994c8-108">11068</span></span>|  
|<span data-ttu-id="994c8-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="994c8-109">Event Source</span></span>|<span data-ttu-id="994c8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="994c8-110">ENTSSO</span></span>|  
|<span data-ttu-id="994c8-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="994c8-111">Component</span></span>|<span data-ttu-id="994c8-112">なし</span><span class="sxs-lookup"><span data-stu-id="994c8-112">N/A</span></span>|  
|<span data-ttu-id="994c8-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="994c8-113">Symbolic Name</span></span>|<span data-ttu-id="994c8-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span><span class="sxs-lookup"><span data-stu-id="994c8-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span></span>|  
|<span data-ttu-id="994c8-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="994c8-115">Message Text</span></span>|<span data-ttu-id="994c8-116">参照サーバーのアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="994c8-116">Lookup server access denied.</span></span> <span data-ttu-id="994c8-117">この SSO サーバーは、現在、リモート参照を許可するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="994c8-117">This SSO server is currently not configured to allow remote lookup.</span></span> <span data-ttu-id="994c8-118">'ssoconfig -remoteLookup yes' または SSO 管理 MMC を使用してください。%r</span><span class="sxs-lookup"><span data-stu-id="994c8-118">Use 'ssoconfig -remoteLookup yes' or the SSO Administration MMC.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="994c8-119">説明</span><span class="sxs-lookup"><span data-stu-id="994c8-119">Explanation</span></span>  
 <span data-ttu-id="994c8-120">ENTSSO サーバーがリモート参照を許可するように構成されていないため、参照サーバー アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="994c8-120">Lookup server access has been denied because the ENTSSO server is not configured to allow remote lookup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="994c8-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="994c8-121">User Action</span></span>  
 <span data-ttu-id="994c8-122">リモートの検索を許可するよう、**サーバー スナップイン**、 **[詳細設定]** ] タブで [**リモート検索を許可する**です。</span><span class="sxs-lookup"><span data-stu-id="994c8-122">To allow remote lookup, in the **Servers Snap-In**, **Advanced** tab, select **Allow Remote Lookup**.</span></span>  
  
 <span data-ttu-id="994c8-123">詳細については、次を参照してください。[サーバー スナップインを使用する](../core/how-to-use-the-servers-snap-in.md)です。</span><span class="sxs-lookup"><span data-stu-id="994c8-123">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>