---
title: BizTalk で Oracle データベースの SOAP アクションの構成 |Microsoft ドキュメント
description: Visual Studio で SOAP アクションを入力するか、Wcf-custom アダプターまたは Wcf-oracledb アダプターの BizTalk アダプター パック (BAP) でを使用
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
ms.openlocfilehash: b2577a221385cdef2e210798b3e8170433ff0e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215402"
---
# <a name="configure-the-soap-action-for-oracle-database"></a><span data-ttu-id="dfa1f-103">Oracle データベースの SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-103">Configure the SOAP action for Oracle Database</span></span>
<span data-ttu-id="dfa1f-104">WCF ベースを使用して Oracle データベースで任意の操作を完了する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターのユーザーは、SOAP アクションを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-104">To complete any operation on the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], adapter users must enter a SOAP action.</span></span> <span data-ttu-id="dfa1f-105">SOAP アクションは、どのような操作を完了する必要があるアダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-105">The SOAP action communicates to the adapter what action should be completed.</span></span> <span data-ttu-id="dfa1f-106">デザイン時に、または実行時に SOAP アクションを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-106">You can enter the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="dfa1f-107">ただし、入力 SOAP アクション両方デザイン時に時刻を実行すると、デザイン時に入力するアクションはオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-107">However, if you enter the SOAP action both at design time and run time, the action you enter at design time is overridden.</span></span>  
  
 <span data-ttu-id="dfa1f-108">SOAP アクションを指定する方法の詳細については、次を参照してください。 [WCF 送信アダプタ用の SOAP アクションの指定](../../core/specifying-soap-actions-for-wcf-send-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="dfa1f-109">Visual Studio からの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="dfa1f-110">Visual Studio から、必要がありますを指定する SOAP アクションのオーケストレーションの一部としてを使用して、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-110">From Visual Studio, you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="dfa1f-111">BizTalk オーケストレーションが含まれる、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックスします。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="dfa1f-112">ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="dfa1f-113">BizTalk 式エディターで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="dfa1f-114">例:</span><span class="sxs-lookup"><span data-stu-id="dfa1f-114">For example:</span></span>  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     <span data-ttu-id="dfa1f-115">詳細については**式**図形と、BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="dfa1f-116">BizTalk Server 管理コンソールからの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="dfa1f-117">BizTalk Server 管理コンソールで、Wcf-custom または Wcf-oracledb ポートの構成の一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-117">From the BizTalk Server Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span> 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="dfa1f-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-118">Enter a SOAP action for the WCF-Custom port</span></span>  
 
  
1.  <span data-ttu-id="dfa1f-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="dfa1f-120">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="dfa1f-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="dfa1f-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="dfa1f-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="dfa1f-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="dfa1f-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="dfa1f-126">**シングル アクション形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-126">**By using the single action format**.</span></span> <span data-ttu-id="dfa1f-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="dfa1f-128">例:</span><span class="sxs-lookup"><span data-stu-id="dfa1f-128">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
        ```  
  
    -   <span data-ttu-id="dfa1f-129">**アクション マッピング形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-129">**By using the action mapping format**.</span></span> <span data-ttu-id="dfa1f-130">1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="dfa1f-131">たとえば、1 つの WCF カスタム ポートを送信および (レコードを挿入する、EMP テーブル内) Op1、Op2 (レコードを更新する、EMP テーブル内) のメッセージを受け取る場合、SOAP アクションは、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="dfa1f-132">このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="dfa1f-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="dfa1f-134">各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-134">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a><span data-ttu-id="dfa1f-135">Wcf-oracledb ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-135">Enter a SOAP action for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="dfa1f-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="dfa1f-137">Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-137">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="dfa1f-138">手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-138">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="dfa1f-139">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="dfa1f-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="dfa1f-141">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-oracledb ポートを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB port you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="dfa1f-142">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-142">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="dfa1f-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="dfa1f-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="dfa1f-145">**シングル アクション形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-145">**By using the single action format**.</span></span> <span data-ttu-id="dfa1f-146">Wcf-oracledb、送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-146">Use this format if the WCF-OracleDB port sends and receive messages for a single operation.</span></span> <span data-ttu-id="dfa1f-147">例:</span><span class="sxs-lookup"><span data-stu-id="dfa1f-147">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
        ```  
  
    -   <span data-ttu-id="dfa1f-148">**アクション マッピング形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-148">**By using the action mapping format**.</span></span> <span data-ttu-id="dfa1f-149">1 つの Wcf-oracledb ポートを送信および複数の操作のメッセージを受け取る場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-149">Use this format if a single WCF-OracleDB port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="dfa1f-150">たとえば、1 つの Wcf-oracledb ポートは、(レコードを挿入する、EMP テーブル内) Op1、Op2 (レコードを更新する、EMP テーブル内) のメッセージを送受信場合、SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-150">For example, if a single WCF-OracleDB port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="dfa1f-151">このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="dfa1f-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="dfa1f-153">各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="dfa1f-153">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dfa1f-154">参照</span><span class="sxs-lookup"><span data-stu-id="dfa1f-154">See Also</span></span>  
[<span data-ttu-id="dfa1f-155">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="dfa1f-155">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)