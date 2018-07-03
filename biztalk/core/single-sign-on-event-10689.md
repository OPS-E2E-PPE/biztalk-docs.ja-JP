---
title: 'シングル サインオン: イベント 10689 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79e4e31f-18e4-4f52-9466-18e58842942f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 277acc742cd49804559ba2c8e7aa157fb3c7092d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022808"
---
# <a name="single-sign-on-event-10689"></a><span data-ttu-id="ae2a2-102">シングル サインオン: イベント 10689</span><span class="sxs-lookup"><span data-stu-id="ae2a2-102">Single Sign-On: Event 10689</span></span>
## <a name="details"></a><span data-ttu-id="ae2a2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ae2a2-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="ae2a2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ae2a2-104">Product Name</span></span>   |                         <span data-ttu-id="ae2a2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ae2a2-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="ae2a2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ae2a2-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="ae2a2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ae2a2-107">Event ID</span></span>     |                                   <span data-ttu-id="ae2a2-108">10689</span><span class="sxs-lookup"><span data-stu-id="ae2a2-108">10689</span></span>                                   |
|  <span data-ttu-id="ae2a2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ae2a2-109">Event Source</span></span>   |                                  <span data-ttu-id="ae2a2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ae2a2-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="ae2a2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ae2a2-111">Component</span></span>    |                                    <span data-ttu-id="ae2a2-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ae2a2-112">N\A</span></span>                                    |
|  <span data-ttu-id="ae2a2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ae2a2-113">Symbolic Name</span></span>  |                 <span data-ttu-id="ae2a2-114">SSO_ERROR_REPLAY_INCORRECT_RECORD_VERSION</span><span class="sxs-lookup"><span data-stu-id="ae2a2-114">SSO_ERROR_REPLAY_INCORRECT_RECORD_VERSION</span></span>                 |
|  <span data-ttu-id="ae2a2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ae2a2-115">Message Text</span></span>   | <span data-ttu-id="ae2a2-116">再生ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="ae2a2-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="ae2a2-117">再生ファイル: %1</span><span class="sxs-lookup"><span data-stu-id="ae2a2-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="ae2a2-118">説明</span><span class="sxs-lookup"><span data-stu-id="ae2a2-118">Explanation</span></span>  
 <span data-ttu-id="ae2a2-119">このエラー イベントは、SSO が SSO データベースとの接続を再確立したが、破損のために再生ファイルを読み取れなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="ae2a2-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="ae2a2-120">SSO で再生ファイルを開くことができない場合、次の再生ファイルに進みます (次の再生ファイルがある場合)。</span><span class="sxs-lookup"><span data-stu-id="ae2a2-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="ae2a2-121">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae2a2-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="ae2a2-122">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="ae2a2-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ae2a2-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ae2a2-123">User Action</span></span>  
 <span data-ttu-id="ae2a2-124">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ae2a2-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="ae2a2-125">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae2a2-125">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="ae2a2-126">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ae2a2-126">Delete the replay file.</span></span>  

  <span data-ttu-id="ae2a2-127">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="ae2a2-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="ae2a2-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ae2a2-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="ae2a2-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="ae2a2-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
