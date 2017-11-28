---
title: "シングル サインオン: イベント 10717 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70195251b599daebd50b57f0b137dd026dd032e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10717"></a><span data-ttu-id="2844a-102">シングル サインオン: イベント 10717</span><span class="sxs-lookup"><span data-stu-id="2844a-102">Single Sign-On: Event 10717</span></span>
## <a name="details"></a><span data-ttu-id="2844a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2844a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2844a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2844a-104">Product Name</span></span>|<span data-ttu-id="2844a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2844a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2844a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2844a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2844a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2844a-107">Event ID</span></span>|<span data-ttu-id="2844a-108">10717</span><span class="sxs-lookup"><span data-stu-id="2844a-108">10717</span></span>|  
|<span data-ttu-id="2844a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2844a-109">Event Source</span></span>|<span data-ttu-id="2844a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2844a-110">ENTSSO</span></span>|  
|<span data-ttu-id="2844a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2844a-111">Component</span></span>|<span data-ttu-id="2844a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="2844a-112">N\A</span></span>|  
|<span data-ttu-id="2844a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2844a-113">Symbolic Name</span></span>|<span data-ttu-id="2844a-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span><span class="sxs-lookup"><span data-stu-id="2844a-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span></span>|  
|<span data-ttu-id="2844a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2844a-115">Message Text</span></span>|<span data-ttu-id="2844a-116">再生ファイル ディレクトリを作成できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="2844a-116">Failed to create the replay files directory.%r</span></span><br /><br /> <span data-ttu-id="2844a-117">クライアント ユーザー: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2844a-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="2844a-118">再生ファイル ディレクトリ: %2 %r</span><span class="sxs-lookup"><span data-stu-id="2844a-118">Replay Files Directory: %2%r</span></span><br /><br /> <span data-ttu-id="2844a-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="2844a-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2844a-120">説明</span><span class="sxs-lookup"><span data-stu-id="2844a-120">Explanation</span></span>  
 <span data-ttu-id="2844a-121">このエラー イベントは、再生ファイル ディレクトリを作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="2844a-121">This Error event indicates that a replay files directory could not be created.</span></span>  
  
 <span data-ttu-id="2844a-122">SSO サービスがパスワード同期アダプターからパスワード変更を受信すると、パスワード変更は SSO データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2844a-122">When password changes are received by the SSO service from a password sync adapter, they are stored in the SSO database.</span></span> <span data-ttu-id="2844a-123">SSO データベースが一時的に使用できない場合は、パスワード変更はローカルの再生ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="2844a-123">If the SSO database is temporarily unavailable, the password changes are stored locally in replay files.</span></span> <span data-ttu-id="2844a-124">再生ファイルは再生ファイルのディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="2844a-124">Replay files are stored in the replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2844a-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2844a-125">User Action</span></span>  
 <span data-ttu-id="2844a-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2844a-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="2844a-127">再生ファイル ディレクトリを確認し、再生ファイル ディレクトリが存在しない場合は、SSO サービスと同じサービス アカウントを使用して、手動で再生ファイル ディレクトリを作成してみます。</span><span class="sxs-lookup"><span data-stu-id="2844a-127">Check the replay files directory, if one does not exist, attempt to create it manually using the same service account as the SSO service.</span></span> <span data-ttu-id="2844a-128">SSO サービスと同じアカウントを使用して再生ファイル ディレクトリを作成できない場合は、そのアカウントのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="2844a-128">If you cannot create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  
  
 <span data-ttu-id="2844a-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2844a-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="2844a-130">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2844a-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="2844a-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="2844a-131">Password Synchronization</span></span>](../core/password-synchronization2.md)