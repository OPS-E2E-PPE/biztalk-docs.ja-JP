---
title: シングル サインオン:イベント 10688 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63fe4ac5-dc1d-4d5a-8ce3-40ed4556afcf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e760441481a5eddfd2d7d53294a8f6f4abade8fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397408"
---
# <a name="single-sign-on-event-10688"></a><span data-ttu-id="6049e-102">シングル サインオン:イベント 10688</span><span class="sxs-lookup"><span data-stu-id="6049e-102">Single Sign-On: Event 10688</span></span>
## <a name="details"></a><span data-ttu-id="6049e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6049e-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="6049e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6049e-104">Product Name</span></span>   |                         <span data-ttu-id="6049e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6049e-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="6049e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6049e-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="6049e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6049e-107">Event ID</span></span>     |                                   <span data-ttu-id="6049e-108">10688</span><span class="sxs-lookup"><span data-stu-id="6049e-108">10688</span></span>                                   |
|  <span data-ttu-id="6049e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6049e-109">Event Source</span></span>   |                                  <span data-ttu-id="6049e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6049e-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="6049e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6049e-111">Component</span></span>    |                                    <span data-ttu-id="6049e-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="6049e-112">N\A</span></span>                                    |
|  <span data-ttu-id="6049e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6049e-113">Symbolic Name</span></span>  |                   <span data-ttu-id="6049e-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span><span class="sxs-lookup"><span data-stu-id="6049e-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span></span>                   |
|  <span data-ttu-id="6049e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6049e-115">Message Text</span></span>   | <span data-ttu-id="6049e-116">再生 file.%r で破損が検出されました</span><span class="sxs-lookup"><span data-stu-id="6049e-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="6049e-117">再生ファイル: %1</span><span class="sxs-lookup"><span data-stu-id="6049e-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="6049e-118">説明</span><span class="sxs-lookup"><span data-stu-id="6049e-118">Explanation</span></span>  
 <span data-ttu-id="6049e-119">このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、破損のため、再生ファイルを読み取ることができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6049e-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="6049e-120">SSO で再生ファイルを開くことはできない場合は、(存在する場合)、[次へ] の再生ファイルに進みます。</span><span class="sxs-lookup"><span data-stu-id="6049e-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="6049e-121">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="6049e-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="6049e-122">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="6049e-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6049e-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6049e-123">User Action</span></span>  
 <span data-ttu-id="6049e-124">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6049e-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="6049e-125">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="6049e-125">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="6049e-126">再生ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="6049e-126">Delete the replay file.</span></span>  

  <span data-ttu-id="6049e-127">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="6049e-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="6049e-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6049e-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="6049e-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="6049e-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
