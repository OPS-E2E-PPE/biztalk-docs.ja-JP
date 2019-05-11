---
title: 無効なアドレスの長さ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e16eb6-e77e-4361-ac91-0730004c4433
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c23c8c20dba45957cb338b588e16013a01626b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381486"
---
# <a name="invalid-address-length"></a><span data-ttu-id="7509c-102">アドレスの長さが無効です</span><span class="sxs-lookup"><span data-stu-id="7509c-102">Invalid address length</span></span>
## <a name="details"></a><span data-ttu-id="7509c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7509c-103">Details</span></span>  

|                 |                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7509c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7509c-104">Product Name</span></span>   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| <span data-ttu-id="7509c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7509c-105">Product Version</span></span> |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    <span data-ttu-id="7509c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7509c-106">Event ID</span></span>     |                                              <span data-ttu-id="7509c-107">0</span><span class="sxs-lookup"><span data-stu-id="7509c-107">0</span></span>                                              |
|  <span data-ttu-id="7509c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7509c-108">Event Source</span></span>   |                                              <span data-ttu-id="7509c-109">0</span><span class="sxs-lookup"><span data-stu-id="7509c-109">0</span></span>                                              |
|    <span data-ttu-id="7509c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7509c-110">Component</span></span>    |                                              <span data-ttu-id="7509c-111">0</span><span class="sxs-lookup"><span data-stu-id="7509c-111">0</span></span>                                              |
|  <span data-ttu-id="7509c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7509c-112">Symbolic Name</span></span>  |                                              <span data-ttu-id="7509c-113">0</span><span class="sxs-lookup"><span data-stu-id="7509c-113">0</span></span>                                              |
|  <span data-ttu-id="7509c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7509c-114">Message Text</span></span>   | <span data-ttu-id="7509c-115">無効なアドレスの長さ。指定されたアドレスの長さは{0}文字制限は{1}文字</span><span class="sxs-lookup"><span data-stu-id="7509c-115">Invalid address length; specified address length is {0} characters, limit is {1} characters</span></span> |

## <a name="explanation"></a><span data-ttu-id="7509c-116">説明</span><span class="sxs-lookup"><span data-stu-id="7509c-116">Explanation</span></span>  
 <span data-ttu-id="7509c-117">WCF トランスポートの 255 文字の最大長を超えるアドレスを指定するとします。</span><span class="sxs-lookup"><span data-stu-id="7509c-117">You provided an address that exceeds the maximum length of 255 characters for a WCF transport.</span></span> <span data-ttu-id="7509c-118">これは、WCF ではなく、BizTalk Server によって課される制限です。</span><span class="sxs-lookup"><span data-stu-id="7509c-118">This is a limitation imposed by BizTalk Server, not by WCF.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7509c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7509c-119">User Action</span></span>  
 <span data-ttu-id="7509c-120">有効なアドレスを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7509c-120">Use the following procedure to configure a valid address.</span></span>  

#### <a name="to-configure-a-valid-address"></a><span data-ttu-id="7509c-121">有効なアドレスを構成するには</span><span class="sxs-lookup"><span data-stu-id="7509c-121">To configure a valid address</span></span>  

1. <span data-ttu-id="7509c-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="7509c-122">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="7509c-123">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="7509c-123">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="7509c-124">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="7509c-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="7509c-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7509c-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="7509c-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7509c-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="7509c-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7509c-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="7509c-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7509c-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="7509c-129">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="7509c-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="7509c-130">**アドレス (URI)** テキスト ボックスに、アドレスが 255 文字の最大の長さを超えていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7509c-130">In the **Address (URI)** text box, ensure the address does not exceed the maximum length of 255 characters.</span></span>
