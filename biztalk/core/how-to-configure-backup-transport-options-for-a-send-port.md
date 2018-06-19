---
title: 送信ポートに対してバックアップ トランスポートのオプションを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 8ff8b1354772290ce9e04742a6130a6f6f2df627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248378"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a><span data-ttu-id="5241c-102">送信ポートに対してバックアップ トランスポートのオプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="5241c-102">How to Configure Backup Transport Options for a Send Port</span></span>
<span data-ttu-id="5241c-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートに対してバックアップ トランスポートのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5241c-103">This topic describes how to use the BizTalk Server Administration console to configure backup transport options for a send port.</span></span> <span data-ttu-id="5241c-104">プライマリ トランスポートにエラーが発生した場合は、指定したバックアップ トランスポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="5241c-104">The backup transport that you specify takes effect in the event the primary transport fails to function.</span></span> <span data-ttu-id="5241c-105">プライマリ トランスポートの構成に記載されて[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。</span><span class="sxs-lookup"><span data-stu-id="5241c-105">Configuring the primary transport is described in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5241c-106">動的ポートの場合、トランスポート オプションは実行時に自動的に決まるため、プロパティを手動で構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="5241c-106">For dynamic ports, there are not properties available to configure because transport options are automatically determined at run time.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5241c-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="5241c-107">Prerequisites</span></span>  
 <span data-ttu-id="5241c-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5241c-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5241c-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="5241c-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-specify-transport-options-for-a-send-port"></a><span data-ttu-id="5241c-110">送信ポートのトランスポート オプションを指定するには</span><span class="sxs-lookup"><span data-stu-id="5241c-110">To specify transport options for a send port</span></span>  
  
1.  <span data-ttu-id="5241c-111">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5241c-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5241c-112">コンソール ツリーで、BizTalk グループを展開し、送信ポートに対してバックアップ トランスポートのオプションを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="5241c-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure backup transport options for a send port.</span></span>  
  
3.  <span data-ttu-id="5241c-113">展開**送信ポート**をクリックして、構成する送信ポートを右クリックして**プロパティ**、クリックして**バックアップ トランスポート**です。</span><span class="sxs-lookup"><span data-stu-id="5241c-113">Expand **Send Ports**, right-click the send port to configure, click **Properties**, and then click **Backup Transport**.</span></span>  
  
4.  <span data-ttu-id="5241c-114">次の表に示すようにバックアップ トランスポートのプロパティを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5241c-114">Configure backup transport properties as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="5241c-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5241c-115">Use this</span></span>|<span data-ttu-id="5241c-116">目的</span><span class="sxs-lookup"><span data-stu-id="5241c-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5241c-117">**型**</span><span class="sxs-lookup"><span data-stu-id="5241c-117">**Type**</span></span>|<span data-ttu-id="5241c-118">ドロップダウン リストから、適切なバックアップ トランスポートの種類またはトランスポート プロトコルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5241c-118">From the drop-down list, select the appropriate backup transport type, or transport protocol.</span></span> <span data-ttu-id="5241c-119">送信請求 - 応答のポートの場合、ドロップダウン リストでは、送信請求 - 応答をサポートするアダプターのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5241c-119">If the port is a solicit-response port, only transport types that support solicit-response are available in the list.</span></span>|  
    |<span data-ttu-id="5241c-120">**構成**</span><span class="sxs-lookup"><span data-stu-id="5241c-120">**Configure**</span></span>|<span data-ttu-id="5241c-121">バックアップ トランスポートの種類を選択してクリックして**構成**、およびトランスポートのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="5241c-121">After you select the backup transport type, click **Configure**, and then configure transport properties.</span></span> <span data-ttu-id="5241c-122">プロパティを構成する詳細についてをクリックして**ヘルプ**です。</span><span class="sxs-lookup"><span data-stu-id="5241c-122">For more information about configuring the properties, click **Help**.</span></span>|  
    |<span data-ttu-id="5241c-123">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="5241c-123">**Send handler**</span></span>|<span data-ttu-id="5241c-124">ドロップダウン リストから、送信アダプターが動作しているホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5241c-124">From the drop-down list, select the host instance on which the send adapter is running.</span></span>|  
    |<span data-ttu-id="5241c-125">**再試行の回数**</span><span class="sxs-lookup"><span data-stu-id="5241c-125">**Retry count**</span></span>|<span data-ttu-id="5241c-126">メッセージ エラーが発生したときに送信ポートがメッセージを再送する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5241c-126">Specify the number of times for the send port to resend a message on message failure.</span></span> <span data-ttu-id="5241c-127">指定できる範囲は 0 ～ 1,000 です。既定値は 3 です。</span><span class="sxs-lookup"><span data-stu-id="5241c-127">The default is 3; the allowed range is from 0 to 1,000.</span></span>|  
    |<span data-ttu-id="5241c-128">**再試行の間隔**</span><span class="sxs-lookup"><span data-stu-id="5241c-128">**Retry interval**</span></span>|<span data-ttu-id="5241c-129">メッセージの再送を試みる間隔 (分) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5241c-129">Specify the interval in minutes between message resend attempts.</span></span> <span data-ttu-id="5241c-130">既定値は 5 です。許容範囲は 0 ~ 525,600 です。</span><span class="sxs-lookup"><span data-stu-id="5241c-130">The default is 5; the allowed range is from 0 to 525,600.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5241c-131">参照</span><span class="sxs-lookup"><span data-stu-id="5241c-131">See Also</span></span>  
 [<span data-ttu-id="5241c-132">作成して、送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="5241c-132">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)