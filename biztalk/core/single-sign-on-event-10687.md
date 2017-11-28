---
title: "シングル サインオン: イベント 10687 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 368e9bbad42e49ebd71bc1a581b0fb18bbcc2d5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10687"></a><span data-ttu-id="6bacb-102">シングル サインオン: イベント 10687</span><span class="sxs-lookup"><span data-stu-id="6bacb-102">Single Sign-On: Event 10687</span></span>
## <a name="details"></a><span data-ttu-id="6bacb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6bacb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6bacb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6bacb-104">Product Name</span></span>|<span data-ttu-id="6bacb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6bacb-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6bacb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6bacb-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6bacb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6bacb-107">Event ID</span></span>|<span data-ttu-id="6bacb-108">10687</span><span class="sxs-lookup"><span data-stu-id="6bacb-108">10687</span></span>|  
|<span data-ttu-id="6bacb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6bacb-109">Event Source</span></span>|<span data-ttu-id="6bacb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6bacb-110">ENTSSO</span></span>|  
|<span data-ttu-id="6bacb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6bacb-111">Component</span></span>|<span data-ttu-id="6bacb-112">N\A</span><span class="sxs-lookup"><span data-stu-id="6bacb-112">N\A</span></span>|  
|<span data-ttu-id="6bacb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6bacb-113">Symbolic Name</span></span>|<span data-ttu-id="6bacb-114">SSO_INFO_REPLAY_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="6bacb-114">SSO_INFO_REPLAY_COMPLETE</span></span>|  
|<span data-ttu-id="6bacb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6bacb-115">Message Text</span></span>|<span data-ttu-id="6bacb-116">保存された外部パスワード変更の再生が完了しました。%r</span><span class="sxs-lookup"><span data-stu-id="6bacb-116">Replay of stored external password changes completed.%r</span></span><br /><br /> <span data-ttu-id="6bacb-117">再生ファイル: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6bacb-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="6bacb-118">追加データ: %2</span><span class="sxs-lookup"><span data-stu-id="6bacb-118">Additional Data: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6bacb-119">説明</span><span class="sxs-lookup"><span data-stu-id="6bacb-119">Explanation</span></span>  
 <span data-ttu-id="6bacb-120">この情報イベントは、SSO によって保存された外部パスワード変更ファイルの再生が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6bacb-120">This Information event indicates that SSO has completed replaying the stored external password changes file.</span></span> <span data-ttu-id="6bacb-121">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6bacb-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6bacb-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6bacb-122">User Action</span></span>  
  
-   <span data-ttu-id="6bacb-123">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6bacb-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="6bacb-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="6bacb-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="6bacb-125">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6bacb-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="6bacb-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="6bacb-126">Password Synchronization</span></span>](../core/password-synchronization2.md)