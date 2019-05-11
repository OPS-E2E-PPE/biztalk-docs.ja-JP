---
title: アクション エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87cf0a5b-d1dd-4807-9660-e8a8b7012b40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3588559d0090a9a78b05882b297d7f39805a3a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361806"
---
# <a name="action-errors"></a><span data-ttu-id="e008a-102">アクション エラー</span><span class="sxs-lookup"><span data-stu-id="e008a-102">Action Errors</span></span>
<span data-ttu-id="e008a-103">ここでは、WCF のアクション エラーを診断および解決するための詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="e008a-103">This section contains detailed information for diagnosing and resolving WCF Action errors.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e008a-104">詳細</span><span class="sxs-lookup"><span data-stu-id="e008a-104">Details</span></span>  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e008a-105">製品名</span><span class="sxs-lookup"><span data-stu-id="e008a-105">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| <span data-ttu-id="e008a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e008a-106">Product Version</span></span> |                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                              |
|    <span data-ttu-id="e008a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e008a-107">Event ID</span></span>     |                                                                          <span data-ttu-id="e008a-108">0</span><span class="sxs-lookup"><span data-stu-id="e008a-108">0</span></span>                                                                          |
|  <span data-ttu-id="e008a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e008a-109">Event Source</span></span>   |                                                                          <span data-ttu-id="e008a-110">0</span><span class="sxs-lookup"><span data-stu-id="e008a-110">0</span></span>                                                                          |
|    <span data-ttu-id="e008a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e008a-111">Component</span></span>    |                                                                          <span data-ttu-id="e008a-112">0</span><span class="sxs-lookup"><span data-stu-id="e008a-112">0</span></span>                                                                          |
|  <span data-ttu-id="e008a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e008a-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="e008a-114">0</span><span class="sxs-lookup"><span data-stu-id="e008a-114">0</span></span>                                                                          |
|  <span data-ttu-id="e008a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e008a-115">Message Text</span></span>   | <span data-ttu-id="e008a-116">1 つのアクションは、改行文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e008a-116">A single action cannot contain new line characters.</span></span> <span data-ttu-id="e008a-117">すべての改行文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="e008a-117">Remove all new line characters.</span></span> <span data-ttu-id="e008a-118">または、複数のアクションを指定するには、アクション マッピングの構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="e008a-118">Or, to specify multiple actions, use the action mapping syntax.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e008a-119">説明</span><span class="sxs-lookup"><span data-stu-id="e008a-119">Explanation</span></span>  
 <span data-ttu-id="e008a-120">このエラーは、送信ポートの action プロパティには許可されていない新しい改行文字が含まれていますを示します。</span><span class="sxs-lookup"><span data-stu-id="e008a-120">This error indicates the action property of a send port contains a new line character, which is not allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e008a-121">マッピングとしてアクションが定義されている場合、この制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="e008a-121">This restriction does not apply when the action is defined as a mapping.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e008a-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e008a-122">User Action</span></span>  
 <span data-ttu-id="e008a-123">アクション プロパティを修正するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e008a-123">Use the following procedure to fix the action property.</span></span>  
  
 
1. <span data-ttu-id="e008a-124">開いている**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="e008a-124">Open **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e008a-125">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="e008a-125">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="e008a-126">アプリケーションを特定して、トランスポートを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e008a-126">Locate your application, and then locate your transport.</span></span>  
  
4. <span data-ttu-id="e008a-127">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e008a-127">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="e008a-128">選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e008a-128">Select **Properties**.</span></span>  
  
6. <span data-ttu-id="e008a-129">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e008a-129">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="e008a-130">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e008a-130">Select **Configure**.</span></span>  
  
8. <span data-ttu-id="e008a-131">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="e008a-131">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, select the **General** tab.</span></span>  
  
9. <span data-ttu-id="e008a-132">**SOAP アクション ヘッダー**セクションから改行文字を削除、**アクション**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="e008a-132">In the **SOAP Action header** section, remove the new line character from the **Action** text box.</span></span>  

## <a name="more-good-info"></a><span data-ttu-id="e008a-133">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="e008a-133">More good info</span></span>  
 <span data-ttu-id="e008a-134">アクションの詳細については、次を参照してください[WCF 送信アダプター用の SOAP アクションの指定。](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span><span class="sxs-lookup"><span data-stu-id="e008a-134">For additional information on actions, see [Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span></span>