---
title: トランザクションのオプション&quot;トランザクション&quot;とエラー処理オプションの&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3818ddba18b89aedd1185f5ad87f3682dd5686a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971419"
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a><span data-ttu-id="0a62e-102">トランザクションのオプション&quot;トランザクション&quot;とエラー処理オプションの&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります</span><span class="sxs-lookup"><span data-stu-id="0a62e-102">Transactions option &quot;Transactional&quot; and the error handling option &quot;Suspend request message on failure&quot; should not both be set to false</span></span>
## <a name="details"></a><span data-ttu-id="0a62e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0a62e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0a62e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0a62e-104">Product Name</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| <span data-ttu-id="0a62e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0a62e-105">Product Version</span></span> |                                                                            [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                            |
|    <span data-ttu-id="0a62e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0a62e-106">Event ID</span></span>     |                                                                                                        <span data-ttu-id="0a62e-107">0</span><span class="sxs-lookup"><span data-stu-id="0a62e-107">0</span></span>                                                                                                         |
|  <span data-ttu-id="0a62e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0a62e-108">Event Source</span></span>   |                                                                                                        <span data-ttu-id="0a62e-109">0</span><span class="sxs-lookup"><span data-stu-id="0a62e-109">0</span></span>                                                                                                         |
|    <span data-ttu-id="0a62e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a62e-110">Component</span></span>    |                                                                                                        <span data-ttu-id="0a62e-111">0</span><span class="sxs-lookup"><span data-stu-id="0a62e-111">0</span></span>                                                                                                         |
|  <span data-ttu-id="0a62e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0a62e-112">Symbolic Name</span></span>  |                                                                                                        <span data-ttu-id="0a62e-113">0</span><span class="sxs-lookup"><span data-stu-id="0a62e-113">0</span></span>                                                                                                         |
|  <span data-ttu-id="0a62e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0a62e-114">Message Text</span></span>   | <span data-ttu-id="0a62e-115">メッセージが表示されなくなる可能性があるため、エラー処理オプションの "エラー発生時に場所を無効にする" および "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="0a62e-115">The transactions option "Transactional" and the error handling option "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="0a62e-116">1 つまたは両方のオプションを true に設定してください。</span><span class="sxs-lookup"><span data-stu-id="0a62e-116">Please set one or both options to true.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0a62e-117">説明</span><span class="sxs-lookup"><span data-stu-id="0a62e-117">Explanation</span></span>  
 <span data-ttu-id="0a62e-118">Wcf-netmsmq アダプターは、オプションで**トランザクション**と**エラー発生時に要求メッセージを保留**両方を false に設定する必要があります (オフ)。</span><span class="sxs-lookup"><span data-stu-id="0a62e-118">In the WCF-NetMsmq adapter, the options **Transactional** and **Suspend request message on failure** should not both be set to false (unchecked).</span></span> <span data-ttu-id="0a62e-119">メッセージ送信の失敗でトランザクションとしてロール バックせずに、メッセージを中断してメッセージ ボックスに保存しない場合は、メッセージが失われることがあります。</span><span class="sxs-lookup"><span data-stu-id="0a62e-119">Message loss may occur if the failed message submission does not roll back as a transaction, while the message is not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a62e-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0a62e-120">User Action</span></span>  
 <span data-ttu-id="0a62e-121">アダプター設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a62e-121">Use the following procedure to verify adapter settings.</span></span>  
  
#### <a name="to-verify-adapter-settings"></a><span data-ttu-id="0a62e-122">アダプター設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="0a62e-122">To verify adapter settings</span></span>  
  
1. <span data-ttu-id="0a62e-123">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0a62e-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="0a62e-124">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="0a62e-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="0a62e-125">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="0a62e-125">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="0a62e-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0a62e-126">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="0a62e-127">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a62e-127">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="0a62e-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a62e-128">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="0a62e-129">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="0a62e-129">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="0a62e-130">**Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="0a62e-130">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="0a62e-131">**トランザクション**セクションであるかどうか、**トランザクション**がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="0a62e-131">In the **Transactions** section, determine if **Transactional** is checked.</span></span>  
  
10. <span data-ttu-id="0a62e-132">をクリックして、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="0a62e-132">Click the **Messages** tab.</span></span>  
  
11. <span data-ttu-id="0a62e-133">かどうか確認**エラー発生時に要求メッセージを保留**がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="0a62e-133">Determine if **Suspend request message on failure** is checked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a62e-134">これらの手順は、場所の受信にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0a62e-134">These steps only apply to receive locations.</span></span>