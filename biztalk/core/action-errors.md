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
ms.openlocfilehash: c3cb63e90f85c830c30524b3adc1e3b0d86ab8b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997275"
---
# <a name="action-errors"></a><span data-ttu-id="55005-102">アクション エラー</span><span class="sxs-lookup"><span data-stu-id="55005-102">Action Errors</span></span>
<span data-ttu-id="55005-103">ここでは、WCF のアクション エラーを診断および解決するための詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="55005-103">This section contains detailed information for diagnosing and resolving WCF Action errors.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55005-104">詳細</span><span class="sxs-lookup"><span data-stu-id="55005-104">Details</span></span>  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="55005-105">製品名</span><span class="sxs-lookup"><span data-stu-id="55005-105">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| <span data-ttu-id="55005-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="55005-106">Product Version</span></span> |                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                              |
|    <span data-ttu-id="55005-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="55005-107">Event ID</span></span>     |                                                                          <span data-ttu-id="55005-108">0</span><span class="sxs-lookup"><span data-stu-id="55005-108">0</span></span>                                                                          |
|  <span data-ttu-id="55005-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="55005-109">Event Source</span></span>   |                                                                          <span data-ttu-id="55005-110">0</span><span class="sxs-lookup"><span data-stu-id="55005-110">0</span></span>                                                                          |
|    <span data-ttu-id="55005-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="55005-111">Component</span></span>    |                                                                          <span data-ttu-id="55005-112">0</span><span class="sxs-lookup"><span data-stu-id="55005-112">0</span></span>                                                                          |
|  <span data-ttu-id="55005-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="55005-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="55005-114">0</span><span class="sxs-lookup"><span data-stu-id="55005-114">0</span></span>                                                                          |
|  <span data-ttu-id="55005-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="55005-115">Message Text</span></span>   | <span data-ttu-id="55005-116">単一のアクションに改行文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="55005-116">A single action cannot contain new line characters.</span></span> <span data-ttu-id="55005-117">改行文字をすべて削除するか、</span><span class="sxs-lookup"><span data-stu-id="55005-117">Remove all new line characters.</span></span> <span data-ttu-id="55005-118">アクション マッピングの構文を使用して複数のアクションを指定してください。</span><span class="sxs-lookup"><span data-stu-id="55005-118">Or, to specify multiple actions, use the action mapping syntax.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="55005-119">説明</span><span class="sxs-lookup"><span data-stu-id="55005-119">Explanation</span></span>  
 <span data-ttu-id="55005-120">このエラーは、送信ポートのアクション プロパティに、使用できない改行文字が含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="55005-120">This error indicates the action property of a send port contains a new line character, which is not allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55005-121">この制限は、マッピングとしてアクションを定義するときには適用されません。</span><span class="sxs-lookup"><span data-stu-id="55005-121">This restriction does not apply when the action is defined as a mapping.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55005-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="55005-122">User Action</span></span>  
 <span data-ttu-id="55005-123">アクション プロパティを修正するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="55005-123">Use the following procedure to fix the action property.</span></span>  
  
 
1. <span data-ttu-id="55005-124">開いている**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="55005-124">Open **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="55005-125">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="55005-125">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="55005-126">アプリケーションを特定し、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="55005-126">Locate your application, and then locate your transport.</span></span>  
  
4. <span data-ttu-id="55005-127">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="55005-127">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="55005-128">選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="55005-128">Select **Properties**.</span></span>  
  
6. <span data-ttu-id="55005-129">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="55005-129">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="55005-130">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="55005-130">Select **Configure**.</span></span>  
  
8. <span data-ttu-id="55005-131">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="55005-131">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, select the **General** tab.</span></span>  
  
9. <span data-ttu-id="55005-132">**SOAP アクション ヘッダー**セクションから改行文字を削除、**アクション**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="55005-132">In the **SOAP Action header** section, remove the new line character from the **Action** text box.</span></span>  

## <a name="more-good-info"></a><span data-ttu-id="55005-133">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="55005-133">More good info</span></span>  
 <span data-ttu-id="55005-134">アクションの詳細については、次を参照してください[WCF 送信アダプター用の SOAP アクションの指定。](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span><span class="sxs-lookup"><span data-stu-id="55005-134">For additional information on actions, see [Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span></span>