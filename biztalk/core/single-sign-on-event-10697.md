---
title: 'シングル サインオン: イベント 10697 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4263ecbd-939e-4374-b0b6-aada3b2af900
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991d17351ddbaa998c0f7c90774e1615f3bc472e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980403"
---
# <a name="single-sign-on-event-10697"></a><span data-ttu-id="275fc-102">シングル サインオン: イベント 10697</span><span class="sxs-lookup"><span data-stu-id="275fc-102">Single Sign-On: Event 10697</span></span>
## <a name="details"></a><span data-ttu-id="275fc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="275fc-103">Details</span></span>  

|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="275fc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="275fc-104">Product Name</span></span>   |                                           <span data-ttu-id="275fc-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="275fc-105">Enterprise Single Sign-On</span></span>                                           |
| <span data-ttu-id="275fc-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="275fc-106">Product Version</span></span> |                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                           |
|    <span data-ttu-id="275fc-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="275fc-107">Event ID</span></span>     |                                                     <span data-ttu-id="275fc-108">10697</span><span class="sxs-lookup"><span data-stu-id="275fc-108">10697</span></span>                                                     |
|  <span data-ttu-id="275fc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="275fc-109">Event Source</span></span>   |                                                    <span data-ttu-id="275fc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="275fc-110">ENTSSO</span></span>                                                     |
|    <span data-ttu-id="275fc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="275fc-111">Component</span></span>    |                                                      <span data-ttu-id="275fc-112">N\A</span><span class="sxs-lookup"><span data-stu-id="275fc-112">N\A</span></span>                                                      |
|  <span data-ttu-id="275fc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="275fc-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="275fc-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="275fc-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span></span>                                        |
|  <span data-ttu-id="275fc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="275fc-115">Message Text</span></span>   | <span data-ttu-id="275fc-116">進行ファイルで破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="275fc-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="275fc-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="275fc-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="275fc-118">追加データ: %2</span><span class="sxs-lookup"><span data-stu-id="275fc-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="275fc-119">説明</span><span class="sxs-lookup"><span data-stu-id="275fc-119">Explanation</span></span>  
 <span data-ttu-id="275fc-120">このエラー イベントは、SSO が SSO データベースとの接続を再び確立したが、対応する再生ファイルとの不一致が原因で進行状況ファイルを開けなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="275fc-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the progress file because of a mismatch with the corresponding replay file.</span></span> <span data-ttu-id="275fc-121">進行ファイルを開くことができない場合は、最初の再生ファイルの先頭のレコードから開始されます。</span><span class="sxs-lookup"><span data-stu-id="275fc-121">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  

 <span data-ttu-id="275fc-122">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="275fc-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="275fc-123">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="275fc-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="275fc-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="275fc-124">User Action</span></span>  
 <span data-ttu-id="275fc-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="275fc-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="275fc-126">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="275fc-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="275fc-127">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="275fc-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="275fc-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="275fc-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="275fc-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="275fc-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
