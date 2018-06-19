---
title: ログ ストアの選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 6ba64c59-3a15-4c10-b44f-18e0e432c6d3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0518b536db16d641b77a61cfeb4851990a7bca0a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960736"
---
# <a name="selecting-the-logging-store"></a><span data-ttu-id="226e1-102">ログ ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="226e1-102">Selecting the Logging Store</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="226e1-103">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]など、さまざまなログ ストアの組み合わせを選択するオプションを使用して提供する[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI)、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]、および[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ログです。</span><span class="sxs-lookup"><span data-stu-id="226e1-103"> [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] provides you with the option to select a combination of different logging stores, such as [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI), [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log.</span></span>  
  
 <span data-ttu-id="226e1-104">使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ログ ストアを構成するエクスプ ローラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="226e1-104">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to configure the logging store.</span></span>  
  
 <span data-ttu-id="226e1-105">開くには、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーと、ログ ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="226e1-105">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and select the logging store.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="226e1-106">BTAHL7 構成エクスプ ローラーを開く</span><span class="sxs-lookup"><span data-stu-id="226e1-106">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="226e1-107">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="226e1-107">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-select-the--logging-store"></a><span data-ttu-id="226e1-108">ログ ストアを選択</span><span class="sxs-lookup"><span data-stu-id="226e1-108">To select the  logging store</span></span>  
  
1.  <span data-ttu-id="226e1-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、**グローバル設定** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="226e1-109">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, on the **Global Settings** tab, do the following:</span></span>  
  
    |<span data-ttu-id="226e1-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="226e1-110">Use this</span></span>|<span data-ttu-id="226e1-111">目的</span><span class="sxs-lookup"><span data-stu-id="226e1-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="226e1-112">**WMI**</span><span class="sxs-lookup"><span data-stu-id="226e1-112">**WMI**</span></span>|<span data-ttu-id="226e1-113">BTAHL7 の WMI 通知を生成する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="226e1-113">Select this option if you want to generate WMI notifications for BTAHL7.</span></span>|  
    |<span data-ttu-id="226e1-114">**SQL**</span><span class="sxs-lookup"><span data-stu-id="226e1-114">**SQL**</span></span>|<span data-ttu-id="226e1-115">使用する場合は、このオプションを選択[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ストアとして。</span><span class="sxs-lookup"><span data-stu-id="226e1-115">Select this option if you want to use [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your  logging store.</span></span> <span data-ttu-id="226e1-116">**注:** BTAHL7 が存在しない場合は、ログに必要なテーブルを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="226e1-116">**Note:**  BTAHL7 automatically creates the tables required for  logging if they do not exist.</span></span>|  
    |<span data-ttu-id="226e1-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="226e1-117">**SQL Server**</span></span>|<span data-ttu-id="226e1-118">型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名。</span><span class="sxs-lookup"><span data-stu-id="226e1-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="226e1-119">これは、選択したときに必要な**SQL**オプション。</span><span class="sxs-lookup"><span data-stu-id="226e1-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="226e1-120">許容最大長は、64 文字です。</span><span class="sxs-lookup"><span data-stu-id="226e1-120">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="226e1-121">既定のサーバーとデータベース名は、構成された BTAHL7 データベースです。</span><span class="sxs-lookup"><span data-stu-id="226e1-121">The default server and database name is the configured BTAHL7 database.</span></span>|  
    |<span data-ttu-id="226e1-122">**データベース名**</span><span class="sxs-lookup"><span data-stu-id="226e1-122">**Database name**</span></span>|<span data-ttu-id="226e1-123">型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース名。</span><span class="sxs-lookup"><span data-stu-id="226e1-123">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="226e1-124">これは、選択したときに必要な**SQL**オプション。</span><span class="sxs-lookup"><span data-stu-id="226e1-124">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="226e1-125">許容最大長は、128 文字です。</span><span class="sxs-lookup"><span data-stu-id="226e1-125">The maximum allowed length is 128 characters.</span></span>|  
    |<span data-ttu-id="226e1-126">**イベント ログ**</span><span class="sxs-lookup"><span data-stu-id="226e1-126">**Event  Log**</span></span>|<span data-ttu-id="226e1-127">使用する場合は、このオプションを選択、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ログ ストアとしてのイベント ログです。</span><span class="sxs-lookup"><span data-stu-id="226e1-127">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as your  logging store.</span></span> <span data-ttu-id="226e1-128">使用する、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント メッセージを表示するイベント ビューアー。</span><span class="sxs-lookup"><span data-stu-id="226e1-128">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>|  
  
2.  <span data-ttu-id="226e1-129">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="226e1-129">Click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="226e1-130">ログ記録イベント ブローカーによって記録されたイベントのロケールは、ログ記録のサービス アカウントのロケールに依存します。</span><span class="sxs-lookup"><span data-stu-id="226e1-130">The locale of the events logged by the  Logging event broker depend on the locale of the  Logging Service account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="226e1-131">パスワードを変更する必要があります最初、ログ記録のサービス アカウントのパスワードを変更するときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)]ディレクトリ サービス、および実行するすべてのサーバーでログ サービスのパスワードを変更した後、ログ記録がサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="226e1-131">When changing the  Logging Service account password, you should first change the password in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)] directory service, and then restart the  Logging Service after changing the  Logging Service password on every server running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="226e1-132">参照</span><span class="sxs-lookup"><span data-stu-id="226e1-132">See Also</span></span>  
 <span data-ttu-id="226e1-133">[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="226e1-133">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 [<span data-ttu-id="226e1-134">ログ記録の構成</span><span class="sxs-lookup"><span data-stu-id="226e1-134">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)