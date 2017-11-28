---
title: "シングル サインオン: イベント 11060 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1423b7385e6c0b8f78fb815ec48b749556cd291f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11060"></a><span data-ttu-id="fbcd9-102">シングル サインオン: イベント 11060</span><span class="sxs-lookup"><span data-stu-id="fbcd9-102">Single Sign-On: Event 11060</span></span>
## <a name="details"></a><span data-ttu-id="fbcd9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fbcd9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbcd9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fbcd9-104">Product Name</span></span>|<span data-ttu-id="fbcd9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fbcd9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="fbcd9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fbcd9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="fbcd9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fbcd9-107">Event ID</span></span>|<span data-ttu-id="fbcd9-108">11060</span><span class="sxs-lookup"><span data-stu-id="fbcd9-108">11060</span></span>|  
|<span data-ttu-id="fbcd9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fbcd9-109">Event Source</span></span>|<span data-ttu-id="fbcd9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fbcd9-110">ENTSSO</span></span>|  
|<span data-ttu-id="fbcd9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fbcd9-111">Component</span></span>|<span data-ttu-id="fbcd9-112">なし</span><span class="sxs-lookup"><span data-stu-id="fbcd9-112">N/A</span></span>|  
|<span data-ttu-id="fbcd9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fbcd9-113">Symbolic Name</span></span>|<span data-ttu-id="fbcd9-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="fbcd9-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="fbcd9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fbcd9-115">Message Text</span></span>|<span data-ttu-id="fbcd9-116">MIIS からの Windows パスワード変更は、SSO サービス アカウントからのもののみ受け付けられます。%r</span><span class="sxs-lookup"><span data-stu-id="fbcd9-116">Windows password changes from MIIS will only be accepted from the SSO service account.%r</span></span><br /><br /> <span data-ttu-id="fbcd9-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fbcd9-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="fbcd9-118">クライアント ユーザー: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fbcd9-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="fbcd9-119">SSO サービス アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="fbcd9-119">SSO Service Account: %3%r</span></span><br /><br /> <span data-ttu-id="fbcd9-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="fbcd9-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fbcd9-121">説明</span><span class="sxs-lookup"><span data-stu-id="fbcd9-121">Explanation</span></span>  
 <span data-ttu-id="fbcd9-122">ENTSSO サーバーが、Microsoft Identity Integration Server (MIIS) からパスワード変更を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="fbcd9-122">A password change has been received by the ENTSSO server from Microsoft Identity Integration Server (MIIS).</span></span> <span data-ttu-id="fbcd9-123">しかし、ENTSSO サーバーは、クライアント ユーザー (呼び出し元) が SSO サービス アカウントと同じアカウントの場合にのみ、MIIS からのパスワード変更を受け付けます。</span><span class="sxs-lookup"><span data-stu-id="fbcd9-123">However, the ENTSSO server will only accept password changes from MIIS if the Client User (the caller) is the same account as the SSO service account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fbcd9-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fbcd9-124">User Action</span></span>  
 <span data-ttu-id="fbcd9-125">MIIS でのパスワード同期の呼び出し元の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="fbcd9-125">Check the configuration of the caller for password sync in MIIS.</span></span> <span data-ttu-id="fbcd9-126">詳細については、次を参照してください。 [ENTSSO MIIS パスワード同期用に構成する方法](../core/how-to-configure-entsso-for-miis-password-sync.md)です。</span><span class="sxs-lookup"><span data-stu-id="fbcd9-126">For more information, see [How to Configure ENTSSO for MIIS Password Sync](../core/how-to-configure-entsso-for-miis-password-sync.md).</span></span>