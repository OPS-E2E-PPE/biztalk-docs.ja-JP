---
title: BizTalk での Oracle データベースの SOAP アクションの構成 |Microsoft Docs
description: Visual Studio での SOAP アクションの入力または BizTalk アダプター パック (BAP) で、Wcf-custom または Wcf-oracledb アダプターを使用して、
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d21cca-3907-4f99-af76-c1e7286e1bcf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62bb4567a73411c28ba68010b7def22a121ddda2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377003"
---
# <a name="configure-the-soap-action-for-oracle-database"></a><span data-ttu-id="d633a-103">Oracle データベースの SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d633a-103">Configure the SOAP action for Oracle Database</span></span>
<span data-ttu-id="d633a-104">WCF ベースを使用して Oracle データベースで任意の操作を完了する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターのユーザーは、SOAP アクションを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d633a-104">To complete any operation on the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], adapter users must enter a SOAP action.</span></span> <span data-ttu-id="d633a-105">SOAP アクションは、どのような操作を完了する必要があります、アダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="d633a-105">The SOAP action communicates to the adapter what action should be completed.</span></span> <span data-ttu-id="d633a-106">デザイン時または実行時に SOAP アクションを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="d633a-106">You can enter the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="d633a-107">ただし、SOAP アクション両方デザイン時の入力時間を実行すると、デザイン時に入力するアクションはオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="d633a-107">However, if you enter the SOAP action both at design time and run time, the action you enter at design time is overridden.</span></span>  
  
 <span data-ttu-id="d633a-108">SOAP アクションを指定する方法については、次を参照してください。 [WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d633a-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="d633a-109">Visual Studio からの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="d633a-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="d633a-110">Visual studio でする必要がありますアクションを指定する、SOAP、オーケストレーションの一部としてを使用して、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="d633a-110">From Visual Studio, you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="d633a-111">BizTalk オーケストレーションで含める、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックス。</span><span class="sxs-lookup"><span data-stu-id="d633a-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="d633a-112">ダブルクリックして、**式**図形、BizTalk 式エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d633a-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="d633a-113">BizTalk 式エディタで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d633a-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="d633a-114">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d633a-114">For example:</span></span>  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     <span data-ttu-id="d633a-115">詳細については**式**図形と、BizTalk 式エディタでを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="d633a-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="d633a-116">BizTalk Server 管理からの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="d633a-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="d633a-117">BizTalk Server 管理コンソールで、Wcf-custom または Wcf-oracledb ポート構成の一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d633a-117">From the BizTalk Server Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span> 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="d633a-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="d633a-118">Enter a SOAP action for the WCF-Custom port</span></span>  
 
  
1. <span data-ttu-id="d633a-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d633a-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="d633a-120">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="d633a-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d633a-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="d633a-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="d633a-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="d633a-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="d633a-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d633a-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="d633a-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d633a-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="d633a-126">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-126">**By using the single action format**.</span></span> <span data-ttu-id="d633a-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d633a-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="d633a-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d633a-128">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   <span data-ttu-id="d633a-129">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-129">**By using the action mapping format**.</span></span> <span data-ttu-id="d633a-130">1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d633a-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="d633a-131">たとえば、送受信 (EMP テーブル内のレコードを挿入) するための Op1 と Op2 (EMP テーブル内のレコードを更新) するメッセージを受信する 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="d633a-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="d633a-132">このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d633a-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="d633a-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="d633a-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="d633a-134">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="d633a-134">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a><span data-ttu-id="d633a-135">Wcf-oracledb ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="d633a-135">Enter a SOAP action for the WCF-OracleDB port</span></span>  
  
1. <span data-ttu-id="d633a-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d633a-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="d633a-137">Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="d633a-137">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="d633a-138">手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="d633a-138">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="d633a-139">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="d633a-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d633a-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="d633a-141">ポートのプロパティ ダイアログ ボックスから、**型**ボックスの一覧は、先ほど追加した Wcf-oracledb ポートを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB port you added earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="d633a-142">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="d633a-142">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="d633a-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d633a-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="d633a-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d633a-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="d633a-145">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-145">**By using the single action format**.</span></span> <span data-ttu-id="d633a-146">Wcf-oracledb、送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d633a-146">Use this format if the WCF-OracleDB port sends and receive messages for a single operation.</span></span> <span data-ttu-id="d633a-147">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d633a-147">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   <span data-ttu-id="d633a-148">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="d633a-148">**By using the action mapping format**.</span></span> <span data-ttu-id="d633a-149">1 つの Wcf-oracledb ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d633a-149">Use this format if a single WCF-OracleDB port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="d633a-150">たとえば、送受信 (EMP テーブル内のレコードを挿入) するための Op1 と Op2 (EMP テーブル内のレコードを更新) するメッセージを受信する 1 つの Wcf-oracledb ポート、SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="d633a-150">For example, if a single WCF-OracleDB port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="d633a-151">このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d633a-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="d633a-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="d633a-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="d633a-153">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="d633a-153">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d633a-154">参照</span><span class="sxs-lookup"><span data-stu-id="d633a-154">See Also</span></span>  
[<span data-ttu-id="d633a-155">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="d633a-155">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)