---
title: "無効なアドレスの長さ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8e16eb6-e77e-4361-ac91-0730004c4433
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2df1666fbbd399ef71852b9b9049959830749e99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-length"></a><span data-ttu-id="b00a9-102">アドレスの長さが無効です</span><span class="sxs-lookup"><span data-stu-id="b00a9-102">Invalid address length</span></span>
## <a name="details"></a><span data-ttu-id="b00a9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b00a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b00a9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b00a9-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b00a9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b00a9-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="b00a9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b00a9-106">Event ID</span></span>|<span data-ttu-id="b00a9-107">0</span><span class="sxs-lookup"><span data-stu-id="b00a9-107">0</span></span>|  
|<span data-ttu-id="b00a9-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b00a9-108">Event Source</span></span>|<span data-ttu-id="b00a9-109">0</span><span class="sxs-lookup"><span data-stu-id="b00a9-109">0</span></span>|  
|<span data-ttu-id="b00a9-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b00a9-110">Component</span></span>|<span data-ttu-id="b00a9-111">0</span><span class="sxs-lookup"><span data-stu-id="b00a9-111">0</span></span>|  
|<span data-ttu-id="b00a9-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b00a9-112">Symbolic Name</span></span>|<span data-ttu-id="b00a9-113">0</span><span class="sxs-lookup"><span data-stu-id="b00a9-113">0</span></span>|  
|<span data-ttu-id="b00a9-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b00a9-114">Message Text</span></span>|<span data-ttu-id="b00a9-115">無効なアドレスの長さです。指定したアドレスの長さは {0} 文字、上限は {1} 文字</span><span class="sxs-lookup"><span data-stu-id="b00a9-115">Invalid address length; specified address length is {0} characters, limit is {1} characters</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b00a9-116">説明</span><span class="sxs-lookup"><span data-stu-id="b00a9-116">Explanation</span></span>  
 <span data-ttu-id="b00a9-117">WCF トランスポートの 255 文字という最大文字長を超えるアドレスが指定されました。</span><span class="sxs-lookup"><span data-stu-id="b00a9-117">You provided an address that exceeds the maximum length of 255 characters for a WCF transport.</span></span> <span data-ttu-id="b00a9-118">これは WCF ではなく BizTalk Server の制限です。</span><span class="sxs-lookup"><span data-stu-id="b00a9-118">This is a limitation imposed by BizTalk Server, not by WCF.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b00a9-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b00a9-119">User Action</span></span>  
 <span data-ttu-id="b00a9-120">有効なアドレスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b00a9-120">Use the following procedure to configure a valid address.</span></span>  
  
#### <a name="to-configure-a-valid-address"></a><span data-ttu-id="b00a9-121">有効なアドレスを構成するには</span><span class="sxs-lookup"><span data-stu-id="b00a9-121">To configure a valid address</span></span>  
  
1.  <span data-ttu-id="b00a9-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b00a9-122">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b00a9-123">コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="b00a9-123">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="b00a9-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="b00a9-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="b00a9-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b00a9-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="b00a9-126">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b00a9-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="b00a9-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b00a9-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="b00a9-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b00a9-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="b00a9-129">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="b00a9-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="b00a9-130">**アドレス (URI)**テキスト ボックスに、アドレスが 255 文字の最大の長さを超えていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b00a9-130">In the **Address (URI)** text box, ensure the address does not exceed the maximum length of 255 characters.</span></span>