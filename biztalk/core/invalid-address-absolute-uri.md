---
title: "アドレスが無効です (絶対 uri) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db292ad-9105-492d-a6c5-a7108159901a
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af2cb19c793bdcd7ab4a1dc18eb0ea1c98a991ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-absolute-uri"></a><span data-ttu-id="5977a-102">アドレスが無効です (絶対 URI)</span><span class="sxs-lookup"><span data-stu-id="5977a-102">Invalid address (absolute uri)</span></span>
## <a name="details"></a><span data-ttu-id="5977a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5977a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5977a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5977a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5977a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5977a-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5977a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5977a-106">Event ID</span></span>|<span data-ttu-id="5977a-107">0</span><span class="sxs-lookup"><span data-stu-id="5977a-107">0</span></span>|  
|<span data-ttu-id="5977a-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5977a-108">Event Source</span></span>|<span data-ttu-id="5977a-109">0</span><span class="sxs-lookup"><span data-stu-id="5977a-109">0</span></span>|  
|<span data-ttu-id="5977a-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5977a-110">Component</span></span>|<span data-ttu-id="5977a-111">0</span><span class="sxs-lookup"><span data-stu-id="5977a-111">0</span></span>|  
|<span data-ttu-id="5977a-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5977a-112">Symbolic Name</span></span>|<span data-ttu-id="5977a-113">0</span><span class="sxs-lookup"><span data-stu-id="5977a-113">0</span></span>|  
|<span data-ttu-id="5977a-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5977a-114">Message Text</span></span>|<span data-ttu-id="5977a-115">アドレスが無効です。"{0}" は正しい形式の絶対 URI ではありません。</span><span class="sxs-lookup"><span data-stu-id="5977a-115">Invalid address; "{0}" is not a well-formed absolute uri</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5977a-116">説明</span><span class="sxs-lookup"><span data-stu-id="5977a-116">Explanation</span></span>  
 <span data-ttu-id="5977a-117">このエラー イベントは、インプロセスの WCF トランスポートに整形式の絶対アドレスを指定しなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5977a-117">This error event indicates that you did not provide an in-process WCF transport with a well-formed absolute address.</span></span> <span data-ttu-id="5977a-118">たとえば、インプロセスの WCF トランスポートのアドレス プロパティには、/path/service.svc などの相対アドレスを設定できません。</span><span class="sxs-lookup"><span data-stu-id="5977a-118">For example, you cannot set the Address property of the in-process WCF transport to a relative address, such as /path/service.svc.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5977a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5977a-119">User Action</span></span>  
 <span data-ttu-id="5977a-120">インプロセスの WCF トランスポートのアドレスを整形式の絶対アドレスに変更します。</span><span class="sxs-lookup"><span data-stu-id="5977a-120">Change the address of the in-process WCF transport to a well-formed absolute address.</span></span>  
  
1.  <span data-ttu-id="5977a-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5977a-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5977a-122">コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="5977a-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="5977a-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="5977a-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="5977a-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5977a-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="5977a-125">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5977a-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="5977a-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="5977a-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="5977a-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="5977a-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="5977a-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="5977a-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="5977a-129">**アドレス (URI)**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5977a-129">In the **Address (URI)** text box.</span></span> <span data-ttu-id="5977a-130">アドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="5977a-130">change the address.</span></span> <span data-ttu-id="5977a-131">整形式の絶対アドレスの一例は http://localhost/path/service.svc です。</span><span class="sxs-lookup"><span data-stu-id="5977a-131">An example of a well-formed absolute address is http://localhost/path/service.svc</span></span>