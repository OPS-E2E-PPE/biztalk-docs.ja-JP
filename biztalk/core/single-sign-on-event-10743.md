---
title: シングル サインオン:イベント 10743 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10ec09fac8f7b555cb189e032b94bf0c8f8da839
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278026"
---
# <a name="single-sign-on-event-10743"></a><span data-ttu-id="e5ae2-102">シングル サインオン:イベント 10743</span><span class="sxs-lookup"><span data-stu-id="e5ae2-102">Single Sign-On: Event 10743</span></span>
## <a name="details"></a><span data-ttu-id="e5ae2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e5ae2-103">Details</span></span>  

|                 |                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e5ae2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e5ae2-104">Product Name</span></span>   |                                                                   <span data-ttu-id="e5ae2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e5ae2-105">Enterprise Single Sign-On</span></span>                                                                    |
| <span data-ttu-id="e5ae2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e5ae2-106">Product Version</span></span> |                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    <span data-ttu-id="e5ae2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e5ae2-107">Event ID</span></span>     |                                                                             <span data-ttu-id="e5ae2-108">10743</span><span class="sxs-lookup"><span data-stu-id="e5ae2-108">10743</span></span>                                                                              |
|  <span data-ttu-id="e5ae2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e5ae2-109">Event Source</span></span>   |                                                                             <span data-ttu-id="e5ae2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e5ae2-110">ENTSSO</span></span>                                                                             |
|    <span data-ttu-id="e5ae2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e5ae2-111">Component</span></span>    |                                                                              <span data-ttu-id="e5ae2-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="e5ae2-112">N\A</span></span>                                                                               |
|  <span data-ttu-id="e5ae2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e5ae2-113">Symbolic Name</span></span>  |                                                                    <span data-ttu-id="e5ae2-114">SSO_ERROR_REPLAY_STOPPED</span><span class="sxs-lookup"><span data-stu-id="e5ae2-114">SSO_ERROR_REPLAY_STOPPED</span></span>                                                                    |
|  <span data-ttu-id="e5ae2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e5ae2-115">Message Text</span></span>   | <span data-ttu-id="e5ae2-116">Errors.%r により保存された外部パスワード変更の再生が停止しました</span><span class="sxs-lookup"><span data-stu-id="e5ae2-116">Replay of stored external password changes stopped due to errors.%r</span></span><br /><br /> <span data-ttu-id="e5ae2-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="e5ae2-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="e5ae2-118">追加データ: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="e5ae2-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="e5ae2-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="e5ae2-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="e5ae2-120">説明</span><span class="sxs-lookup"><span data-stu-id="e5ae2-120">Explanation</span></span>  
 <span data-ttu-id="e5ae2-121">イベントは、その再生を示します。 このエラーには、エラーのために停止する外部パスワード変更が保存されます。</span><span class="sxs-lookup"><span data-stu-id="e5ae2-121">This Error event indicates that replay of stored external password changes stopped due to errors.</span></span>  

 <span data-ttu-id="e5ae2-122">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5ae2-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="e5ae2-123">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="e5ae2-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e5ae2-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e5ae2-124">User Action</span></span>  
 <span data-ttu-id="e5ae2-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5ae2-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="e5ae2-126">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5ae2-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="e5ae2-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5ae2-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="e5ae2-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="e5ae2-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="e5ae2-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="e5ae2-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
