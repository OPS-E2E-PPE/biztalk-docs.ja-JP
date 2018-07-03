---
title: 'シングル サインオン: イベント 10718 |Microsoft Docs'
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
ms.openlocfilehash: 958753d50d15662cd138ea5460c121eefcac8a98
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004987"
---
# <a name="single-sign-on-event-10718"></a><span data-ttu-id="d39d9-102">シングル サインオン: イベント 10718</span><span class="sxs-lookup"><span data-stu-id="d39d9-102">Single Sign-On: Event 10718</span></span>
## <a name="details"></a><span data-ttu-id="d39d9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d39d9-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d39d9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d39d9-104">Product Name</span></span>   |                                                                     <span data-ttu-id="d39d9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d39d9-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="d39d9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d39d9-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="d39d9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d39d9-107">Event ID</span></span>     |                                                                               <span data-ttu-id="d39d9-108">10718</span><span class="sxs-lookup"><span data-stu-id="d39d9-108">10718</span></span>                                                                               |
|  <span data-ttu-id="d39d9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d39d9-109">Event Source</span></span>   |                                                                              <span data-ttu-id="d39d9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d39d9-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="d39d9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d39d9-111">Component</span></span>    |                                                                                <span data-ttu-id="d39d9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d39d9-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="d39d9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d39d9-113">Symbolic Name</span></span>  |                                                                <span data-ttu-id="d39d9-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="d39d9-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span></span>                                                                 |
|  <span data-ttu-id="d39d9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d39d9-115">Message Text</span></span>   | <span data-ttu-id="d39d9-116">再生ファイルまたは進行ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="d39d9-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="d39d9-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d39d9-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="d39d9-118">クリアなアダプタ名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="d39d9-118">Clear Adapter Name: %2%r</span></span><br /><br /> <span data-ttu-id="d39d9-119">アダプター名を復号化: %3</span><span class="sxs-lookup"><span data-stu-id="d39d9-119">Decrypted Adapter Name: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="d39d9-120">説明</span><span class="sxs-lookup"><span data-stu-id="d39d9-120">Explanation</span></span>  
 <span data-ttu-id="d39d9-121">このエラー イベントは、再生ファイルまたは進行状況ファイルで破損が検出されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="d39d9-121">This Error event indicates that corruption was detected in the replay or progress file.</span></span>  

 <span data-ttu-id="d39d9-122">再生ファイルは特定のパスワード同期アダプターに対して格納され、その特定のアダプターとして再生できます。</span><span class="sxs-lookup"><span data-stu-id="d39d9-122">A replay file is stored for a particular password sync adapter so it can be played back as that particular adapter.</span></span> <span data-ttu-id="d39d9-123">アダプター名は、クリア形式と暗号化形式の両方で格納されます。</span><span class="sxs-lookup"><span data-stu-id="d39d9-123">The adapter name is stored in both clear and encrypted forms.</span></span> <span data-ttu-id="d39d9-124">このメッセージは、再生ファイルが再生のために暗号化解除されたときに、暗号化解除されたアダプター名がアダプター名と一致しなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d39d9-124">This message indicates that when the replay file was decrypted for playback the decrypted adapter name did not match the adapter name.</span></span> <span data-ttu-id="d39d9-125">これは、再生ファイルが破損していること、または改ざんされた可能性があることを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="d39d9-125">This can suggest that there has been some corruption or possible tampering with the replay file.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d39d9-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d39d9-126">User Action</span></span>  
 <span data-ttu-id="d39d9-127">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d39d9-127">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="d39d9-128">再生ファイルの内容が変更されている可能性がある理由を調べ、バックアップが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d39d9-128">Determine why the contents of the replay file might have been modified, see if a backup exists.</span></span>  

- <span data-ttu-id="d39d9-129">SSO マスター シークレットが変更されたかどうか、または SSO サービス アカウントが変更されたかどうかを確認します。これらは暗号化の動作に影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d39d9-129">Check if the SSO master secret was changed or the SSO service account was changed, this could affect encryption behavior.</span></span>  

- <span data-ttu-id="d39d9-130">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="d39d9-130">Delete the replay file.</span></span>  

  <span data-ttu-id="d39d9-131">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d39d9-131">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="d39d9-132">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d39d9-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="d39d9-133">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d39d9-133">Password Synchronization</span></span>](../core/password-synchronization2.md)
