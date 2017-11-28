---
title: "シングル サインオン: イベント 10723 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00536f3e-26d6-4e19-a98f-e687bb1b6611
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1bb94e6bb528d58d895b528135674a3e47f83b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10723"></a><span data-ttu-id="83074-102">シングル サインオン: イベント 10723</span><span class="sxs-lookup"><span data-stu-id="83074-102">Single Sign-On: Event 10723</span></span>
## <a name="details"></a><span data-ttu-id="83074-103">詳細</span><span class="sxs-lookup"><span data-stu-id="83074-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83074-104">製品名</span><span class="sxs-lookup"><span data-stu-id="83074-104">Product Name</span></span>|<span data-ttu-id="83074-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="83074-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="83074-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="83074-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="83074-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="83074-107">Event ID</span></span>|<span data-ttu-id="83074-108">10723</span><span class="sxs-lookup"><span data-stu-id="83074-108">10723</span></span>|  
|<span data-ttu-id="83074-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="83074-109">Event Source</span></span>|<span data-ttu-id="83074-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="83074-110">ENTSSO</span></span>|  
|<span data-ttu-id="83074-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="83074-111">Component</span></span>|<span data-ttu-id="83074-112">N\A</span><span class="sxs-lookup"><span data-stu-id="83074-112">N\A</span></span>|  
|<span data-ttu-id="83074-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="83074-113">Symbolic Name</span></span>|<span data-ttu-id="83074-114">SSO_ERROR_REPLAY_SECURITY_1</span><span class="sxs-lookup"><span data-stu-id="83074-114">SSO_ERROR_REPLAY_SECURITY_1</span></span>|  
|<span data-ttu-id="83074-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="83074-115">Message Text</span></span>|<span data-ttu-id="83074-116">再生ファイルのディレクトリのセキュリティが、再生ファイルまたは進行ファイルのセキュリティに一致しません。%r</span><span class="sxs-lookup"><span data-stu-id="83074-116">The security on the replay files directory does not match the security on the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="83074-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="83074-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="83074-118">ファイルのセキュリティ: %2 %r</span><span class="sxs-lookup"><span data-stu-id="83074-118">File Security: %2%r</span></span><br /><br /> <span data-ttu-id="83074-119">ディレクトリ セキュリティ: %3</span><span class="sxs-lookup"><span data-stu-id="83074-119">Directory Security: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="83074-120">説明</span><span class="sxs-lookup"><span data-stu-id="83074-120">Explanation</span></span>  
 <span data-ttu-id="83074-121">このエラー イベントは、再生ファイルのディレクトリのセキュリティが再生ファイルまたは進行ファイルのセキュリティに一致していないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="83074-121">This Error event indicates that the security on the replay files directory does not match the security on the replay or progress file.</span></span>  
  
 <span data-ttu-id="83074-122">再生ファイルは再生ファイルのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="83074-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="83074-123">既定では、再生ファイルと再生ファイルのディレクトリの作成に SSO サービス アカウントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="83074-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="83074-124">SSO により、再生ファイルと再生ファイルのディレクトリの作成以降、そのセキュリティ構成が変更されていないことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="83074-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="83074-125">再生ファイルのディレクトリが異なるアカウントで作成された場合、パスワード同期によりそのディレクトリで再生ファイルを作成しようとすると、このエラーが返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="83074-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="83074-126">ユーザーは再生ファイルと再生ファイルのディレクトリのセキュリティ構成を変更しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="83074-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="83074-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="83074-127">User Action</span></span>  
 <span data-ttu-id="83074-128">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83074-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="83074-129">再生ファイルのディレクトリの作成に使用されるアカウントを確認します。</span><span class="sxs-lookup"><span data-stu-id="83074-129">Check the account used to create the replay files directory.</span></span> <span data-ttu-id="83074-130">ディレクトリが空である場合、パスワード同期の実行をもう一度試します。</span><span class="sxs-lookup"><span data-stu-id="83074-130">If the directory is empty, attempt running password sync again.</span></span> <span data-ttu-id="83074-131">SSO サービスと同じサービス アカウントを使用したディレクトリの再作成が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="83074-131">It may be necessary to re-create the directory using the same service account as the SSO service.</span></span> <span data-ttu-id="83074-132">SSO サービスと同じサービス アカウントを使用して再生ファイルのディレクトリを再作成できない場合、そのアカウントのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="83074-132">If you cannot re-create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  
  
 <span data-ttu-id="83074-133">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83074-133">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="83074-134">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="83074-134">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="83074-135">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="83074-135">Password Synchronization</span></span>](../core/password-synchronization2.md)