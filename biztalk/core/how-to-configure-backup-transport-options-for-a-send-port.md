---
title: 送信ポートに対してバックアップ トランスポートのオプションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- managing [send ports], configuring
- configuring, backing up [send ports]
- managing [send ports], backup options
- send ports, configuring
- send ports, backup options
ms.assetid: f05f57a6-e62b-4640-a6e2-cb73e9de2a14
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee35e6eb408ab8749e12a7747643783cabc3019
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341690"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a><span data-ttu-id="d70c7-102">送信ポートに対してバックアップ トランスポートのオプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d70c7-102">How to Configure Backup Transport Options for a Send Port</span></span>
<span data-ttu-id="d70c7-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートに対してバックアップ トランスポートのオプションを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-103">This topic describes how to use the BizTalk Server Administration console to configure backup transport options for a send port.</span></span> <span data-ttu-id="d70c7-104">指定したバックアップ トランスポートは、プライマリ トランスポートは、関数が失敗したイベントに反映されます。</span><span class="sxs-lookup"><span data-stu-id="d70c7-104">The backup transport that you specify takes effect in the event the primary transport fails to function.</span></span> <span data-ttu-id="d70c7-105">プライマリ トランスポートの構成を記載[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-105">Configuring the primary transport is described in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d70c7-106">動的ポートのプロパティがない構成のトランスポートのオプションは実行時に自動的に決定されるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d70c7-106">For dynamic ports, there are not properties available to configure because transport options are automatically determined at run time.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d70c7-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d70c7-107">Prerequisites</span></span>  
 <span data-ttu-id="d70c7-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d70c7-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d70c7-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-specify-transport-options-for-a-send-port"></a><span data-ttu-id="d70c7-110">送信ポートに対してトランスポートのオプションを指定するには</span><span class="sxs-lookup"><span data-stu-id="d70c7-110">To specify transport options for a send port</span></span>  
  
1. <span data-ttu-id="d70c7-111">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d70c7-112">コンソール ツリーで、BizTalk グループと、送信ポートに対してバックアップ トランスポートのオプションを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure backup transport options for a send port.</span></span>  
  
3. <span data-ttu-id="d70c7-113">展開**送信ポート**、構成、 をクリックする送信ポートを右クリックして**プロパティ**、順にクリックします**バックアップ トランスポート**します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-113">Expand **Send Ports**, right-click the send port to configure, click **Properties**, and then click **Backup Transport**.</span></span>  
  
4. <span data-ttu-id="d70c7-114">次の表に示すように、バックアップ トランスポートのプロパティを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-114">Configure backup transport properties as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="d70c7-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d70c7-115">Use this</span></span>|<span data-ttu-id="d70c7-116">目的</span><span class="sxs-lookup"><span data-stu-id="d70c7-116">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="d70c7-117">**型**</span><span class="sxs-lookup"><span data-stu-id="d70c7-117">**Type**</span></span>|<span data-ttu-id="d70c7-118">ドロップダウン リストから、適切なバックアップ トランスポートの種類を選択するか、トランスポート プロトコル。</span><span class="sxs-lookup"><span data-stu-id="d70c7-118">From the drop-down list, select the appropriate backup transport type, or transport protocol.</span></span> <span data-ttu-id="d70c7-119">送信請求 - 応答のポートの場合、ドロップダウン リストでは、送信請求 - 応答をサポートするアダプターのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d70c7-119">If the port is a solicit-response port, only transport types that support solicit-response are available in the list.</span></span>|  
   |<span data-ttu-id="d70c7-120">**構成**</span><span class="sxs-lookup"><span data-stu-id="d70c7-120">**Configure**</span></span>|<span data-ttu-id="d70c7-121">バックアップ トランスポートの種類を選択してクリックして**構成**、し、トランスポートのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-121">After you select the backup transport type, click **Configure**, and then configure transport properties.</span></span> <span data-ttu-id="d70c7-122">プロパティを構成する方法の詳細については、次のようにクリックします。**ヘルプ**します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-122">For more information about configuring the properties, click **Help**.</span></span>|  
   |<span data-ttu-id="d70c7-123">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="d70c7-123">**Send handler**</span></span>|<span data-ttu-id="d70c7-124">ドロップダウン リストから、送信アダプターが動作しているホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-124">From the drop-down list, select the host instance on which the send adapter is running.</span></span>|  
   |<span data-ttu-id="d70c7-125">**再試行の回数**</span><span class="sxs-lookup"><span data-stu-id="d70c7-125">**Retry count**</span></span>|<span data-ttu-id="d70c7-126">メッセージのエラーでメッセージを再送信する送信ポートの回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-126">Specify the number of times for the send port to resend a message on message failure.</span></span> <span data-ttu-id="d70c7-127">既定値は 3 です。許容範囲は 0 ~ 1,000 です。</span><span class="sxs-lookup"><span data-stu-id="d70c7-127">The default is 3; the allowed range is from 0 to 1,000.</span></span>|  
   |<span data-ttu-id="d70c7-128">**再試行の間隔**</span><span class="sxs-lookup"><span data-stu-id="d70c7-128">**Retry interval**</span></span>|<span data-ttu-id="d70c7-129">メッセージの再送を試みる間隔を分単位で間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="d70c7-129">Specify the interval in minutes between message resend attempts.</span></span> <span data-ttu-id="d70c7-130">既定値は 5 です。許容範囲は 0 ~ 525,600 です。</span><span class="sxs-lookup"><span data-stu-id="d70c7-130">The default is 5; the allowed range is from 0 to 525,600.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d70c7-131">参照</span><span class="sxs-lookup"><span data-stu-id="d70c7-131">See Also</span></span>  
 [<span data-ttu-id="d70c7-132">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="d70c7-132">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)