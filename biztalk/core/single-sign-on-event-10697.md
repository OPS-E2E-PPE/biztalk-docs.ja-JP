---
title: シングル サインオン:イベント 10697 |Microsoft Docs
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
ms.openlocfilehash: f18e8ba525f742226f2f38efd285dd58f6896e24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397310"
---
# <a name="single-sign-on-event-10697"></a><span data-ttu-id="67b0f-102">シングル サインオン:イベント 10697</span><span class="sxs-lookup"><span data-stu-id="67b0f-102">Single Sign-On: Event 10697</span></span>
## <a name="details"></a><span data-ttu-id="67b0f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67b0f-103">Details</span></span>  

|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="67b0f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67b0f-104">Product Name</span></span>   |                                           <span data-ttu-id="67b0f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="67b0f-105">Enterprise Single Sign-On</span></span>                                           |
| <span data-ttu-id="67b0f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67b0f-106">Product Version</span></span> |                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                           |
|    <span data-ttu-id="67b0f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67b0f-107">Event ID</span></span>     |                                                     <span data-ttu-id="67b0f-108">10697</span><span class="sxs-lookup"><span data-stu-id="67b0f-108">10697</span></span>                                                     |
|  <span data-ttu-id="67b0f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67b0f-109">Event Source</span></span>   |                                                    <span data-ttu-id="67b0f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="67b0f-110">ENTSSO</span></span>                                                     |
|    <span data-ttu-id="67b0f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67b0f-111">Component</span></span>    |                                                      <span data-ttu-id="67b0f-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="67b0f-112">N\A</span></span>                                                      |
|  <span data-ttu-id="67b0f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67b0f-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="67b0f-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="67b0f-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span></span>                                        |
|  <span data-ttu-id="67b0f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67b0f-115">Message Text</span></span>   | <span data-ttu-id="67b0f-116">進行状況 file.%r で破損が検出されました</span><span class="sxs-lookup"><span data-stu-id="67b0f-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="67b0f-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="67b0f-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="67b0f-118">追加データ: %2</span><span class="sxs-lookup"><span data-stu-id="67b0f-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="67b0f-119">説明</span><span class="sxs-lookup"><span data-stu-id="67b0f-119">Explanation</span></span>  
 <span data-ttu-id="67b0f-120">このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、対応する再生ファイルとの不一致により進行状況ファイルを開くことができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="67b0f-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the progress file because of a mismatch with the corresponding replay file.</span></span> <span data-ttu-id="67b0f-121">SSO では、進行状況ファイルを開くことはできません場合、が、最初の再生ファイルの先頭のレコードから開始されます。</span><span class="sxs-lookup"><span data-stu-id="67b0f-121">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  

 <span data-ttu-id="67b0f-122">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="67b0f-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="67b0f-123">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="67b0f-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="67b0f-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67b0f-124">User Action</span></span>  
 <span data-ttu-id="67b0f-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67b0f-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="67b0f-126">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="67b0f-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="67b0f-127">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="67b0f-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="67b0f-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="67b0f-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="67b0f-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="67b0f-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
