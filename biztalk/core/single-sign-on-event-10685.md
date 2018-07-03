---
title: 'シングル サインオン: イベント 10685 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b276432363f6073627aaa9033c2b78b730ccda1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992523"
---
# <a name="single-sign-on-event-10685"></a><span data-ttu-id="d80f4-102">シングル サインオン: イベント 10685</span><span class="sxs-lookup"><span data-stu-id="d80f4-102">Single Sign-On: Event 10685</span></span>
## <a name="details"></a><span data-ttu-id="d80f4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d80f4-103">Details</span></span>  

|                 |                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d80f4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d80f4-104">Product Name</span></span>   |                                      <span data-ttu-id="d80f4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d80f4-105">Enterprise Single Sign-On</span></span>                                       |
| <span data-ttu-id="d80f4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d80f4-106">Product Version</span></span> |                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                      |
|    <span data-ttu-id="d80f4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d80f4-107">Event ID</span></span>     |                                                <span data-ttu-id="d80f4-108">10685</span><span class="sxs-lookup"><span data-stu-id="d80f4-108">10685</span></span>                                                 |
|  <span data-ttu-id="d80f4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d80f4-109">Event Source</span></span>   |                                                <span data-ttu-id="d80f4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d80f4-110">ENTSSO</span></span>                                                |
|    <span data-ttu-id="d80f4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d80f4-111">Component</span></span>    |                                                 <span data-ttu-id="d80f4-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d80f4-112">N\A</span></span>                                                  |
|  <span data-ttu-id="d80f4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d80f4-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="d80f4-114">SSO_WARN_REPLAY_CANNOT_OPEN</span><span class="sxs-lookup"><span data-stu-id="d80f4-114">SSO_WARN_REPLAY_CANNOT_OPEN</span></span>                                      |
|  <span data-ttu-id="d80f4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d80f4-115">Message Text</span></span>   | <span data-ttu-id="d80f4-116">再生ファイルまたは進行状況ファイルを開けませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="d80f4-116">Could not open the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="d80f4-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d80f4-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="d80f4-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="d80f4-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="d80f4-119">説明</span><span class="sxs-lookup"><span data-stu-id="d80f4-119">Explanation</span></span>  
 <span data-ttu-id="d80f4-120">この警告イベントは、SSO が SSO データベースとの接続を再び確立したが、再生ファイルまたは進行状況ファイルを開くことができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d80f4-120">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay or progress file.</span></span> <span data-ttu-id="d80f4-121">SSO で再生ファイルを開くことができなかった場合、次の再生ファイルが処理されます。</span><span class="sxs-lookup"><span data-stu-id="d80f4-121">If SSO cannot open a replay file, it will proceed to the next replay file.</span></span>  

 <span data-ttu-id="d80f4-122">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d80f4-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="d80f4-123">進行状況ファイルは、SSO データベースとの接続が再び切断された場合に、部分的に再生ファイルを再生することによって、どの程度 SSO を通じて再生ファイルを読み取ることができたかを示します。</span><span class="sxs-lookup"><span data-stu-id="d80f4-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is lost again part-way through playing back of a replay file.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d80f4-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d80f4-124">User Action</span></span>  
 <span data-ttu-id="d80f4-125">この警告イベントを解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d80f4-125">To resolve this Warning event, do the following:</span></span>  

- <span data-ttu-id="d80f4-126">システムおよびアプリケーションのイベント ログで関連するイベントを確認し、SSO が SSO データベースに接続できなかった理由を特定します。</span><span class="sxs-lookup"><span data-stu-id="d80f4-126">You should check the System and Application Event logs for associated events to determine why SSO was unable to contact the SSO database.</span></span>  

  <span data-ttu-id="d80f4-127">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="d80f4-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="d80f4-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d80f4-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="d80f4-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d80f4-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
