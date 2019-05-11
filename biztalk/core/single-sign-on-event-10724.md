---
title: シングル サインオン:イベント 10724 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5494af19164c6c2621196ccd481d8510be58794
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303313"
---
# <a name="single-sign-on-event-10724"></a><span data-ttu-id="5a689-102">シングル サインオン:イベント 10724</span><span class="sxs-lookup"><span data-stu-id="5a689-102">Single Sign-On: Event 10724</span></span>
## <a name="details"></a><span data-ttu-id="5a689-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5a689-103">Details</span></span>  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5a689-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5a689-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="5a689-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5a689-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="5a689-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5a689-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="5a689-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5a689-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="5a689-108">10724</span><span class="sxs-lookup"><span data-stu-id="5a689-108">10724</span></span>                                                                                                |
|  <span data-ttu-id="5a689-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5a689-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="5a689-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5a689-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="5a689-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5a689-111">Component</span></span>    |                                                                                                <span data-ttu-id="5a689-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="5a689-112">N\A</span></span>                                                                                                 |
|  <span data-ttu-id="5a689-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5a689-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="5a689-114">SSO_ERROR_REPLAY_SECURITY_2</span><span class="sxs-lookup"><span data-stu-id="5a689-114">SSO_ERROR_REPLAY_SECURITY_2</span></span>                                                                                     |
|  <span data-ttu-id="5a689-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5a689-115">Message Text</span></span>   | <span data-ttu-id="5a689-116">再生または進行ファイルでのセキュリティが元の value.%r から変更されました</span><span class="sxs-lookup"><span data-stu-id="5a689-116">The security on the replay or progress file has been changed from its original value.%r</span></span><br /><br /> <span data-ttu-id="5a689-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5a689-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="5a689-118">現在のファイルのセキュリティ: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="5a689-118">Current File Security: %2%r</span></span><br /><br /> <span data-ttu-id="5a689-119">元のファイルのセキュリティ: %3</span><span class="sxs-lookup"><span data-stu-id="5a689-119">Original File Security: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="5a689-120">説明</span><span class="sxs-lookup"><span data-stu-id="5a689-120">Explanation</span></span>  
 <span data-ttu-id="5a689-121">このエラー イベントは、または進行ファイルでのセキュリティが変更されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="5a689-121">This Error event indicates that the security on the replay or progress files has been changed.</span></span>  

 <span data-ttu-id="5a689-122">再生ファイルは、再生ファイルのディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5a689-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="5a689-123">既定では、SSO サービス アカウントを使用して、再生ファイルと再生ファイルのディレクトリの両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="5a689-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="5a689-124">SSO は、変更が行われていないことを再生ファイルと再生ファイル ディレクトリのセキュリティ構成が作成後かを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a689-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="5a689-125">再生ファイルのディレクトリは、別のアカウントで作成されている場合、パスワード同期がそのディレクトリ内で再生ファイルを作成しようとしたときにこのエラーが返されますことができます。</span><span class="sxs-lookup"><span data-stu-id="5a689-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="5a689-126">ユーザーが再生ファイルと再生ファイル ディレクトリのセキュリティ構成を変更されないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a689-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5a689-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5a689-127">User Action</span></span>  
 <span data-ttu-id="5a689-128">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a689-128">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="5a689-129">再生ファイルの作成に使用するアカウントのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a689-129">Check permission for the account used to create the replay files.</span></span> <span data-ttu-id="5a689-130">これは、通常、SSO システム アカウントです。</span><span class="sxs-lookup"><span data-stu-id="5a689-130">This is typically the SSO system account.</span></span>  

  <span data-ttu-id="5a689-131">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a689-131">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="5a689-132">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5a689-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="5a689-133">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="5a689-133">Password Synchronization</span></span>](../core/password-synchronization2.md)
