---
title: 'シングル サインオン: イベント 10718 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4bf86f4db59033b1ee4202c739ffeda43a587e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271786"
---
# <a name="single-sign-on-event-10718"></a><span data-ttu-id="ebf4a-102">シングル サインオン: イベント 10718</span><span class="sxs-lookup"><span data-stu-id="ebf4a-102">Single Sign-On: Event 10718</span></span>
## <a name="details"></a><span data-ttu-id="ebf4a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ebf4a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebf4a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ebf4a-104">Product Name</span></span>|<span data-ttu-id="ebf4a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ebf4a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ebf4a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ebf4a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ebf4a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ebf4a-107">Event ID</span></span>|<span data-ttu-id="ebf4a-108">10718</span><span class="sxs-lookup"><span data-stu-id="ebf4a-108">10718</span></span>|  
|<span data-ttu-id="ebf4a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ebf4a-109">Event Source</span></span>|<span data-ttu-id="ebf4a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ebf4a-110">ENTSSO</span></span>|  
|<span data-ttu-id="ebf4a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ebf4a-111">Component</span></span>|<span data-ttu-id="ebf4a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ebf4a-112">N\A</span></span>|  
|<span data-ttu-id="ebf4a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ebf4a-113">Symbolic Name</span></span>|<span data-ttu-id="ebf4a-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="ebf4a-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span></span>|  
|<span data-ttu-id="ebf4a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ebf4a-115">Message Text</span></span>|<span data-ttu-id="ebf4a-116">再生ファイルまたは進行ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="ebf4a-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="ebf4a-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ebf4a-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="ebf4a-118">クリアなアダプタ名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ebf4a-118">Clear Adapter Name: %2%r</span></span><br /><br /> <span data-ttu-id="ebf4a-119">アダプター名を暗号化解除: %3</span><span class="sxs-lookup"><span data-stu-id="ebf4a-119">Decrypted Adapter Name: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ebf4a-120">説明</span><span class="sxs-lookup"><span data-stu-id="ebf4a-120">Explanation</span></span>  
 <span data-ttu-id="ebf4a-121">このエラー イベントは、再生ファイルまたは進行状況ファイルで破損が検出されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-121">This Error event indicates that corruption was detected in the replay or progress file.</span></span>  
  
 <span data-ttu-id="ebf4a-122">再生ファイルは特定のパスワード同期アダプターに対して格納され、その特定のアダプターとして再生できます。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-122">A replay file is stored for a particular password sync adapter so it can be played back as that particular adapter.</span></span> <span data-ttu-id="ebf4a-123">アダプター名は、クリア形式と暗号化形式の両方で格納されます。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-123">The adapter name is stored in both clear and encrypted forms.</span></span> <span data-ttu-id="ebf4a-124">このメッセージは、再生ファイルが再生のために暗号化解除されたときに、暗号化解除されたアダプター名がアダプター名と一致しなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-124">This message indicates that when the replay file was decrypted for playback the decrypted adapter name did not match the adapter name.</span></span> <span data-ttu-id="ebf4a-125">これは、再生ファイルが破損していること、または改ざんされた可能性があることを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-125">This can suggest that there has been some corruption or possible tampering with the replay file.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ebf4a-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ebf4a-126">User Action</span></span>  
 <span data-ttu-id="ebf4a-127">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-127">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="ebf4a-128">再生ファイルの内容が変更されている可能性がある理由を調べ、バックアップが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-128">Determine why the contents of the replay file might have been modified, see if a backup exists.</span></span>  
  
-   <span data-ttu-id="ebf4a-129">SSO マスター シークレットが変更されたかどうか、または SSO サービス アカウントが変更されたかどうかを確認します。これらは暗号化の動作に影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-129">Check if the SSO master secret was changed or the SSO service account was changed, this could affect encryption behavior.</span></span>  
  
-   <span data-ttu-id="ebf4a-130">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-130">Delete the replay file.</span></span>  
  
 <span data-ttu-id="ebf4a-131">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf4a-131">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="ebf4a-132">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ebf4a-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="ebf4a-133">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="ebf4a-133">Password Synchronization</span></span>](../core/password-synchronization2.md)