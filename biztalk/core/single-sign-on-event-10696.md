---
title: 'シングル サインオン: イベント 10696 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dff6d08-8a1f-4137-bda7-55271071da55
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1a2b704b45774e0489f9c765cee45326bf0ff59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271794"
---
# <a name="single-sign-on-event-10696"></a><span data-ttu-id="8bc55-102">シングル サインオン: イベント 10696</span><span class="sxs-lookup"><span data-stu-id="8bc55-102">Single Sign-On: Event 10696</span></span>
## <a name="details"></a><span data-ttu-id="8bc55-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8bc55-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8bc55-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8bc55-104">Product Name</span></span>|<span data-ttu-id="8bc55-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8bc55-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8bc55-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8bc55-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8bc55-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8bc55-107">Event ID</span></span>|<span data-ttu-id="8bc55-108">10696</span><span class="sxs-lookup"><span data-stu-id="8bc55-108">10696</span></span>|  
|<span data-ttu-id="8bc55-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8bc55-109">Event Source</span></span>|<span data-ttu-id="8bc55-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8bc55-110">ENTSSO</span></span>|  
|<span data-ttu-id="8bc55-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8bc55-111">Component</span></span>|<span data-ttu-id="8bc55-112">N\A</span><span class="sxs-lookup"><span data-stu-id="8bc55-112">N\A</span></span>|  
|<span data-ttu-id="8bc55-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8bc55-113">Symbolic Name</span></span>|<span data-ttu-id="8bc55-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span><span class="sxs-lookup"><span data-stu-id="8bc55-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span></span>|  
|<span data-ttu-id="8bc55-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8bc55-115">Message Text</span></span>|<span data-ttu-id="8bc55-116">進行ファイルで破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="8bc55-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="8bc55-117">ファイル名: %1</span><span class="sxs-lookup"><span data-stu-id="8bc55-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8bc55-118">説明</span><span class="sxs-lookup"><span data-stu-id="8bc55-118">Explanation</span></span>  
 <span data-ttu-id="8bc55-119">このエラー イベントは、SSO が SSO データベースとの接続を再び確立したが、進行状況ファイルが破損しているために進行状況ファイルを読み取れなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8bc55-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the progress file because of corruption.</span></span> <span data-ttu-id="8bc55-120">進行ファイルを開くことができない場合は、最初の再生ファイルの先頭のレコードから開始されます。</span><span class="sxs-lookup"><span data-stu-id="8bc55-120">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  
  
 <span data-ttu-id="8bc55-121">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc55-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="8bc55-122">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="8bc55-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8bc55-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8bc55-123">User Action</span></span>  
 <span data-ttu-id="8bc55-124">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8bc55-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="8bc55-125">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bc55-125">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="8bc55-126">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="8bc55-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="8bc55-127">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8bc55-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="8bc55-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="8bc55-128">Password Synchronization</span></span>](../core/password-synchronization2.md)