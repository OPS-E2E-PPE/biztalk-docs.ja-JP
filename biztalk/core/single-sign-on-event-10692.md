---
title: "シングル サインオン: イベント 10692 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2dce820864338cd5ba3b8ecf4a469ae75550a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10692"></a><span data-ttu-id="c55df-102">シングル サインオン: イベント 10692</span><span class="sxs-lookup"><span data-stu-id="c55df-102">Single Sign-On: Event 10692</span></span>
## <a name="details"></a><span data-ttu-id="c55df-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c55df-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c55df-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c55df-104">Product Name</span></span>|<span data-ttu-id="c55df-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c55df-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c55df-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c55df-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c55df-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c55df-107">Event ID</span></span>|<span data-ttu-id="c55df-108">10692</span><span class="sxs-lookup"><span data-stu-id="c55df-108">10692</span></span>|  
|<span data-ttu-id="c55df-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c55df-109">Event Source</span></span>|<span data-ttu-id="c55df-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c55df-110">ENTSSO</span></span>|  
|<span data-ttu-id="c55df-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c55df-111">Component</span></span>|<span data-ttu-id="c55df-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c55df-112">N\A</span></span>|  
|<span data-ttu-id="c55df-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c55df-113">Symbolic Name</span></span>|<span data-ttu-id="c55df-114">SSO_WARN_REPLAY_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="c55df-114">SSO_WARN_REPLAY_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="c55df-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c55df-115">Message Text</span></span>|<span data-ttu-id="c55df-116">元の呼び出し元がアダプターのアクセス アカウントのメンバーではなくなったため、外部パスワード変更を再生できません。%r</span><span class="sxs-lookup"><span data-stu-id="c55df-116">The external password change cannot be replayed because the original caller is no longer a member of the access account for the adapter.%r</span></span><br /><br /> <span data-ttu-id="c55df-117">再生ファイル: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c55df-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="c55df-118">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c55df-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c55df-119">最初の呼び出し元: %3 %r</span><span class="sxs-lookup"><span data-stu-id="c55df-119">Original Caller: %3%r</span></span><br /><br /> <span data-ttu-id="c55df-120">アクセス アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="c55df-120">Access Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c55df-121">説明</span><span class="sxs-lookup"><span data-stu-id="c55df-121">Explanation</span></span>  
 <span data-ttu-id="c55df-122">この警告イベントは、SSO が SSO データベースとの接続を再び確立したが、当初変更を指定したアカウントが有効ではなくなったため、再生ファイルで指定された (SSO データベースでの) 変更を実行できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c55df-122">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to make a change (in the SSO database) specified in the replay file because the account that originally specified the change is no longer valid.</span></span>  
  
 <span data-ttu-id="c55df-123">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c55df-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="c55df-124">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="c55df-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c55df-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c55df-125">User Action</span></span>  
 <span data-ttu-id="c55df-126">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="c55df-126">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="c55df-127">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="c55df-127">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="c55df-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="c55df-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="c55df-129">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c55df-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="c55df-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="c55df-130">Password Synchronization</span></span>](../core/password-synchronization2.md)