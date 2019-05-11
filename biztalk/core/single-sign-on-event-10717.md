---
title: シングル サインオン:イベント 10717 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47ff4ceb707d1cbd353f88c9335d226a9a0158d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397166"
---
# <a name="single-sign-on-event-10717"></a><span data-ttu-id="ab8fd-102">シングル サインオン:イベント 10717</span><span class="sxs-lookup"><span data-stu-id="ab8fd-102">Single Sign-On: Event 10717</span></span>
## <a name="details"></a><span data-ttu-id="ab8fd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ab8fd-103">Details</span></span>  

|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ab8fd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ab8fd-104">Product Name</span></span>   |                                                            <span data-ttu-id="ab8fd-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ab8fd-105">Enterprise Single Sign-On</span></span>                                                             |
| <span data-ttu-id="ab8fd-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ab8fd-106">Product Version</span></span> |                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                            |
|    <span data-ttu-id="ab8fd-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ab8fd-107">Event ID</span></span>     |                                                                      <span data-ttu-id="ab8fd-108">10717</span><span class="sxs-lookup"><span data-stu-id="ab8fd-108">10717</span></span>                                                                       |
|  <span data-ttu-id="ab8fd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ab8fd-109">Event Source</span></span>   |                                                                      <span data-ttu-id="ab8fd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ab8fd-110">ENTSSO</span></span>                                                                      |
|    <span data-ttu-id="ab8fd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ab8fd-111">Component</span></span>    |                                                                       <span data-ttu-id="ab8fd-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="ab8fd-112">N\A</span></span>                                                                        |
|  <span data-ttu-id="ab8fd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ab8fd-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="ab8fd-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span><span class="sxs-lookup"><span data-stu-id="ab8fd-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span></span>                                                          |
|  <span data-ttu-id="ab8fd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ab8fd-115">Message Text</span></span>   | <span data-ttu-id="ab8fd-116">再生ファイルの directory.%r を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-116">Failed to create the replay files directory.%r</span></span><br /><br /> <span data-ttu-id="ab8fd-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="ab8fd-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="ab8fd-118">再生ファイル ディレクトリ: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="ab8fd-118">Replay Files Directory: %2%r</span></span><br /><br /> <span data-ttu-id="ab8fd-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="ab8fd-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="ab8fd-120">説明</span><span class="sxs-lookup"><span data-stu-id="ab8fd-120">Explanation</span></span>  
 <span data-ttu-id="ab8fd-121">このエラー イベントは、再生ファイルのディレクトリが作成しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-121">This Error event indicates that a replay files directory could not be created.</span></span>  

 <span data-ttu-id="ab8fd-122">パスワード同期アダプターから SSO サービスで、パスワードの変更を受信したときに、SSO データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-122">When password changes are received by the SSO service from a password sync adapter, they are stored in the SSO database.</span></span> <span data-ttu-id="ab8fd-123">SSO データベースが一時的に利用できない場合、パスワードの変更が再生ファイルにローカルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-123">If the SSO database is temporarily unavailable, the password changes are stored locally in replay files.</span></span> <span data-ttu-id="ab8fd-124">再生ファイルは、再生ファイルのディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-124">Replay files are stored in the replay files directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ab8fd-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ab8fd-125">User Action</span></span>  
 <span data-ttu-id="ab8fd-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="ab8fd-127">再生ファイル ディレクトリが表示され、1 つのチェックでは存在しない、SSO サービスと同じサービス アカウントを使用して手動で作成しようとしません。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-127">Check the replay files directory, if one does not exist, attempt to create it manually using the same service account as the SSO service.</span></span> <span data-ttu-id="ab8fd-128">SSO サービスと同じアカウントを使用して、再生ファイル ディレクトリを作成できない場合は、そのアカウントのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-128">If you cannot create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  

  <span data-ttu-id="ab8fd-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab8fd-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="ab8fd-130">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ab8fd-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="ab8fd-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="ab8fd-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
