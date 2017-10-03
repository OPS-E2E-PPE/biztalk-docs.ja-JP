---
title: "トランザクションのオプションが&quot;トランザクション&quot;とエラー処理オプション&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8c47e364fccdb310167e56c6556423c2d4b39d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a><span data-ttu-id="9157b-102">トランザクションのオプションが&quot;トランザクション&quot;とエラー処理オプション&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります</span><span class="sxs-lookup"><span data-stu-id="9157b-102">Transactions option &quot;Transactional&quot; and the error handling option &quot;Suspend request message on failure&quot; should not both be set to false</span></span>
## <a name="details"></a><span data-ttu-id="9157b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9157b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9157b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9157b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9157b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9157b-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="9157b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9157b-106">Event ID</span></span>|<span data-ttu-id="9157b-107">0</span><span class="sxs-lookup"><span data-stu-id="9157b-107">0</span></span>|  
|<span data-ttu-id="9157b-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9157b-108">Event Source</span></span>|<span data-ttu-id="9157b-109">0</span><span class="sxs-lookup"><span data-stu-id="9157b-109">0</span></span>|  
|<span data-ttu-id="9157b-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9157b-110">Component</span></span>|<span data-ttu-id="9157b-111">0</span><span class="sxs-lookup"><span data-stu-id="9157b-111">0</span></span>|  
|<span data-ttu-id="9157b-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9157b-112">Symbolic Name</span></span>|<span data-ttu-id="9157b-113">0</span><span class="sxs-lookup"><span data-stu-id="9157b-113">0</span></span>|  
|<span data-ttu-id="9157b-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9157b-114">Message Text</span></span>|<span data-ttu-id="9157b-115">メッセージが表示されなくなる可能性があるため、エラー処理オプションの "エラー発生時に場所を無効にする" および "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="9157b-115">The transactions option "Transactional" and the error handling option "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="9157b-116">1 つまたは両方のオプションを true に設定してください。</span><span class="sxs-lookup"><span data-stu-id="9157b-116">Please set one or both options to true.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9157b-117">説明</span><span class="sxs-lookup"><span data-stu-id="9157b-117">Explanation</span></span>  
 <span data-ttu-id="9157b-118">Wcf-netmsmq アダプターで、オプション**トランザクション**と**エラー発生時に要求メッセージを保留**両方を false に設定する必要があります (オフ)。</span><span class="sxs-lookup"><span data-stu-id="9157b-118">In the WCF-NetMsmq adapter, the options **Transactional** and **Suspend request message on failure** should not both be set to false (unchecked).</span></span> <span data-ttu-id="9157b-119">メッセージ送信の失敗でトランザクションとしてロール バックせずに、メッセージを中断してメッセージ ボックスに保存しない場合は、メッセージが失われることがあります。</span><span class="sxs-lookup"><span data-stu-id="9157b-119">Message loss may occur if the failed message submission does not roll back as a transaction, while the message is not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9157b-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9157b-120">User Action</span></span>  
 <span data-ttu-id="9157b-121">アダプター設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9157b-121">Use the following procedure to verify adapter settings.</span></span>  
  
#### <a name="to-verify-adapter-settings"></a><span data-ttu-id="9157b-122">アダプター設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="9157b-122">To verify adapter settings</span></span>  
  
1.  <span data-ttu-id="9157b-123">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="9157b-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9157b-124">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="9157b-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="9157b-125">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="9157b-125">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="9157b-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9157b-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="9157b-127">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9157b-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="9157b-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9157b-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="9157b-129">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="9157b-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="9157b-130">**Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="9157b-130">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="9157b-131">**トランザクション**セクションで、かどうかを**トランザクション**がオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9157b-131">In the **Transactions** section, determine if **Transactional** is checked.</span></span>  
  
10. <span data-ttu-id="9157b-132">クリックして、**メッセージ**タブです。</span><span class="sxs-lookup"><span data-stu-id="9157b-132">Click the **Messages** tab.</span></span>  
  
11. <span data-ttu-id="9157b-133">かどうかを**エラー発生時に要求メッセージを保留**がオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9157b-133">Determine if **Suspend request message on failure** is checked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9157b-134">これらの手順は、場所の受信にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9157b-134">These steps only apply to receive locations.</span></span>