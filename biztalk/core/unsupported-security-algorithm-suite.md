---
title: "サポートされていないセキュリティ アルゴリズム スイート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11696fed-c3a8-4b11-8249-9f99f7abc8f2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43cce7cd315c3bdfa3835014c2cf1f6a8c7077f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unsupported-security-algorithm-suite"></a><span data-ttu-id="ab198-102">セキュリティ アルゴリズム スイートがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="ab198-102">Unsupported security algorithm suite</span></span>
## <a name="details"></a><span data-ttu-id="ab198-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ab198-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab198-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ab198-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ab198-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ab198-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="ab198-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ab198-106">Event ID</span></span>|<span data-ttu-id="ab198-107">0</span><span class="sxs-lookup"><span data-stu-id="ab198-107">0</span></span>|  
|<span data-ttu-id="ab198-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ab198-108">Event Source</span></span>|<span data-ttu-id="ab198-109">0</span><span class="sxs-lookup"><span data-stu-id="ab198-109">0</span></span>|  
|<span data-ttu-id="ab198-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ab198-110">Component</span></span>|<span data-ttu-id="ab198-111">0</span><span class="sxs-lookup"><span data-stu-id="ab198-111">0</span></span>|  
|<span data-ttu-id="ab198-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ab198-112">Symbolic Name</span></span>|<span data-ttu-id="ab198-113">0</span><span class="sxs-lookup"><span data-stu-id="ab198-113">0</span></span>|  
|<span data-ttu-id="ab198-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ab198-114">Message Text</span></span>|<span data-ttu-id="ab198-115">サポートされていないセキュリティ アルゴリズム スイート: {0}</span><span class="sxs-lookup"><span data-stu-id="ab198-115">Unsupported security algorithm suite: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ab198-116">説明</span><span class="sxs-lookup"><span data-stu-id="ab198-116">Explanation</span></span>  
 <span data-ttu-id="ab198-117">このエラーは、受信場所または送信ポートのセキュリティ アルゴリズム スイート プロパティが不適切な値に設定されているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="ab198-117">This error occurs when the security algorithm suite property of a receive location or send port is set to an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab198-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ab198-118">User Action</span></span>  
 <span data-ttu-id="ab198-119">トランザクション プロトコル プロパティを有効な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab198-119">Ensure that transaction protocol property is set to a valid value.</span></span>  
  
1.  <span data-ttu-id="ab198-120">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="ab198-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ab198-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ab198-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="ab198-122">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="ab198-122">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="ab198-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="ab198-123">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="ab198-124">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab198-124">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="ab198-125">ポート**型**一覧で、 **Wcf-nettcp**です。</span><span class="sxs-lookup"><span data-stu-id="ab198-125">In the port **Type** list, select **WCF-NetTcp**.</span></span>  
  
7.  <span data-ttu-id="ab198-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ab198-126">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="ab198-127">**Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。</span><span class="sxs-lookup"><span data-stu-id="ab198-127">In the **WCF-NetTcp Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="ab198-128">**メッセージ セキュリティ**セクションの値を確認してください**アルゴリズム スイート**が正しい。</span><span class="sxs-lookup"><span data-stu-id="ab198-128">In the **Message security** section, ensure that the values for **Algorithm suite** are correct.</span></span>