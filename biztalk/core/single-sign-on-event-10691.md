---
title: 'シングル サインオン: イベント 10691 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fcefb49-c068-41e9-850d-99864c0899bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da914bff656ff63e65cd041e57e291beea5128e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270698"
---
# <a name="single-sign-on-event-10691"></a><span data-ttu-id="8f920-102">シングル サインオン: イベント 10691</span><span class="sxs-lookup"><span data-stu-id="8f920-102">Single Sign-On: Event 10691</span></span>
## <a name="details"></a><span data-ttu-id="8f920-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8f920-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f920-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8f920-104">Product Name</span></span>|<span data-ttu-id="8f920-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8f920-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8f920-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8f920-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8f920-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8f920-107">Event ID</span></span>|<span data-ttu-id="8f920-108">10691</span><span class="sxs-lookup"><span data-stu-id="8f920-108">10691</span></span>|  
|<span data-ttu-id="8f920-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8f920-109">Event Source</span></span>|<span data-ttu-id="8f920-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8f920-110">ENTSSO</span></span>|  
|<span data-ttu-id="8f920-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8f920-111">Component</span></span>|<span data-ttu-id="8f920-112">N\A</span><span class="sxs-lookup"><span data-stu-id="8f920-112">N\A</span></span>|  
|<span data-ttu-id="8f920-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8f920-113">Symbolic Name</span></span>|<span data-ttu-id="8f920-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="8f920-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span></span>|  
|<span data-ttu-id="8f920-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8f920-115">Message Text</span></span>|<span data-ttu-id="8f920-116">再生ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="8f920-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="8f920-117">再生ファイル: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8f920-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="8f920-118">追加データ: %2</span><span class="sxs-lookup"><span data-stu-id="8f920-118">Additional Data: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f920-119">説明</span><span class="sxs-lookup"><span data-stu-id="8f920-119">Explanation</span></span>  
 <span data-ttu-id="8f920-120">このエラー イベントは、SSO が SSO データベースとの接続を再び確立したが、対応する進行状況ファイルとの不一致が原因で再生ファイルを開けなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8f920-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay file because of a mismatch with the corresponding progress file.</span></span> <span data-ttu-id="8f920-121">SSO で再生ファイルを開くことができない場合、次の再生ファイルに進みます (次の再生ファイルがある場合)。</span><span class="sxs-lookup"><span data-stu-id="8f920-121">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  
  
 <span data-ttu-id="8f920-122">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f920-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="8f920-123">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="8f920-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f920-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8f920-124">User Action</span></span>  
 <span data-ttu-id="8f920-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8f920-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="8f920-126">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f920-126">Check System and Application event logs for associated events.</span></span>  
  
-   <span data-ttu-id="8f920-127">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="8f920-127">Delete the replay file.</span></span>  
  
 <span data-ttu-id="8f920-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="8f920-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="8f920-129">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8f920-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="8f920-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="8f920-130">Password Synchronization</span></span>](../core/password-synchronization2.md)