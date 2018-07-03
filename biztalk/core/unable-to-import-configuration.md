---
title: 構成をインポートできません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2887da50-4f74-4259-a7d6-c87bc9b9fc58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5be14cff11021ac1a50116ee2e7784223724f675
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023784"
---
# <a name="unable-to-import-configuration"></a><span data-ttu-id="06136-102">構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="06136-102">Unable to import configuration</span></span>
## <a name="details"></a><span data-ttu-id="06136-103">詳細</span><span class="sxs-lookup"><span data-stu-id="06136-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="06136-104">製品名</span><span class="sxs-lookup"><span data-stu-id="06136-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="06136-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="06136-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="06136-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="06136-106">Event ID</span></span>     |                                         <span data-ttu-id="06136-107">0</span><span class="sxs-lookup"><span data-stu-id="06136-107">0</span></span>                                          |
|  <span data-ttu-id="06136-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="06136-108">Event Source</span></span>   |                                         <span data-ttu-id="06136-109">0</span><span class="sxs-lookup"><span data-stu-id="06136-109">0</span></span>                                          |
|    <span data-ttu-id="06136-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="06136-110">Component</span></span>    |                                         <span data-ttu-id="06136-111">0</span><span class="sxs-lookup"><span data-stu-id="06136-111">0</span></span>                                          |
|  <span data-ttu-id="06136-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="06136-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="06136-113">0</span><span class="sxs-lookup"><span data-stu-id="06136-113">0</span></span>                                          |
|  <span data-ttu-id="06136-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="06136-114">Message Text</span></span>   |                   <span data-ttu-id="06136-115">ファイルから構成をインポートできません"{0}"。</span><span class="sxs-lookup"><span data-stu-id="06136-115">Unable to import configuration from file "{0}"</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="06136-116">説明</span><span class="sxs-lookup"><span data-stu-id="06136-116">Explanation</span></span>  
 <span data-ttu-id="06136-117">このエラーには複数の理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="06136-117">There could be multiple reasons for this error:</span></span>  
  
-   <span data-ttu-id="06136-118">構成ファイルに、指定したエンコーディングでは無効な文字が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="06136-118">The configuration file may contain invalid character in the given encoding.</span></span>  
  
-   <span data-ttu-id="06136-119">ルート要素が欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="06136-119">The root element may be missing.</span></span>  
  
-   <span data-ttu-id="06136-120">ルート レベルのデータが無効な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="06136-120">The data at the root level may be invalid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06136-121">この状況およびユーザー操作は、WCF-Custom アダプターおよび WCF-CustomIsolate アダプターのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="06136-121">This situation, and the user action, applies only to WCF-Custom and WCF-CustomIsolate adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06136-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="06136-122">User Action</span></span>  
 <span data-ttu-id="06136-123">有効な構成ファイルをインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="06136-123">Use the following procedure to import a valid configuration file.</span></span>  
  
#### <a name="to-import-a-valid-configuration-file"></a><span data-ttu-id="06136-124">有効な構成ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="06136-124">To import a valid configuration file</span></span>  
  
1. <span data-ttu-id="06136-125">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="06136-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="06136-126">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="06136-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="06136-127">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="06136-127">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="06136-128">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="06136-128">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="06136-129">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06136-129">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="06136-130">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="06136-130">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="06136-131">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="06136-131">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="06136-132">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**インポート/エクスポート**タブ。</span><span class="sxs-lookup"><span data-stu-id="06136-132">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Import/Export** tab.</span></span>  
  
9. <span data-ttu-id="06136-133">**[インポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06136-133">Click **Import**.</span></span> <span data-ttu-id="06136-134">有効で完成した構成ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="06136-134">Import a valid and complete configuration file.</span></span>  
  
   <span data-ttu-id="06136-135">サービス構成エディターで開くことによって、構成ファイルの有効性を確認することも **(開始 > すべてのプログラム > Windows SDK)** (この手順を前提とする Windows SDK をインストールします)。開いている**svcConfigEditor.exe**構成ファイルの各プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="06136-135">You can also verify the validity of the configuration file by opening it with the Service Configuration Editor **(Start > All Programs > Windows SDK)** (this step assumes you have the Windows SDK installed.) Open **svcConfigEditor.exe** and verify each property of the configuration file.</span></span>