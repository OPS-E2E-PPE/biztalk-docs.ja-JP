---
title: バインドのプロパティの競合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cacdbd24b6c9dd72ab1e123cc5990ba35d274c30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354957"
---
# <a name="conflicting-binding-properties"></a><span data-ttu-id="2e67d-102">バインド プロパティの競合</span><span class="sxs-lookup"><span data-stu-id="2e67d-102">Conflicting binding properties</span></span>
## <a name="details"></a><span data-ttu-id="2e67d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2e67d-103">Details</span></span>  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2e67d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2e67d-104">Product Name</span></span>   |                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                    |
| <span data-ttu-id="2e67d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2e67d-105">Product Version</span></span> |                                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                |
|    <span data-ttu-id="2e67d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2e67d-106">Event ID</span></span>     |                                                                            <span data-ttu-id="2e67d-107">0</span><span class="sxs-lookup"><span data-stu-id="2e67d-107">0</span></span>                                                                            |
|  <span data-ttu-id="2e67d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2e67d-108">Event Source</span></span>   |                                                                            <span data-ttu-id="2e67d-109">0</span><span class="sxs-lookup"><span data-stu-id="2e67d-109">0</span></span>                                                                            |
|    <span data-ttu-id="2e67d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2e67d-110">Component</span></span>    |                                                                            <span data-ttu-id="2e67d-111">0</span><span class="sxs-lookup"><span data-stu-id="2e67d-111">0</span></span>                                                                            |
|  <span data-ttu-id="2e67d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2e67d-112">Symbolic Name</span></span>  |                                                                            <span data-ttu-id="2e67d-113">0</span><span class="sxs-lookup"><span data-stu-id="2e67d-113">0</span></span>                                                                            |
|  <span data-ttu-id="2e67d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2e67d-114">Message Text</span></span>   | <span data-ttu-id="2e67d-115">競合するバインドのプロパティ:MsmqAuthenticationMode ={0}と MsmqProtectionLevel ={1}が無効です。</span><span class="sxs-lookup"><span data-stu-id="2e67d-115">Conflicting binding properties: MsmqAuthenticationMode={0} and MsmqProtectionLevel={1} is invalid.</span></span> <span data-ttu-id="2e67d-116">いずれかの競合を解決するプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2e67d-116">Change one of the properties to resolve the conflict</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2e67d-117">説明</span><span class="sxs-lookup"><span data-stu-id="2e67d-117">Explanation</span></span>  
 <span data-ttu-id="2e67d-118">Wcf-netmsmq トランスポートの MSMQ 保護レベル プロパティに設定されました**サインオン**または**EncryptAndSign** None MSMQ 認証モード。</span><span class="sxs-lookup"><span data-stu-id="2e67d-118">The MSMQ protection level property of a WCF-NetMsmq transport was set to **Sign** or **EncryptAndSign** for the None MSMQ authentication mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2e67d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2e67d-119">User Action</span></span>  
 <span data-ttu-id="2e67d-120">MSMQ 保護レベルまたは MSMQ 保護レベルのプロパティと一致するように MSMQ 認証モードのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2e67d-120">Change the MSMQ protection level or the MSMQ authentication mode property to be consistent with the MSMQ protection level property.</span></span>  
  
1. <span data-ttu-id="2e67d-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="2e67d-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2e67d-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="2e67d-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="2e67d-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="2e67d-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="2e67d-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="2e67d-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="2e67d-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e67d-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="2e67d-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e67d-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="2e67d-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="2e67d-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="2e67d-128">**Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="2e67d-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="2e67d-129">MSMQ の値をチェック**認証モード**一覧と**MSMQ 保護レベル**一覧。</span><span class="sxs-lookup"><span data-stu-id="2e67d-129">Check the values in the MSMQ **authentication mode** list and the **MSMQ protection level** list.</span></span>  
  
   <span data-ttu-id="2e67d-130">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e67d-130">For further information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="2e67d-131">Wcf-netmsmq 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2e67d-131">How to Configure a WCF-NetMsmq Send Port</span></span>](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [<span data-ttu-id="2e67d-132">Wcf-netmsmq 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2e67d-132">How to Configure a WCF-NetMsmq Receive Location</span></span>](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)