---
title: シングル サインオン:イベント 10691 |Microsoft Docs
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
ms.openlocfilehash: 6042996195e9584729fbf3303a22b6560ed47578
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397340"
---
# <a name="single-sign-on-event-10691"></a><span data-ttu-id="ecbf1-102">シングル サインオン:イベント 10691</span><span class="sxs-lookup"><span data-stu-id="ecbf1-102">Single Sign-On: Event 10691</span></span>
## <a name="details"></a><span data-ttu-id="ecbf1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ecbf1-103">Details</span></span>  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ecbf1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ecbf1-104">Product Name</span></span>   |                                          <span data-ttu-id="ecbf1-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ecbf1-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="ecbf1-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ecbf1-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    <span data-ttu-id="ecbf1-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ecbf1-107">Event ID</span></span>     |                                                    <span data-ttu-id="ecbf1-108">10691</span><span class="sxs-lookup"><span data-stu-id="ecbf1-108">10691</span></span>                                                    |
|  <span data-ttu-id="ecbf1-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ecbf1-109">Event Source</span></span>   |                                                   <span data-ttu-id="ecbf1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ecbf1-110">ENTSSO</span></span>                                                    |
|    <span data-ttu-id="ecbf1-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ecbf1-111">Component</span></span>    |                                                     <span data-ttu-id="ecbf1-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="ecbf1-112">N\A</span></span>                                                     |
|  <span data-ttu-id="ecbf1-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ecbf1-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="ecbf1-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="ecbf1-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span></span>                                        |
|  <span data-ttu-id="ecbf1-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ecbf1-115">Message Text</span></span>   | <span data-ttu-id="ecbf1-116">再生 file.%r で破損が検出されました</span><span class="sxs-lookup"><span data-stu-id="ecbf1-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="ecbf1-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="ecbf1-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="ecbf1-118">追加データ: %2</span><span class="sxs-lookup"><span data-stu-id="ecbf1-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="ecbf1-119">説明</span><span class="sxs-lookup"><span data-stu-id="ecbf1-119">Explanation</span></span>  
 <span data-ttu-id="ecbf1-120">このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、対応する進行状況ファイルとの不一致により、再生ファイルを開くことができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay file because of a mismatch with the corresponding progress file.</span></span> <span data-ttu-id="ecbf1-121">SSO で再生ファイルを開くことはできない場合は、(存在する場合)、[次へ] の再生ファイルに進みます。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-121">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="ecbf1-122">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="ecbf1-123">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ecbf1-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ecbf1-124">User Action</span></span>  
 <span data-ttu-id="ecbf1-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="ecbf1-126">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-126">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="ecbf1-127">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-127">Delete the replay file.</span></span>  

  <span data-ttu-id="ecbf1-128">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="ecbf1-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="ecbf1-129">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ecbf1-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="ecbf1-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="ecbf1-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
