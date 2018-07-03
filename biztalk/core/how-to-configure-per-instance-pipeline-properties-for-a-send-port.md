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
ms.openlocfilehash: 2d1d49f0c6f54341c14cb14c38cc0de7fefaa9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991003"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="30a27-102">送信ポートのインスタンスごとにパイプライン プロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="30a27-102">How to Configure Per-Instance Pipeline Properties for a Send Port</span></span>
<span data-ttu-id="30a27-103">ここでは、BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して送信ポートのパイプライン プロパティを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30a27-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a send port after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="30a27-104">送信ポートのパイプライン プロパティを変更した場合、その送信ポートについてのみ、既定のパイプライン プロパティが上書きされます。したがって、BizTalk グループに含まれる各送信ポートについて、それぞれ異なるパイプライン プロパティを構成することも可能です。</span><span class="sxs-lookup"><span data-stu-id="30a27-104">Changes that you make overwrite the default pipeline properties for this send port only, so if you want, you can configure different pipeline properties for each send port in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="30a27-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="30a27-105">Prerequisites</span></span>  
 <span data-ttu-id="30a27-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30a27-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="30a27-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="30a27-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30a27-108">インスタンスごとにパイプライン プロパティを使用して、値を設定する場合、 **DocumentSpecNames**同じプロジェクトでパイプラインを指定されたドキュメント スキーマとパイプラインの XML 逆アセンブラー コンポーネントでプロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30a27-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="30a27-109">送信ポートのインスタンスごとにパイプライン プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="30a27-109">To configure per-instance pipeline properties for a send port</span></span>  
  
1. <span data-ttu-id="30a27-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="30a27-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="30a27-111">コンソール ツリーで、展開**BizTalk Server 管理**、パイプライン プロパティを構成する送信ポートが含まれる BizTalk グループ**アプリケーション**、し、送信ポートを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="30a27-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the send port for which you want to configure pipeline properties, expand **Applications**, and then expand the application containing the send port.</span></span>  
  
3. <span data-ttu-id="30a27-112">をクリックして、**送信ポート**フォルダー、送信ポートを右クリックしておよびクリックして**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="30a27-112">Click the **Send Ports** folder, right-click the send port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="30a27-113">省略記号をクリックします (**.**) の右側にボタン、**送信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="30a27-113">Click the ellipsis (**…**) button to the right of the **Send Pipeline** box.</span></span>  
  
5. <span data-ttu-id="30a27-114">をクリックし、プロパティを構成する**OK**します。</span><span class="sxs-lookup"><span data-stu-id="30a27-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="30a27-115">クリックして**ヘルプ**の詳細については、プロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="30a27-115">Click **Help** on the properties page for more information.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="30a27-116">パイプライン プロパティの情報は正しく入力してください。</span><span class="sxs-lookup"><span data-stu-id="30a27-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="30a27-117">数値を入力すべきところで文字列を入力するなど、無効な値を入力するとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="30a27-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6. <span data-ttu-id="30a27-118">送信請求-応答の送信ポートの場合は、省略記号をクリックします (**.。**) の右側にボタン、**受信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="30a27-118">If this is a solicit-response send port, click the ellipsis (**…**) button to the right of the **Receive Pipeline** box.</span></span>  
  
7. <span data-ttu-id="30a27-119">をクリックし、プロパティを構成する**OK** 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="30a27-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="30a27-120">クリックして**ヘルプ**の詳細については、プロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="30a27-120">Click **Help** on the properties page for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a27-121">参照</span><span class="sxs-lookup"><span data-stu-id="30a27-121">See Also</span></span>  
 <span data-ttu-id="30a27-122">[パイプラインの管理](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="30a27-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="30a27-123">[作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="30a27-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="30a27-124">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="30a27-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)