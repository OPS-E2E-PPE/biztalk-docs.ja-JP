---
title: シングル サインオン:イベント 10718 |Microsoft Docs
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
ms.openlocfilehash: 331d78687d7948a4f37ab3b16e4a95e42c5e209c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397211"
---
# <a name="single-sign-on-event-10718"></a><span data-ttu-id="f468b-102">シングル サインオン:イベント 10718</span><span class="sxs-lookup"><span data-stu-id="f468b-102">Single Sign-On: Event 10718</span></span>
## <a name="details"></a><span data-ttu-id="f468b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f468b-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f468b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f468b-104">Product Name</span></span>   |                                                                     <span data-ttu-id="f468b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f468b-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="f468b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f468b-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="f468b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f468b-107">Event ID</span></span>     |                                                                               <span data-ttu-id="f468b-108">10718</span><span class="sxs-lookup"><span data-stu-id="f468b-108">10718</span></span>                                                                               |
|  <span data-ttu-id="f468b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f468b-109">Event Source</span></span>   |                                                                              <span data-ttu-id="f468b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f468b-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="f468b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f468b-111">Component</span></span>    |                                                                                <span data-ttu-id="f468b-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="f468b-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="f468b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f468b-113">Symbolic Name</span></span>  |                                                                <span data-ttu-id="f468b-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="f468b-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span></span>                                                                 |
|  <span data-ttu-id="f468b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f468b-115">Message Text</span></span>   | <span data-ttu-id="f468b-116">再生または進行状況 file.%r で破損が検出されました</span><span class="sxs-lookup"><span data-stu-id="f468b-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="f468b-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f468b-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="f468b-118">クリアなアダプタ名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="f468b-118">Clear Adapter Name: %2%r</span></span><br /><br /> <span data-ttu-id="f468b-119">アダプター名を復号化: %3</span><span class="sxs-lookup"><span data-stu-id="f468b-119">Decrypted Adapter Name: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="f468b-120">説明</span><span class="sxs-lookup"><span data-stu-id="f468b-120">Explanation</span></span>  
 <span data-ttu-id="f468b-121">このエラー イベントは、再生ファイルまたは進行ファイルで破損が検出されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f468b-121">This Error event indicates that corruption was detected in the replay or progress file.</span></span>  

 <span data-ttu-id="f468b-122">再生ファイルは、特定のパスワード同期アダプターの格納されているため、その特定のアダプターとして再生できます。</span><span class="sxs-lookup"><span data-stu-id="f468b-122">A replay file is stored for a particular password sync adapter so it can be played back as that particular adapter.</span></span> <span data-ttu-id="f468b-123">アダプター名は、フォームのクリアと暗号化の両方に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f468b-123">The adapter name is stored in both clear and encrypted forms.</span></span> <span data-ttu-id="f468b-124">このメッセージは、こと、再生ファイルが再生の復号化、復号化されたアダプター名が一致しません、アダプター名を示します。</span><span class="sxs-lookup"><span data-stu-id="f468b-124">This message indicates that when the replay file was decrypted for playback the decrypted adapter name did not match the adapter name.</span></span> <span data-ttu-id="f468b-125">これにより、されているといくつかの破損または再生ファイルの可能な改ざんは提示されます。</span><span class="sxs-lookup"><span data-stu-id="f468b-125">This can suggest that there has been some corruption or possible tampering with the replay file.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f468b-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f468b-126">User Action</span></span>  
 <span data-ttu-id="f468b-127">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f468b-127">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="f468b-128">再生ファイルの内容をされた可能性がありますを決定する、変更は、バックアップが存在するかどうかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f468b-128">Determine why the contents of the replay file might have been modified, see if a backup exists.</span></span>  

- <span data-ttu-id="f468b-129">チェックの場合は、SSO マスター シークレットが変更されたか、SSO サービス アカウントが変更された、暗号化の動作に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f468b-129">Check if the SSO master secret was changed or the SSO service account was changed, this could affect encryption behavior.</span></span>  

- <span data-ttu-id="f468b-130">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="f468b-130">Delete the replay file.</span></span>  

  <span data-ttu-id="f468b-131">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f468b-131">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="f468b-132">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f468b-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f468b-133">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="f468b-133">Password Synchronization</span></span>](../core/password-synchronization2.md)
