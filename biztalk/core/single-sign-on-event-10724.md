---
title: "シングル サインオン: イベント 10724 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd9e65b18b66f119e3cc2acf7f078f17466e46b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10724"></a><span data-ttu-id="b5837-102">シングル サインオン: イベント 10724</span><span class="sxs-lookup"><span data-stu-id="b5837-102">Single Sign-On: Event 10724</span></span>
## <a name="details"></a><span data-ttu-id="b5837-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b5837-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5837-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b5837-104">Product Name</span></span>|<span data-ttu-id="b5837-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b5837-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b5837-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b5837-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b5837-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b5837-107">Event ID</span></span>|<span data-ttu-id="b5837-108">10724</span><span class="sxs-lookup"><span data-stu-id="b5837-108">10724</span></span>|  
|<span data-ttu-id="b5837-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b5837-109">Event Source</span></span>|<span data-ttu-id="b5837-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b5837-110">ENTSSO</span></span>|  
|<span data-ttu-id="b5837-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b5837-111">Component</span></span>|<span data-ttu-id="b5837-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b5837-112">N\A</span></span>|  
|<span data-ttu-id="b5837-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b5837-113">Symbolic Name</span></span>|<span data-ttu-id="b5837-114">SSO_ERROR_REPLAY_SECURITY_2</span><span class="sxs-lookup"><span data-stu-id="b5837-114">SSO_ERROR_REPLAY_SECURITY_2</span></span>|  
|<span data-ttu-id="b5837-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b5837-115">Message Text</span></span>|<span data-ttu-id="b5837-116">再生ファイルまたは進行状況ファイルのセキュリティが元の値から変更されました。%r</span><span class="sxs-lookup"><span data-stu-id="b5837-116">The security on the replay or progress file has been changed from its original value.%r</span></span><br /><br /> <span data-ttu-id="b5837-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b5837-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="b5837-118">現在のファイルのセキュリティ: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b5837-118">Current File Security: %2%r</span></span><br /><br /> <span data-ttu-id="b5837-119">元のファイル セキュリティ: %3</span><span class="sxs-lookup"><span data-stu-id="b5837-119">Original File Security: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5837-120">説明</span><span class="sxs-lookup"><span data-stu-id="b5837-120">Explanation</span></span>  
 <span data-ttu-id="b5837-121">このエラー イベントは、再生ファイルまたは進行状況ファイルのセキュリティが変更されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="b5837-121">This Error event indicates that the security on the replay or progress files has been changed.</span></span>  
  
 <span data-ttu-id="b5837-122">再生ファイルは再生ファイルのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b5837-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="b5837-123">既定では、再生ファイルと再生ファイルのディレクトリの作成に SSO サービス アカウントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5837-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="b5837-124">SSO により、再生ファイルと再生ファイルのディレクトリの作成以降、そのセキュリティ構成が変更されていないことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="b5837-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="b5837-125">再生ファイルのディレクトリが異なるアカウントで作成された場合、パスワード同期によりそのディレクトリで再生ファイルを作成しようとすると、このエラーが返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b5837-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="b5837-126">ユーザーは再生ファイルと再生ファイルのディレクトリのセキュリティ構成を変更しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b5837-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5837-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b5837-127">User Action</span></span>  
 <span data-ttu-id="b5837-128">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b5837-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="b5837-129">再生ファイルの作成に使用されたアカウントのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5837-129">Check permission for the account used to create the replay files.</span></span> <span data-ttu-id="b5837-130">これは、通常、SSO システム アカウントです。</span><span class="sxs-lookup"><span data-stu-id="b5837-130">This is typically the SSO system account.</span></span>  
  
 <span data-ttu-id="b5837-131">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5837-131">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="b5837-132">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b5837-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="b5837-133">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="b5837-133">Password Synchronization</span></span>](../core/password-synchronization2.md)