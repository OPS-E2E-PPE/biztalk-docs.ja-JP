---
title: "シングル サインオン: イベント 10741 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52ad76e20937bfa4af1dbec6d71ba59003874435
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10741"></a><span data-ttu-id="a6410-102">シングル サインオン: イベント 10741</span><span class="sxs-lookup"><span data-stu-id="a6410-102">Single Sign-On: Event 10741</span></span>
## <a name="details"></a><span data-ttu-id="a6410-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a6410-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6410-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a6410-104">Product Name</span></span>|<span data-ttu-id="a6410-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a6410-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a6410-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a6410-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a6410-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a6410-107">Event ID</span></span>|<span data-ttu-id="a6410-108">10741</span><span class="sxs-lookup"><span data-stu-id="a6410-108">10741</span></span>|  
|<span data-ttu-id="a6410-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a6410-109">Event Source</span></span>|<span data-ttu-id="a6410-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a6410-110">ENTSSO</span></span>|  
|<span data-ttu-id="a6410-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a6410-111">Component</span></span>|<span data-ttu-id="a6410-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a6410-112">N\A</span></span>|  
|<span data-ttu-id="a6410-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a6410-113">Symbolic Name</span></span>|<span data-ttu-id="a6410-114">SSO_WARN_SAVING_REPLAY_FILE</span><span class="sxs-lookup"><span data-stu-id="a6410-114">SSO_WARN_SAVING_REPLAY_FILE</span></span>|  
|<span data-ttu-id="a6410-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a6410-115">Message Text</span></span>|<span data-ttu-id="a6410-116">再生ファイルまたは進行状況ファイルを保存しています。%r</span><span class="sxs-lookup"><span data-stu-id="a6410-116">Saving replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="a6410-117">保存したファイル: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a6410-117">Saved File: %1%r</span></span><br /><br /> <span data-ttu-id="a6410-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="a6410-118">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6410-119">説明</span><span class="sxs-lookup"><span data-stu-id="a6410-119">Explanation</span></span>  
 <span data-ttu-id="a6410-120">この警告イベントは、SSO が再生ファイルまたは進行状況ファイルを保存していることを示します。</span><span class="sxs-lookup"><span data-stu-id="a6410-120">This Warning event indicates that SSO is saving a replay or progress file.</span></span>  
  
 <span data-ttu-id="a6410-121">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6410-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="a6410-122">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="a6410-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6410-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a6410-123">User Action</span></span>  
  
-   <span data-ttu-id="a6410-124">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a6410-124">No user action is necessary.</span></span>  
  
 <span data-ttu-id="a6410-125">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6410-125">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="a6410-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="a6410-126">Password Synchronization</span></span>](../core/password-synchronization2.md)