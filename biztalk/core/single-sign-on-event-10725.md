---
title: シングル サインオン:イベント 10725 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89218d73-bda0-4e98-a578-cd244af79041
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b47a3a9ac9c9537515dc2baf3affe6e4a729bb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267549"
---
# <a name="single-sign-on-event-10725"></a><span data-ttu-id="3a84c-102">シングル サインオン:イベント 10725</span><span class="sxs-lookup"><span data-stu-id="3a84c-102">Single Sign-On: Event 10725</span></span>
## <a name="details"></a><span data-ttu-id="3a84c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3a84c-103">Details</span></span>  

|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3a84c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3a84c-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="3a84c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3a84c-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="3a84c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3a84c-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="3a84c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3a84c-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="3a84c-108">10725</span><span class="sxs-lookup"><span data-stu-id="3a84c-108">10725</span></span>                                                                                                  |
|  <span data-ttu-id="3a84c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3a84c-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="3a84c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3a84c-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="3a84c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3a84c-111">Component</span></span>    |                                                                                                   <span data-ttu-id="3a84c-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="3a84c-112">N\A</span></span>                                                                                                   |
|  <span data-ttu-id="3a84c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3a84c-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="3a84c-114">SSO_ERROR_REPLAY_SECURITY_3</span><span class="sxs-lookup"><span data-stu-id="3a84c-114">SSO_ERROR_REPLAY_SECURITY_3</span></span>                                                                                       |
|  <span data-ttu-id="3a84c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3a84c-115">Message Text</span></span>   | <span data-ttu-id="3a84c-116">再生ファイルのディレクトリのセキュリティが再生または進行状況 file.%r のセキュリティと一致しません</span><span class="sxs-lookup"><span data-stu-id="3a84c-116">The security on the replay files directory does not match the security on the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="3a84c-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3a84c-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="3a84c-118">ファイルのセキュリティ: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="3a84c-118">File Security: %2%r</span></span><br /><br /> <span data-ttu-id="3a84c-119">ディレクトリ セキュリティ: %3</span><span class="sxs-lookup"><span data-stu-id="3a84c-119">Directory Security: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="3a84c-120">説明</span><span class="sxs-lookup"><span data-stu-id="3a84c-120">Explanation</span></span>  
 <span data-ttu-id="3a84c-121">このエラー イベントは、再生ファイルのディレクトリのセキュリティでは、再生ファイルまたは進行ファイルでのセキュリティが一致しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3a84c-121">This Error event indicates that the security on the replay files directory does not match the security on the replay or progress file.</span></span>  

 <span data-ttu-id="3a84c-122">再生ファイルは、再生ファイルのディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3a84c-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="3a84c-123">既定では、SSO サービス アカウントを使用して、再生ファイルと再生ファイルのディレクトリの両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="3a84c-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="3a84c-124">SSO は、変更が行われていないことを再生ファイルと再生ファイル ディレクトリのセキュリティ構成が作成後かを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a84c-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="3a84c-125">再生ファイルのディレクトリは、別のアカウントで作成されている場合、パスワード同期がそのディレクトリ内で再生ファイルを作成しようとしたときにこのエラーが返されますことができます。</span><span class="sxs-lookup"><span data-stu-id="3a84c-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="3a84c-126">ユーザーが再生ファイルと再生ファイル ディレクトリのセキュリティ構成を変更されないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a84c-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3a84c-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3a84c-127">User Action</span></span>  
 <span data-ttu-id="3a84c-128">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3a84c-128">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="3a84c-129">再生ファイルのディレクトリを作成するために使用するアカウントを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a84c-129">Check the account used to create the replay files directory.</span></span> <span data-ttu-id="3a84c-130">ディレクトリが空の場合は、パスワード同期をもう一度実行していることを試みます。</span><span class="sxs-lookup"><span data-stu-id="3a84c-130">If the directory is empty, attempt running password sync again.</span></span> <span data-ttu-id="3a84c-131">SSO サービスと同じサービス アカウントを使用してディレクトリを再作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a84c-131">It may be necessary to re-create the directory using the same service account as the SSO service.</span></span> <span data-ttu-id="3a84c-132">SSO サービスと同じアカウントを使用して、再生ファイル ディレクトリを再作成することはできませんがある場合は、そのアカウントのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="3a84c-132">If you cannot re-create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  

  <span data-ttu-id="3a84c-133">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a84c-133">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="3a84c-134">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3a84c-134">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="3a84c-135">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="3a84c-135">Password Synchronization</span></span>](../core/password-synchronization2.md)
