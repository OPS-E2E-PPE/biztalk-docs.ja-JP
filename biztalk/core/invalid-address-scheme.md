---
title: 無効なアドレス スキーム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b2b1a1514c605a40c98dacfd90911f806ddcd2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381489"
---
# <a name="invalid-address-scheme"></a><span data-ttu-id="13cba-102">アドレス スキームが無効です</span><span class="sxs-lookup"><span data-stu-id="13cba-102">Invalid address scheme</span></span>
## <a name="details"></a><span data-ttu-id="13cba-103">詳細</span><span class="sxs-lookup"><span data-stu-id="13cba-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="13cba-104">製品名</span><span class="sxs-lookup"><span data-stu-id="13cba-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="13cba-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="13cba-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="13cba-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="13cba-106">Event ID</span></span>     |                                        <span data-ttu-id="13cba-107">000</span><span class="sxs-lookup"><span data-stu-id="13cba-107">000</span></span>                                         |
|  <span data-ttu-id="13cba-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="13cba-108">Event Source</span></span>   |                                         <span data-ttu-id="13cba-109">0</span><span class="sxs-lookup"><span data-stu-id="13cba-109">0</span></span>                                          |
|    <span data-ttu-id="13cba-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="13cba-110">Component</span></span>    |                                         <span data-ttu-id="13cba-111">0</span><span class="sxs-lookup"><span data-stu-id="13cba-111">0</span></span>                                          |
|  <span data-ttu-id="13cba-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="13cba-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="13cba-113">0</span><span class="sxs-lookup"><span data-stu-id="13cba-113">0</span></span>                                          |
|  <span data-ttu-id="13cba-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="13cba-114">Message Text</span></span>   |                  <span data-ttu-id="13cba-115">無効なアドレスのスキーム指定してください"{0}"スキーム。</span><span class="sxs-lookup"><span data-stu-id="13cba-115">Invalid address scheme; expecting "{0}" scheme.</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="13cba-116">説明</span><span class="sxs-lookup"><span data-stu-id="13cba-116">Explanation</span></span>  
 <span data-ttu-id="13cba-117">トランスポート バインディングに定義されている型に一致しないプロトコル スキームを指定したとします。</span><span class="sxs-lookup"><span data-stu-id="13cba-117">You provided a protocol scheme that does not match the type defined by your transport binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13cba-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="13cba-118">User Action</span></span>  
 <span data-ttu-id="13cba-119">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="13cba-119">To resolve this error, do the following:</span></span>  
  
1. <span data-ttu-id="13cba-120">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="13cba-120">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="13cba-121">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="13cba-121">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="13cba-122">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="13cba-122">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="13cba-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="13cba-123">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="13cba-124">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13cba-124">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="13cba-125">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="13cba-125">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="13cba-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="13cba-126">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="13cba-127">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="13cba-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="13cba-128">**アドレス (URI)** テキスト ボックスに、アドレスの値が使用されている WCF アダプターの種類と一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13cba-128">In the **Address (URI)** text box, ensure that address value matches the type of the WCF adapter that is being used.</span></span>  
  
   <span data-ttu-id="13cba-129">また、システム指定のバインディングの種類で、Wcf-custom アダプターを使用する場合の値を確認、**バインドの種類**ボックスの一覧、**バインド**タブ。場合、**バインドの種類**するように構成**customBinding**、アドレスが記載トランスポート バインド要素と一致する必要があります、**バインドの種類**一覧で、 **バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="13cba-129">Also, if you use the WCF-Custom adapter with a system-provided binding type, check the value of the **Binding Type** list on the **Binding** tab. If the **Binding Type** is configured to **customBinding**, the address should match the transport binding element listed in the **Binding Type** list on the **Binding** tab.</span></span>