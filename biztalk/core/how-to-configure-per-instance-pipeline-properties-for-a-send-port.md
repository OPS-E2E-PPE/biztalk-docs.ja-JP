---
title: 送信ポートのインスタンスごとのパイプライン プロパティを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- managing [pipelines], properties
- configuring, send ports
- configuring, pipelines
- managing [pipelines], configuring
- managing [send ports], pipelines
- managing [send ports], configuring
- send ports, pipelines
- pipelines, configuring
ms.assetid: c58faa9e-0dfb-458b-8f1b-d3c91bce0436
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ab5b83ae12cd6de262e23ed2136f1c9a886d57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341239"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="adbef-102">送信ポートのインスタンスごとのパイプライン プロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="adbef-102">How to Configure Per-Instance Pipeline Properties for a Send Port</span></span>
<span data-ttu-id="adbef-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk グループにパイプラインを展開した後、送信ポートのパイプライン プロパティを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="adbef-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a send port after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="adbef-104">既定値を上書き変更パイプラインのみ、この送信ポートのプロパティの場合は、BizTalk グループの送信ポートごとに異なるパイプライン プロパティを構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="adbef-104">Changes that you make overwrite the default pipeline properties for this send port only, so if you want, you can configure different pipeline properties for each send port in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="adbef-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="adbef-105">Prerequisites</span></span>  
 <span data-ttu-id="adbef-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="adbef-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="adbef-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="adbef-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adbef-108">インスタンスごとにパイプライン プロパティを使用して、値を設定する場合、 **DocumentSpecNames**同じプロジェクトでパイプラインを指定されたドキュメント スキーマとパイプラインの XML 逆アセンブラー コンポーネントでプロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adbef-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="adbef-109">送信ポートのインスタンスごとのパイプライン プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="adbef-109">To configure per-instance pipeline properties for a send port</span></span>  
  
1. <span data-ttu-id="adbef-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="adbef-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="adbef-111">コンソール ツリーで、展開**BizTalk Server 管理**、パイプライン プロパティを構成する送信ポートが含まれる BizTalk グループ**アプリケーション**、し、送信ポートを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="adbef-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the send port for which you want to configure pipeline properties, expand **Applications**, and then expand the application containing the send port.</span></span>  
  
3. <span data-ttu-id="adbef-112">をクリックして、**送信ポート**フォルダー、送信ポートを右クリックしておよびクリックして**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="adbef-112">Click the **Send Ports** folder, right-click the send port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="adbef-113">省略記号をクリックします (**.**) の右側にボタン、**送信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="adbef-113">Click the ellipsis (**…**) button to the right of the **Send Pipeline** box.</span></span>  
  
5. <span data-ttu-id="adbef-114">をクリックし、プロパティを構成する**OK**します。</span><span class="sxs-lookup"><span data-stu-id="adbef-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="adbef-115">クリックして**ヘルプ**の詳細については、プロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="adbef-115">Click **Help** on the properties page for more information.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="adbef-116">パイプラインのプロパティの正しい情報を入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="adbef-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="adbef-117">数値ではなく文字列など、無効な値を入力すると、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="adbef-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6. <span data-ttu-id="adbef-118">送信請求-応答の送信ポートの場合は、省略記号をクリックします (**...**) の右側にボタン、**受信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="adbef-118">If this is a solicit-response send port, click the ellipsis (**…**) button to the right of the **Receive Pipeline** box.</span></span>  
  
7. <span data-ttu-id="adbef-119">をクリックし、プロパティを構成する**OK** 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="adbef-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="adbef-120">クリックして**ヘルプ**の詳細については、プロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="adbef-120">Click **Help** on the properties page for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbef-121">参照</span><span class="sxs-lookup"><span data-stu-id="adbef-121">See Also</span></span>  
 <span data-ttu-id="adbef-122">[パイプラインの管理](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="adbef-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="adbef-123">[作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="adbef-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="adbef-124">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="adbef-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)