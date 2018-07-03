---
title: 'シングル サインオン: イベント 10691 |Microsoft Docs'
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
ms.openlocfilehash: 69acc99acd002f23d3d6e02430d58fb88f9651a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009899"
---
# <a name="single-sign-on-event-10691"></a><span data-ttu-id="c84a6-102">シングル サインオン: イベント 10691</span><span class="sxs-lookup"><span data-stu-id="c84a6-102">Single Sign-On: Event 10691</span></span>
## <a name="details"></a><span data-ttu-id="c84a6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c84a6-103">Details</span></span>  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c84a6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c84a6-104">Product Name</span></span>   |                                          <span data-ttu-id="c84a6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c84a6-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="c84a6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c84a6-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    <span data-ttu-id="c84a6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c84a6-107">Event ID</span></span>     |                                                    <span data-ttu-id="c84a6-108">10691</span><span class="sxs-lookup"><span data-stu-id="c84a6-108">10691</span></span>                                                    |
|  <span data-ttu-id="c84a6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c84a6-109">Event Source</span></span>   |                                                   <span data-ttu-id="c84a6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c84a6-110">ENTSSO</span></span>                                                    |
|    <span data-ttu-id="c84a6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c84a6-111">Component</span></span>    |                                                     <span data-ttu-id="c84a6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c84a6-112">N\A</span></span>                                                     |
|  <span data-ttu-id="c84a6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c84a6-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="c84a6-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="c84a6-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span></span>                                        |
|  <span data-ttu-id="c84a6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c84a6-115">Message Text</span></span>   | <span data-ttu-id="c84a6-116">再生ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="c84a6-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="c84a6-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="c84a6-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="c84a6-118">追加データ: %2</span><span class="sxs-lookup"><span data-stu-id="c84a6-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="c84a6-119">説明</span><span class="sxs-lookup"><span data-stu-id="c84a6-119">Explanation</span></span>  
 <span data-ttu-id="c84a6-120">このエラー イベントは、SSO が SSO データベースとの接続を再び確立したが、対応する進行状況ファイルとの不一致が原因で再生ファイルを開けなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c84a6-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay file because of a mismatch with the corresponding progress file.</span></span> <span data-ttu-id="c84a6-121">SSO で再生ファイルを開くことができない場合、次の再生ファイルに進みます (次の再生ファイルがある場合)。</span><span class="sxs-lookup"><span data-stu-id="c84a6-121">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="c84a6-122">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c84a6-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="c84a6-123">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="c84a6-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c84a6-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c84a6-124">User Action</span></span>  
 <span data-ttu-id="c84a6-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c84a6-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="c84a6-126">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="c84a6-126">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="c84a6-127">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c84a6-127">Delete the replay file.</span></span>  

  <span data-ttu-id="c84a6-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="c84a6-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c84a6-129">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c84a6-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="c84a6-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="c84a6-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
