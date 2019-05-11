---
title: シングル サインオン:イベント 10696 |Microsoft Docs
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
ms.openlocfilehash: 364abc55edf749a01828b5188a0ba55ad2a151b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397327"
---
# <a name="single-sign-on-event-10696"></a><span data-ttu-id="57176-102">シングル サインオン:イベント 10696</span><span class="sxs-lookup"><span data-stu-id="57176-102">Single Sign-On: Event 10696</span></span>
## <a name="details"></a><span data-ttu-id="57176-103">詳細</span><span class="sxs-lookup"><span data-stu-id="57176-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="57176-104">製品名</span><span class="sxs-lookup"><span data-stu-id="57176-104">Product Name</span></span>   |                         <span data-ttu-id="57176-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="57176-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="57176-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="57176-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="57176-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="57176-107">Event ID</span></span>     |                                   <span data-ttu-id="57176-108">10696</span><span class="sxs-lookup"><span data-stu-id="57176-108">10696</span></span>                                   |
|  <span data-ttu-id="57176-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="57176-109">Event Source</span></span>   |                                  <span data-ttu-id="57176-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="57176-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="57176-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="57176-111">Component</span></span>    |                                    <span data-ttu-id="57176-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="57176-112">N\A</span></span>                                    |
|  <span data-ttu-id="57176-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="57176-113">Symbolic Name</span></span>  |                <span data-ttu-id="57176-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span><span class="sxs-lookup"><span data-stu-id="57176-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span></span>                |
|  <span data-ttu-id="57176-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="57176-115">Message Text</span></span>   | <span data-ttu-id="57176-116">進行状況 file.%r で破損が検出されました</span><span class="sxs-lookup"><span data-stu-id="57176-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="57176-117">ファイル名: %1</span><span class="sxs-lookup"><span data-stu-id="57176-117">File Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="57176-118">説明</span><span class="sxs-lookup"><span data-stu-id="57176-118">Explanation</span></span>  
 <span data-ttu-id="57176-119">このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、破損のため、進行状況ファイルを読み取ることができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="57176-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the progress file because of corruption.</span></span> <span data-ttu-id="57176-120">SSO では、進行状況ファイルを開くことはできません場合、が、最初の再生ファイルの先頭のレコードから開始されます。</span><span class="sxs-lookup"><span data-stu-id="57176-120">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  

 <span data-ttu-id="57176-121">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="57176-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="57176-122">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="57176-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="57176-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="57176-123">User Action</span></span>  
 <span data-ttu-id="57176-124">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="57176-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="57176-125">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="57176-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="57176-126">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="57176-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="57176-127">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="57176-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="57176-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="57176-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
