---
title: インスタンスごとのパイプライン プロパティを構成する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- receive locations, configuring
- managing [pipelines], properties
- managing [pipelines], receive locations
- managing [receive locations], pipelines
- managing [pipelines], configuring
- pipelines, receive locations
- pipelines, configuring
- receive locations, pipelines
- managing [receive locations], configuring
ms.assetid: e1ed3b10-2f39-479b-a3e6-22b4b2872192
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c591e7ea30dd97b116f89c3d50d03ea48392b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982419"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a><span data-ttu-id="c798a-102">受信場所のインスタンスごとにパイプライン プロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c798a-102">How to Configure Per-instance Pipeline Properties for a Receive Location</span></span>
<span data-ttu-id="c798a-103">このトピックでは、BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して受信場所のパイプライン プロパティを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c798a-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="c798a-104">受信場所のパイプライン プロパティを変更した場合、その受信場所についてのみ、既定のパイプライン プロパティが上書きされます。したがって、BizTalk グループに含まれる各受信場所について、それぞれ異なるパイプライン プロパティを構成することも可能です。</span><span class="sxs-lookup"><span data-stu-id="c798a-104">Changes that you make overwrite the default pipeline properties for this receive location only, so if you want, you can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c798a-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="c798a-105">Prerequisites</span></span>  
 <span data-ttu-id="c798a-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c798a-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c798a-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="c798a-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c798a-108">インスタンスごとにパイプライン プロパティを使用して、値を設定する場合、 **DocumentSpecNames**同じプロジェクトでパイプラインを指定されたドキュメント スキーマとパイプラインの XML 逆アセンブラー コンポーネントでプロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c798a-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a><span data-ttu-id="c798a-109">受信場所のインスタンスごとにパイプライン プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="c798a-109">To configure per-instance pipeline properties for a receive location</span></span>  
  
1. <span data-ttu-id="c798a-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c798a-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c798a-111">コンソール ツリーで、展開**BizTalk Server 管理**、パイプライン プロパティを構成する受信場所が含まれる BizTalk グループ**アプリケーション**、し、受信場所を含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="c798a-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the receive location for which to configure pipeline properties, expand **Applications**, and then expand the application containing the receive location.</span></span>  
  
3. <span data-ttu-id="c798a-112">をクリックして、**受信場所**フォルダーは、受信場所を右クリックし、順にクリックします**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c798a-112">Click the **Receive Locations** folder, right-click the receive location, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="c798a-113">右側にある省略記号 (...) をクリックして、**受信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="c798a-113">Click the ellipsis (…) to the right of the **Receive Pipeline** box.</span></span>  
  
5. <span data-ttu-id="c798a-114">をクリックし、プロパティを構成する**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c798a-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="c798a-115">詳細については、次のようにクリックします。**ヘルプ**[プロパティ] ページ。</span><span class="sxs-lookup"><span data-stu-id="c798a-115">For more information, click **Help** on the properties page.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="c798a-116">パイプライン プロパティの情報は正しく入力してください。</span><span class="sxs-lookup"><span data-stu-id="c798a-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="c798a-117">数値を入力すべきところで文字列を入力するなど、無効な値を入力するとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c798a-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6. <span data-ttu-id="c798a-118">この場合、要求-応答受信場所の右側にある省略記号 (...) をクリックして、**送信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="c798a-118">If this is a request-response receive location, click the ellipsis (…) to the right of the **Send Pipeline** box.</span></span>  
  
7. <span data-ttu-id="c798a-119">をクリックし、プロパティを構成する**OK** 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="c798a-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="c798a-120">詳細については、次のようにクリックします。**ヘルプ**[プロパティ] ページ。</span><span class="sxs-lookup"><span data-stu-id="c798a-120">For more information, click **Help** on the properties page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c798a-121">参照</span><span class="sxs-lookup"><span data-stu-id="c798a-121">See Also</span></span>  
 <span data-ttu-id="c798a-122">[パイプラインの管理](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="c798a-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="c798a-123">[作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="c798a-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="c798a-124">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="c798a-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)