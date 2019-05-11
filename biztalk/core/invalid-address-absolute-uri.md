---
title: アドレスが無効です (絶対 uri) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5db292ad-9105-492d-a6c5-a7108159901a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00b8c4986224e07865dc641551906e6aeed704fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331290"
---
# <a name="invalid-address-absolute-uri"></a><span data-ttu-id="f6289-102">アドレスが無効です (絶対 URI)</span><span class="sxs-lookup"><span data-stu-id="f6289-102">Invalid address (absolute uri)</span></span>
## <a name="details"></a><span data-ttu-id="f6289-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f6289-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f6289-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f6289-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f6289-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f6289-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f6289-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f6289-106">Event ID</span></span>     |                                         <span data-ttu-id="f6289-107">0</span><span class="sxs-lookup"><span data-stu-id="f6289-107">0</span></span>                                          |
|  <span data-ttu-id="f6289-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f6289-108">Event Source</span></span>   |                                         <span data-ttu-id="f6289-109">0</span><span class="sxs-lookup"><span data-stu-id="f6289-109">0</span></span>                                          |
|    <span data-ttu-id="f6289-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6289-110">Component</span></span>    |                                         <span data-ttu-id="f6289-111">0</span><span class="sxs-lookup"><span data-stu-id="f6289-111">0</span></span>                                          |
|  <span data-ttu-id="f6289-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f6289-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f6289-113">0</span><span class="sxs-lookup"><span data-stu-id="f6289-113">0</span></span>                                          |
|  <span data-ttu-id="f6289-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f6289-114">Message Text</span></span>   |              <span data-ttu-id="f6289-115">アドレスが無効です。"{0}"は適切な形式の絶対 uri ではありません</span><span class="sxs-lookup"><span data-stu-id="f6289-115">Invalid address; "{0}" is not a well-formed absolute uri</span></span>              |

## <a name="explanation"></a><span data-ttu-id="f6289-116">説明</span><span class="sxs-lookup"><span data-stu-id="f6289-116">Explanation</span></span>  
 <span data-ttu-id="f6289-117">このエラー イベントは、適切な形式の絶対アドレスでは、インプロセスの WCF トランスポートを指定しなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f6289-117">This error event indicates that you did not provide an in-process WCF transport with a well-formed absolute address.</span></span> <span data-ttu-id="f6289-118">たとえば、/path/service.svc などの相対アドレスをインプロセスの WCF トランスポートのアドレス プロパティを設定できません。</span><span class="sxs-lookup"><span data-stu-id="f6289-118">For example, you cannot set the Address property of the in-process WCF transport to a relative address, such as /path/service.svc.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f6289-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f6289-119">User Action</span></span>  
 <span data-ttu-id="f6289-120">インプロセスの WCF トランスポートのアドレスを適切な形式の絶対アドレスに変更します。</span><span class="sxs-lookup"><span data-stu-id="f6289-120">Change the address of the in-process WCF transport to a well-formed absolute address.</span></span>  

1. <span data-ttu-id="f6289-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="f6289-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f6289-122">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="f6289-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="f6289-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="f6289-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="f6289-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f6289-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="f6289-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6289-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="f6289-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6289-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="f6289-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f6289-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="f6289-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="f6289-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="f6289-129">**アドレス (URI)** テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="f6289-129">In the **Address (URI)** text box.</span></span> <span data-ttu-id="f6289-130">アドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="f6289-130">change the address.</span></span> <span data-ttu-id="f6289-131">適切な形式の絶対アドレスの例は、します。 http://localhost/path/service.svc</span><span class="sxs-lookup"><span data-stu-id="f6289-131">An example of a well-formed absolute address is http://localhost/path/service.svc</span></span>
