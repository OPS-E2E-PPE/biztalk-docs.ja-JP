---
title: シングル サインオン:イベント 10693 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 672bac7d-0ccc-4a42-a49d-57e387f4cf3a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cef53efa210d38d145dd4859fd3363e853a71fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397361"
---
# <a name="single-sign-on-event-10693"></a><span data-ttu-id="f5a68-102">シングル サインオン:イベント 10693</span><span class="sxs-lookup"><span data-stu-id="f5a68-102">Single Sign-On: Event 10693</span></span>
## <a name="details"></a><span data-ttu-id="f5a68-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f5a68-103">Details</span></span>  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f5a68-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f5a68-104">Product Name</span></span>   |                                       <span data-ttu-id="f5a68-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f5a68-105">Enterprise Single Sign-On</span></span>                                        |
| <span data-ttu-id="f5a68-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f5a68-106">Product Version</span></span> |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    <span data-ttu-id="f5a68-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f5a68-107">Event ID</span></span>     |                                                 <span data-ttu-id="f5a68-108">10693</span><span class="sxs-lookup"><span data-stu-id="f5a68-108">10693</span></span>                                                  |
|  <span data-ttu-id="f5a68-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f5a68-109">Event Source</span></span>   |                                                 <span data-ttu-id="f5a68-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f5a68-110">ENTSSO</span></span>                                                 |
|    <span data-ttu-id="f5a68-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f5a68-111">Component</span></span>    |                                                  <span data-ttu-id="f5a68-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="f5a68-112">N\A</span></span>                                                   |
|  <span data-ttu-id="f5a68-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f5a68-113">Symbolic Name</span></span>  |                                    <span data-ttu-id="f5a68-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span><span class="sxs-lookup"><span data-stu-id="f5a68-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span></span>                                    |
|  <span data-ttu-id="f5a68-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f5a68-115">Message Text</span></span>   | <span data-ttu-id="f5a68-116">再生を作成または進行状況の file.%r できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f5a68-116">Could not create the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="f5a68-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f5a68-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="f5a68-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="f5a68-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="f5a68-119">説明</span><span class="sxs-lookup"><span data-stu-id="f5a68-119">Explanation</span></span>  
 <span data-ttu-id="f5a68-120">この警告イベントは、SSO が SSO データベースへの接続が失われたときに再生や進行状況ファイルを作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f5a68-120">This Warning event indicates that SSO was unable to create a replay and\or progress file when connection to the SSO database was lost.</span></span>  

 <span data-ttu-id="f5a68-121">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5a68-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="f5a68-122">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="f5a68-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f5a68-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f5a68-123">User Action</span></span>  
 <span data-ttu-id="f5a68-124">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f5a68-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="f5a68-125">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5a68-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="f5a68-126">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f5a68-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f5a68-127">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f5a68-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f5a68-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="f5a68-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
