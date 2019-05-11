---
title: シングル サインオン:イベント 10692 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdfd3359baec8f4dbecaaafc6acd0e614956ffcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397351"
---
# <a name="single-sign-on-event-10692"></a><span data-ttu-id="1cc7d-102">シングル サインオン:イベント 10692</span><span class="sxs-lookup"><span data-stu-id="1cc7d-102">Single Sign-On: Event 10692</span></span>
## <a name="details"></a><span data-ttu-id="1cc7d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1cc7d-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1cc7d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1cc7d-104">Product Name</span></span>   |                                                                                                                      <span data-ttu-id="1cc7d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1cc7d-105">Enterprise Single Sign-On</span></span>                                                                                                                      |
| <span data-ttu-id="1cc7d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1cc7d-106">Product Version</span></span> |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    <span data-ttu-id="1cc7d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1cc7d-107">Event ID</span></span>     |                                                                                                                                <span data-ttu-id="1cc7d-108">10692</span><span class="sxs-lookup"><span data-stu-id="1cc7d-108">10692</span></span>                                                                                                                                |
|  <span data-ttu-id="1cc7d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1cc7d-109">Event Source</span></span>   |                                                                                                                               <span data-ttu-id="1cc7d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1cc7d-110">ENTSSO</span></span>                                                                                                                                |
|    <span data-ttu-id="1cc7d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1cc7d-111">Component</span></span>    |                                                                                                                                 <span data-ttu-id="1cc7d-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="1cc7d-112">N\A</span></span>                                                                                                                                 |
|  <span data-ttu-id="1cc7d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1cc7d-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="1cc7d-114">SSO_WARN_REPLAY_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="1cc7d-114">SSO_WARN_REPLAY_ACCESS_DENIED</span></span>                                                                                                                    |
|  <span data-ttu-id="1cc7d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1cc7d-115">Message Text</span></span>   | <span data-ttu-id="1cc7d-116">最初の呼び出し元が adapter.%r アクセス アカウントのメンバーではなくなったために、外部パスワード変更を再生することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cc7d-116">The external password change cannot be replayed because the original caller is no longer a member of the access account for the adapter.%r</span></span><br /><br /> <span data-ttu-id="1cc7d-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="1cc7d-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="1cc7d-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="1cc7d-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="1cc7d-119">最初の呼び出し元: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="1cc7d-119">Original Caller: %3%r</span></span><br /><br /> <span data-ttu-id="1cc7d-120">アクセス アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="1cc7d-120">Access Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="1cc7d-121">説明</span><span class="sxs-lookup"><span data-stu-id="1cc7d-121">Explanation</span></span>  
 <span data-ttu-id="1cc7d-122">この警告イベントは、こと SSO が SSO データベースとの接続を再確立が (SSO データベース) に変更を加えることができません指定再生ファイルで、変更を最初に指定されたアカウントが有効ではなくなったためにを示します。</span><span class="sxs-lookup"><span data-stu-id="1cc7d-122">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to make a change (in the SSO database) specified in the replay file because the account that originally specified the change is no longer valid.</span></span>  

 <span data-ttu-id="1cc7d-123">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cc7d-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="1cc7d-124">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="1cc7d-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1cc7d-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1cc7d-125">User Action</span></span>  
 <span data-ttu-id="1cc7d-126">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1cc7d-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="1cc7d-127">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="1cc7d-127">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="1cc7d-128">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="1cc7d-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="1cc7d-129">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="1cc7d-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="1cc7d-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="1cc7d-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
