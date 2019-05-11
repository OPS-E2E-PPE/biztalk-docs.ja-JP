---
title: シングル サインオン:イベント 10685 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f73b44e334c60a59211b59a46f5c9a2dacffa8ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397397"
---
# <a name="single-sign-on-event-10685"></a><span data-ttu-id="bee10-102">シングル サインオン:イベント 10685</span><span class="sxs-lookup"><span data-stu-id="bee10-102">Single Sign-On: Event 10685</span></span>
## <a name="details"></a><span data-ttu-id="bee10-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bee10-103">Details</span></span>  

|                 |                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bee10-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bee10-104">Product Name</span></span>   |                                      <span data-ttu-id="bee10-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bee10-105">Enterprise Single Sign-On</span></span>                                       |
| <span data-ttu-id="bee10-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bee10-106">Product Version</span></span> |                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                      |
|    <span data-ttu-id="bee10-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bee10-107">Event ID</span></span>     |                                                <span data-ttu-id="bee10-108">10685</span><span class="sxs-lookup"><span data-stu-id="bee10-108">10685</span></span>                                                 |
|  <span data-ttu-id="bee10-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bee10-109">Event Source</span></span>   |                                                <span data-ttu-id="bee10-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bee10-110">ENTSSO</span></span>                                                |
|    <span data-ttu-id="bee10-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bee10-111">Component</span></span>    |                                                 <span data-ttu-id="bee10-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="bee10-112">N\A</span></span>                                                  |
|  <span data-ttu-id="bee10-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bee10-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="bee10-114">SSO_WARN_REPLAY_CANNOT_OPEN</span><span class="sxs-lookup"><span data-stu-id="bee10-114">SSO_WARN_REPLAY_CANNOT_OPEN</span></span>                                      |
|  <span data-ttu-id="bee10-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bee10-115">Message Text</span></span>   | <span data-ttu-id="bee10-116">再生を開くまたは file.%r 進行状況できませんでした。</span><span class="sxs-lookup"><span data-stu-id="bee10-116">Could not open the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="bee10-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bee10-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="bee10-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="bee10-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="bee10-119">説明</span><span class="sxs-lookup"><span data-stu-id="bee10-119">Explanation</span></span>  
 <span data-ttu-id="bee10-120">この警告イベントは、SSO が SSO データベースとの接続が再び確立したが、再生ファイルまたは進行状況ファイルを開くことができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bee10-120">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay or progress file.</span></span> <span data-ttu-id="bee10-121">SSO で再生ファイルを開くことはできない場合は、これは次の再生ファイルに進みます。</span><span class="sxs-lookup"><span data-stu-id="bee10-121">If SSO cannot open a replay file, it will proceed to the next replay file.</span></span>  

 <span data-ttu-id="bee10-122">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="bee10-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="bee10-123">進行状況ファイルは、どの程度 SSO を通じて再生ファイルのケースで連絡先 SSO データベースとが読めるように失われたもう一度再生ファイルの再生段階を示します。</span><span class="sxs-lookup"><span data-stu-id="bee10-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is lost again part-way through playing back of a replay file.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bee10-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bee10-124">User Action</span></span>  
 <span data-ttu-id="bee10-125">この警告イベントを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bee10-125">To resolve this Warning event, do the following:</span></span>  

- <span data-ttu-id="bee10-126">SSO が SSO データベースに接続できない理由を確認する関連するイベントのシステムおよびアプリケーション イベント ログを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bee10-126">You should check the System and Application Event logs for associated events to determine why SSO was unable to contact the SSO database.</span></span>  

  <span data-ttu-id="bee10-127">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="bee10-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="bee10-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="bee10-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="bee10-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="bee10-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
