---
title: シングル サインオン:イベント 10726 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12fbac2d-30ca-4f4c-989b-d770b0f623d9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c14aea83bef1213eeda4bf56e4de7e400ee3e56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258979"
---
# <a name="single-sign-on-event-10726"></a><span data-ttu-id="c7d8d-102">シングル サインオン:イベント 10726</span><span class="sxs-lookup"><span data-stu-id="c7d8d-102">Single Sign-On: Event 10726</span></span>
## <a name="details"></a><span data-ttu-id="c7d8d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c7d8d-103">Details</span></span>  

|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c7d8d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c7d8d-104">Product Name</span></span>   |                                                             <span data-ttu-id="c7d8d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c7d8d-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="c7d8d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c7d8d-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="c7d8d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c7d8d-107">Event ID</span></span>     |                                                                       <span data-ttu-id="c7d8d-108">10726</span><span class="sxs-lookup"><span data-stu-id="c7d8d-108">10726</span></span>                                                                        |
|  <span data-ttu-id="c7d8d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c7d8d-109">Event Source</span></span>   |                                                                       <span data-ttu-id="c7d8d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c7d8d-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="c7d8d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c7d8d-111">Component</span></span>    |                                                                        <span data-ttu-id="c7d8d-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="c7d8d-112">N\A</span></span>                                                                         |
|  <span data-ttu-id="c7d8d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c7d8d-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="c7d8d-114">SSO_ERROR_REPLAY_CORRUPTION</span><span class="sxs-lookup"><span data-stu-id="c7d8d-114">SSO_ERROR_REPLAY_CORRUPTION</span></span>                                                             |
|  <span data-ttu-id="c7d8d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c7d8d-115">Message Text</span></span>   | <span data-ttu-id="c7d8d-116">再生または進行状況 file.%r で破損が検出されました</span><span class="sxs-lookup"><span data-stu-id="c7d8d-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="c7d8d-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c7d8d-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="c7d8d-118">追加データ: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="c7d8d-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="c7d8d-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="c7d8d-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="c7d8d-120">説明</span><span class="sxs-lookup"><span data-stu-id="c7d8d-120">Explanation</span></span>  
 <span data-ttu-id="c7d8d-121">このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、破損のため、再生ファイルを読み取ることができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-121">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="c7d8d-122">SSO で再生ファイルを開くことはできない場合は、(存在する場合)、[次へ] の再生ファイルに進みます。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-122">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="c7d8d-123">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="c7d8d-124">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c7d8d-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c7d8d-125">User Action</span></span>  
 <span data-ttu-id="c7d8d-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="c7d8d-127">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-127">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="c7d8d-128">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-128">Delete the replay file.</span></span>  

  <span data-ttu-id="c7d8d-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7d8d-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="c7d8d-130">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c7d8d-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="c7d8d-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="c7d8d-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
