---
title: 'シングル サインオン: イベント 10693 |Microsoft Docs'
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
ms.openlocfilehash: 8f9dd254fd81d54f0c60a2ea8b0a143e94ddd516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009483"
---
# <a name="single-sign-on-event-10693"></a><span data-ttu-id="ab2cb-102">シングル サインオン: イベント 10693</span><span class="sxs-lookup"><span data-stu-id="ab2cb-102">Single Sign-On: Event 10693</span></span>
## <a name="details"></a><span data-ttu-id="ab2cb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ab2cb-103">Details</span></span>  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ab2cb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ab2cb-104">Product Name</span></span>   |                                       <span data-ttu-id="ab2cb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ab2cb-105">Enterprise Single Sign-On</span></span>                                        |
| <span data-ttu-id="ab2cb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ab2cb-106">Product Version</span></span> |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    <span data-ttu-id="ab2cb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ab2cb-107">Event ID</span></span>     |                                                 <span data-ttu-id="ab2cb-108">10693</span><span class="sxs-lookup"><span data-stu-id="ab2cb-108">10693</span></span>                                                  |
|  <span data-ttu-id="ab2cb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ab2cb-109">Event Source</span></span>   |                                                 <span data-ttu-id="ab2cb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ab2cb-110">ENTSSO</span></span>                                                 |
|    <span data-ttu-id="ab2cb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ab2cb-111">Component</span></span>    |                                                  <span data-ttu-id="ab2cb-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ab2cb-112">N\A</span></span>                                                   |
|  <span data-ttu-id="ab2cb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ab2cb-113">Symbolic Name</span></span>  |                                    <span data-ttu-id="ab2cb-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span><span class="sxs-lookup"><span data-stu-id="ab2cb-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span></span>                                    |
|  <span data-ttu-id="ab2cb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ab2cb-115">Message Text</span></span>   | <span data-ttu-id="ab2cb-116">再生を作成または進行状況の file.%r できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ab2cb-116">Could not create the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="ab2cb-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ab2cb-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="ab2cb-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="ab2cb-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="ab2cb-119">説明</span><span class="sxs-lookup"><span data-stu-id="ab2cb-119">Explanation</span></span>  
 <span data-ttu-id="ab2cb-120">この警告イベントは、SSO データベースへの接続が失われたときに、SSO が再生ファイルや進行状況ファイルを作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ab2cb-120">This Warning event indicates that SSO was unable to create a replay and\or progress file when connection to the SSO database was lost.</span></span>  

 <span data-ttu-id="ab2cb-121">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab2cb-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="ab2cb-122">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="ab2cb-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ab2cb-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ab2cb-123">User Action</span></span>  
 <span data-ttu-id="ab2cb-124">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab2cb-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="ab2cb-125">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab2cb-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="ab2cb-126">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="ab2cb-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="ab2cb-127">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ab2cb-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="ab2cb-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="ab2cb-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
