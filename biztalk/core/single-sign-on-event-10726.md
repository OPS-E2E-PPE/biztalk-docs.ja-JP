---
title: 'シングル サインオン: イベント 10726 |Microsoft Docs'
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
ms.openlocfilehash: 2799f35d233685ef07b446d2ed6ae2c7c931678c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990795"
---
# <a name="single-sign-on-event-10726"></a><span data-ttu-id="51084-102">シングル サインオン: イベント 10726</span><span class="sxs-lookup"><span data-stu-id="51084-102">Single Sign-On: Event 10726</span></span>
## <a name="details"></a><span data-ttu-id="51084-103">詳細</span><span class="sxs-lookup"><span data-stu-id="51084-103">Details</span></span>  

|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="51084-104">製品名</span><span class="sxs-lookup"><span data-stu-id="51084-104">Product Name</span></span>   |                                                             <span data-ttu-id="51084-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="51084-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="51084-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="51084-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="51084-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="51084-107">Event ID</span></span>     |                                                                       <span data-ttu-id="51084-108">10726</span><span class="sxs-lookup"><span data-stu-id="51084-108">10726</span></span>                                                                        |
|  <span data-ttu-id="51084-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="51084-109">Event Source</span></span>   |                                                                       <span data-ttu-id="51084-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="51084-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="51084-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="51084-111">Component</span></span>    |                                                                        <span data-ttu-id="51084-112">N\A</span><span class="sxs-lookup"><span data-stu-id="51084-112">N\A</span></span>                                                                         |
|  <span data-ttu-id="51084-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="51084-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="51084-114">SSO_ERROR_REPLAY_CORRUPTION</span><span class="sxs-lookup"><span data-stu-id="51084-114">SSO_ERROR_REPLAY_CORRUPTION</span></span>                                                             |
|  <span data-ttu-id="51084-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="51084-115">Message Text</span></span>   | <span data-ttu-id="51084-116">再生ファイルまたは進行ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="51084-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="51084-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="51084-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="51084-118">追加データ: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="51084-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="51084-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="51084-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="51084-120">説明</span><span class="sxs-lookup"><span data-stu-id="51084-120">Explanation</span></span>  
 <span data-ttu-id="51084-121">このエラー イベントは、SSO が SSO データベースとの接続を再確立したが、破損のために再生ファイルを読み取れなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="51084-121">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="51084-122">SSO で再生ファイルを開くことができない場合、次の再生ファイルに進みます (次の再生ファイルがある場合)。</span><span class="sxs-lookup"><span data-stu-id="51084-122">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="51084-123">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="51084-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="51084-124">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="51084-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="51084-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="51084-125">User Action</span></span>  
 <span data-ttu-id="51084-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="51084-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="51084-127">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="51084-127">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="51084-128">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="51084-128">Delete the replay file.</span></span>  

  <span data-ttu-id="51084-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51084-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="51084-130">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="51084-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="51084-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="51084-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
