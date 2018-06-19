---
title: 'シングル サインオン: イベント 10694 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75faca65-48d9-45f6-b079-2b612ef3de76
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c11d30b30f55c04b8f3023740a8e0f488c5762e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270642"
---
# <a name="single-sign-on-event-10694"></a><span data-ttu-id="b552a-102">シングル サインオン: イベント 10694</span><span class="sxs-lookup"><span data-stu-id="b552a-102">Single Sign-On: Event 10694</span></span>
## <a name="details"></a><span data-ttu-id="b552a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b552a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b552a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b552a-104">Product Name</span></span>|<span data-ttu-id="b552a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b552a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b552a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b552a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b552a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b552a-107">Event ID</span></span>|<span data-ttu-id="b552a-108">10694</span><span class="sxs-lookup"><span data-stu-id="b552a-108">10694</span></span>|  
|<span data-ttu-id="b552a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b552a-109">Event Source</span></span>|<span data-ttu-id="b552a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b552a-110">ENTSSO</span></span>|  
|<span data-ttu-id="b552a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b552a-111">Component</span></span>|<span data-ttu-id="b552a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b552a-112">N\A</span></span>|  
|<span data-ttu-id="b552a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b552a-113">Symbolic Name</span></span>|<span data-ttu-id="b552a-114">SSO_ERROR_REPLAY_INCORRECT_VERSION</span><span class="sxs-lookup"><span data-stu-id="b552a-114">SSO_ERROR_REPLAY_INCORRECT_VERSION</span></span>|  
|<span data-ttu-id="b552a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b552a-115">Message Text</span></span>|<span data-ttu-id="b552a-116">再生ファイルまたは進行ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="b552a-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="b552a-117">ファイル名: %1</span><span class="sxs-lookup"><span data-stu-id="b552a-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b552a-118">説明</span><span class="sxs-lookup"><span data-stu-id="b552a-118">Explanation</span></span>  
 <span data-ttu-id="b552a-119">このエラー イベントは、SSO が SSO データベースとの接続を再確立したが、破損のために再生ファイルを読み取れなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b552a-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="b552a-120">SSO で再生ファイルを開くことができない場合、次の再生ファイルに進みます (次の再生ファイルがある場合)。</span><span class="sxs-lookup"><span data-stu-id="b552a-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  
  
 <span data-ttu-id="b552a-121">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b552a-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="b552a-122">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="b552a-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b552a-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b552a-123">User Action</span></span>  
 <span data-ttu-id="b552a-124">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b552a-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="b552a-125">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="b552a-125">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="b552a-126">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="b552a-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b552a-127">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b552a-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="b552a-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="b552a-128">Password Synchronization</span></span>](../core/password-synchronization2.md)