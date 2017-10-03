---
title: "シングル サインオン: イベント 10654 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d7de49ec1606c7c0a33f802af11af4e8ad2848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10654"></a><span data-ttu-id="564f5-102">シングル サインオン: イベント 10654</span><span class="sxs-lookup"><span data-stu-id="564f5-102">Single Sign-On: Event 10654</span></span>
## <a name="details"></a><span data-ttu-id="564f5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="564f5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="564f5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="564f5-104">Product Name</span></span>|<span data-ttu-id="564f5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="564f5-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="564f5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="564f5-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="564f5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="564f5-107">Event ID</span></span>|<span data-ttu-id="564f5-108">10654</span><span class="sxs-lookup"><span data-stu-id="564f5-108">10654</span></span>|  
|<span data-ttu-id="564f5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="564f5-109">Event Source</span></span>|<span data-ttu-id="564f5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="564f5-110">ENTSSO</span></span>|  
|<span data-ttu-id="564f5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="564f5-111">Component</span></span>|<span data-ttu-id="564f5-112">N\A</span><span class="sxs-lookup"><span data-stu-id="564f5-112">N\A</span></span>|  
|<span data-ttu-id="564f5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="564f5-113">Symbolic Name</span></span>|<span data-ttu-id="564f5-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="564f5-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="564f5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="564f5-115">Message Text</span></span>|<span data-ttu-id="564f5-116">パスワード同期サーバーへの (Windows の) アクセスは拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="564f5-116">Password sync server (for Windows) access denied.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="564f5-117">説明</span><span class="sxs-lookup"><span data-stu-id="564f5-117">Explanation</span></span>  
 <span data-ttu-id="564f5-118">このエラー イベントは、メッセージが [名前] サーバーに送信されたが、応答がブロックされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="564f5-118">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="564f5-119">原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="564f5-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="564f5-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="564f5-120">User Action</span></span>  
 <span data-ttu-id="564f5-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="564f5-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="564f5-122">このメッセージの情報と、イベント ログで関連情報に注意してください、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="564f5-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  
  
 <span data-ttu-id="564f5-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="564f5-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="564f5-124">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="564f5-124">Password Synchronization</span></span>](../core/password-synchronization2.md)