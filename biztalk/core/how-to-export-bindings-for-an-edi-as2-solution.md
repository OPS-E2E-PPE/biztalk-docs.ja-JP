---
title: "EDI AS2 ソリューションのバインドをエクスポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 856ab630-66c4-4496-884a-fdbe641143c5
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aceeb81933324d5b3c164396290fe7b99cdc7295
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-for-an-edi-as2-solution"></a><span data-ttu-id="52f82-102">EDI AS2 ソリューションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="52f82-102">How to Export Bindings for an EDI-AS2 Solution</span></span>
<span data-ttu-id="52f82-103">このトピックでは、EDI または AS2 ソリューションとして設定されたコンピュータから構成をエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="52f82-103">This topic describes how to export the configuration from a computer set up as an EDI and/or AS2 solution.</span></span> <span data-ttu-id="52f82-104">これにより、自動化された方法で別のコンピュータと同じ構成を設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="52f82-104">This enables you to set up the same configuration on another computer in an automated fashion.</span></span> <span data-ttu-id="52f82-105">バインドのエクスポート元としては、アプリケーション、グループ、アセンブリがあります。</span><span class="sxs-lookup"><span data-stu-id="52f82-105">You can export the bindings from an application, group, or assembly.</span></span>  
  
 <span data-ttu-id="52f82-106">バインド ファイルを作成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="52f82-106">You create a binding file from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="52f82-107">.xml バインド ファイルには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成に関するすべての情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="52f82-107">The .xml binding file contains all information pertinent to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration.</span></span> <span data-ttu-id="52f82-108">このファイルには、特定のセキュリティ情報を除くすべての EDI および AS2 の構成プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52f82-108">This includes all EDI and AS2 configuration properties, with the exception of certain security information.</span></span> <span data-ttu-id="52f82-109">バインド ファイル (などの EDI および AS2 ノード) 内のノードの詳細については、次を参照してください。[バインド ファイルの構造体](../core/structure-of-a-binding-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="52f82-109">For detailed information about the nodes in a binding file (including EDI and AS2 nodes), see [Structure of a Binding File](../core/structure-of-a-binding-file.md).</span></span> <span data-ttu-id="52f82-110">EDI/AS2 バインドに関する一般的な情報については、以下の「[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バインド ファイルの EDI および AS2 ノード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52f82-110">For general information about the EDI/AS2 bindings, see "EDI and AS2 Nodes in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Binding File" below.</span></span>  
  
 <span data-ttu-id="52f82-111">また、.msi ファイル使用して、アプリケーションのエクスポート時にバインドをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="52f82-111">You can also export bindings as part of exporting an application using an .msi file.</span></span> <span data-ttu-id="52f82-112">詳細については、次を参照してください。、[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="52f82-112">For more information, see the [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span> <span data-ttu-id="52f82-113">BTSTask コマンドを使用して、バインドをエクスポートおよびインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="52f82-113">Or you can use the BTSTask command to export and import bindings.</span></span> <span data-ttu-id="52f82-114">BTSTask の詳細については、次を参照してください。 [BTSTask コマンドライン リファレンス](../core/btstask-command-line-reference.md)です。</span><span class="sxs-lookup"><span data-stu-id="52f82-114">For more information about BTSTask, see [BTSTask Command-Line Reference](../core/btstask-command-line-reference.md).</span></span>  
  
 <span data-ttu-id="52f82-115">**バインドをエクスポートします。**</span><span class="sxs-lookup"><span data-stu-id="52f82-115">**Exporting Bindings**</span></span>  
  
 <span data-ttu-id="52f82-116">構成をエクスポートすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって、バインドされているすべてのパーティの EDI プロパティおよびその他のパーティ情報が自動的にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="52f82-116">When you export the configuration, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will automatically export the EDI Properties, and other party information, of all bound parties.</span></span> <span data-ttu-id="52f82-117">グローバル パーティ情報のエクスポートをアクティブ化すると、オーケストレーションにバインドされていないパーティのプロパティおよびグローバル EDI プロパティも [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="52f82-117">If you activate the exporting of global party information, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also export properties for parties that are not bound to an orchestration, and global EDI properties.</span></span> <span data-ttu-id="52f82-118">グローバル パーティ情報は、次の 3 つの方法でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="52f82-118">You can export global party information in three ways:</span></span>  
  
-   <span data-ttu-id="52f82-119">[バインドのエクスポート] ダイアログ ボックスで "グローバル パーティ情報をエクスポートする" プロパティをオンにする。</span><span class="sxs-lookup"><span data-stu-id="52f82-119">By checking the Export Global Party Information property in the Export Bindings dialog box.</span></span>  
  
-   <span data-ttu-id="52f82-120">MSI ファイルのエクスポート ウィザードの [リソースの選択] ペインで [グローバル パーティ] をオンにする。</span><span class="sxs-lookup"><span data-stu-id="52f82-120">By checking the Global Parties checkbox in the Select Resources pane of the Export MSI File Wizard.</span></span>  
  
-   <span data-ttu-id="52f82-121">次の手順に従って BTSTask コマンド ライン ツールで GlobalParties スイッチを使用する。</span><span class="sxs-lookup"><span data-stu-id="52f82-121">By using the GlobalParties switch in the BTSTask command line tool, as follows:</span></span>  
  
    ```  
    BTSTask ExportBindings -Destination:value ((([-ApplicationName:value] | [-AssemblyName:value]) [-GlobalParties]) | [-GroupLevel])  
    ```  
  
 <span data-ttu-id="52f82-122">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-122">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="52f82-123">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、EDIFACT プロパティから UNB6.1 および UNB6.2 フィールドが削除され、X12 プロパティから ISA1、ISA2、ISA3、および ISA4 フィールドが削除されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] removes UNB6.1 and UNB6.2 fields from EDIFACT Properties, and ISA1, ISA2, ISA3, and ISA4 fields from X12 Properties.</span></span>  
  
 <span data-ttu-id="52f82-124">バインドのエクスポート、アプリケーションのエクスポート、および BTSTask コマンド以外にも、手動で XML バインド ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="52f82-124">In addition to using the export-bindings, export-application, or BTSTask commands, you can create an XML binding file manually.</span></span> <span data-ttu-id="52f82-125">これにより、基幹業務アプリケーションからパーティおよび EDI 設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="52f82-125">By doing so, you can export party and EDI settings from a line-of-business application.</span></span> <span data-ttu-id="52f82-126">バインドのインポート コマンドまたは BTSTask コマンドを使用して、バインドをインポートすることも可能になります。</span><span class="sxs-lookup"><span data-stu-id="52f82-126">You could then import the bindings using the import-bindings command or the BTSTask command.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="52f82-127">前提条件</span><span class="sxs-lookup"><span data-stu-id="52f82-127">Prerequisites</span></span>  
 <span data-ttu-id="52f82-128">ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="52f82-128">You must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="52f82-129">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマニュアルの「BizTalk アプリケーションの展開と管理に必要なアクセス許可」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52f82-129">For more information, see "Permissions Required for Deploying and Managing a BizTalk Application" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
### <a name="exporting-the-configuration-into-a-binding-file"></a><span data-ttu-id="52f82-130">バインド ファイルへの構成のエクスポート</span><span class="sxs-lookup"><span data-stu-id="52f82-130">Exporting the Configuration into a Binding File</span></span>  
  
1.  <span data-ttu-id="52f82-131">構成のエクスポート元となるコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="52f82-131">On the computer that you want to export the configuration from, open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
2.  <span data-ttu-id="52f82-132">構成のコピー元 をポイントする BizTalk アプリケーションを右クリックして**エクスポート**、クリックして**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="52f82-132">Right-click the BizTalk Application that you want to copy the configuration from, point to **Export**, and then click **Bindings**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52f82-133">BTSTask ユーティリティを使用して、構成をエクスポートおよびインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="52f82-133">You can also use the BTSTask utility to export or import the configuration.</span></span>  
  
3.  <span data-ttu-id="52f82-134">エクスポート オプションを選択して、現在のアプリケーションまたはグループからバインドをエクスポートするか、またはアセンブリのバインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="52f82-134">Select the export option, selecting to export from the current application or group, or exporting bindings for an assembly.</span></span>  
  
4.  <span data-ttu-id="52f82-135">すべてのパーティをエクスポートするし、非依存プロパティには、オーケストレーションがバインドされていない場合でもクリックして**グローバル パーティ情報をエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="52f82-135">If you want to export all parties and their non-sensitive properties, even if an orchestration is not bound to them, click **Export Global Party information**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52f82-136">クリックしない場合**グローバル パーティ情報をエクスポート**、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルに、オーケストレーションにバインドされているパーティのプロパティがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="52f82-136">If you do not click **Export Global Party information**, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will export properties for any parties that are bound to an orchestration, into the binding file.</span></span> <span data-ttu-id="52f82-137">ただしはエクスポートされません、オーケストレーションにバインドされていないパーティをクリックした場合を除き、**グローバル パーティ情報をエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="52f82-137">However, it will not export any parties that are not bound to an orchestration, unless you click **Export Global Party information**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52f82-138">バインド ファイルを生成中に、**グローバル パーティ情報をエクスポート**プロパティが選択されているコンピューターで定義されたすべてのパーティの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52f82-138">The binding file generated while the **Export Global Party information** property is selected will include the configuration of all parties defined on the computer.</span></span> <span data-ttu-id="52f82-139">コンピュータで定義されたパーティの完全なセットのサブセットの構成は、エクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="52f82-139">It is not possible to export the configuration of a subset of the complete set of parties defined on a computer.</span></span>  
  
5.  <span data-ttu-id="52f82-140">をクリックして**OK**バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="52f82-140">Click **OK** to export the bindings.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="52f82-141"> では、パスワード、セキュリティ情報、認証情報などの EDI の機密フィールドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="52f82-141"> will not export any EDI sensitive fields, such as passwords or security/authentication information.</span></span> <span data-ttu-id="52f82-142">ただし、EDI の機密フィールドの空白文字列はエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="52f82-142">It will export a blank string for any EDI sensitive field.</span></span> <span data-ttu-id="52f82-143">バインドを別のコンピュータにインポートしたら、EDI の機密フィールドの値を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52f82-143">After importing the bindings onto another computer, you must manually set the values for EDI sensitive fields.</span></span>  
  
6.  <span data-ttu-id="52f82-144">バインドをインポートするコンピュータを後から設定するために、パスワード、セキュリティ情報、認証情報などの EDI の機密フィールドをメモなどに記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="52f82-144">Manually note any EDI sensitive fields, such as passwords or security/authentication information, for later setting on the computer that you import the bindings onto.</span></span>  
  
## <a name="edi-and-as2-nodes-in-the-biztalk-server-binding-file"></a><span data-ttu-id="52f82-145">BizTalk Server バインド ファイルの EDI および AS2 ノード</span><span class="sxs-lookup"><span data-stu-id="52f82-145">EDI and AS2 Nodes in the BizTalk Server Binding File</span></span>  
 <span data-ttu-id="52f82-146">構成をエクスポートする場合、**グローバル パーティ情報をエクスポート**プロパティを選択すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルを次のノードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-146">If you export your configuration with the **Export Global Party information** property selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a binding file that has that following nodes:</span></span>  
  
```  
EdiData  
   PartyEDIProperties  
      PartnerAgreement  
         Contacts  
      PartnerEdifact  
         PartnerEdifactReceiverGroups  
         PartnerEdifactSenderGroups  
      PartnerAckValidation  
      PartnerX12  
      PartnerX12ReceiverGroups  
      PartnerX12SenderGroups  
      PartnerBatchUpdatable  
      PartnerAS2CommonUpdatable  
      PartnerAS2  
```  
  
 <span data-ttu-id="52f82-147">EDI グローバル プロパティは、次のノードのバインド ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-147">EDI global properties will be added to the binding file in the following nodes.</span></span>  
  
```  
EDIGlobalProperties  
   EDIGlobalProperties  
      GlobalCommon  
      GlobalEdiFact  
      GlobalX12  
```  
  
 <span data-ttu-id="52f82-148">EDI および AS2 ノードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バインド ファイルの末尾に追加されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-148">EDI and AS2 nodes are added to the end of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] binding file.</span></span> <span data-ttu-id="52f82-149">EdiData ノードは、Party Collection ノードの下の Party サブノードに追加され、EdiGlobalProperties ノードは、Party Collection ノードの後に同じレベルで追加されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-149">The EdiData node is added to the Party subnode under the Party Collection node, and the EdiGlobalProperties node is added after, and at the same level as, the Party Collection node.</span></span> <span data-ttu-id="52f82-150">BizTalk バインド ファイル内の EDI および AS2 ノードに関する詳細については、次を参照してください。[バインド ファイルの構造体](../core/structure-of-a-binding-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="52f82-150">For more information about the EDI and AS2 nodes in the BizTalk binding file, see [Structure of a Binding File](../core/structure-of-a-binding-file.md).</span></span>  
  
 <span data-ttu-id="52f82-151">EdiData ノードは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="52f82-151">The EdiData node is optional.</span></span> <span data-ttu-id="52f82-152">ただし、EdiData ノードが存在する場合、EdiData の下のサブノードも存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52f82-152">However, if the EdiData node is present, the subnodes under EdiData are required.</span></span> <span data-ttu-id="52f82-153">同様に、EdiGlobalProperties ノードも省略可能ですが、EdiGlobalProperties ノードが存在する場合は、このノードの下のサブノードも存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52f82-153">Likewise, the EdiGlobalProperties node is optional; however, if the EdiGlobalProperties node is present, the subnodes under it are required.</span></span>  
  
 <span data-ttu-id="52f82-154">EDI および AS2 バインド ファイル ノードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのパートナー アグリーメント マネージャーのプロパティ ページに直接は対応していません。</span><span class="sxs-lookup"><span data-stu-id="52f82-154">EDI and AS2 binding file nodes do not correspond directly to the property pages in the Partner Agreement Manager in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="52f82-155">一部の EDI および AS2 バインド ファイル ノードには、sender ロールで使用されるプロパティと receiver ロールで使用されるプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52f82-155">Some EDI and AS2 binding file nodes include properties used for sender roles and properties used for receiver roles.</span></span> <span data-ttu-id="52f82-156">ロールは、ノードの IsSender プロパティによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-156">The role is indicated by the IsSender property in the node.</span></span> <span data-ttu-id="52f82-157">sender ロールおよび receiver ロールで使用されないノード (PartnerAgreement、PartnerBatchUpdatable、PartnerAS2Updatable、および GlobalCommon) では、IsSender は常に False です。</span><span class="sxs-lookup"><span data-stu-id="52f82-157">For those nodes that are not used for both sender and receiver roles (PartnerAgreement, PartnerBatchUpdatable, PartnerAS2Updatable, and GlobalCommon), IsSender is always False.</span></span>  
  
 <span data-ttu-id="52f82-158">PartnerEdifact ノードおよび PartnerX12 ノードには、IsSender が True または False のいずれに設定されている場合でも、receiver ロールと sender ロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="52f82-158">The PartnerEdifact and PartnerX12 nodes contain properties for both the receiver and sender roles, whether or not IsSender is set to True or False.</span></span> <span data-ttu-id="52f82-159">たとえば、IsSender が True に設定されている場合でも、PartnerEdifact には Una1 フィールド (インターチェンジ受信者としてのパーティで使用される) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52f82-159">For example, PartnerEdifact will include a Una1 field (used for the party as an interchange receiver), even when IsSender is True.</span></span> <span data-ttu-id="52f82-160">また、IsSender が False に設定されている場合でも、PartnerEdifact には Unb5CheckDup フィールド (インターチェンジ送信者としてのパーティで使用される) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52f82-160">PartnerEdifact will also include a Unb5CheckDup field (used for the party as an interchange sender), even when IsSender is False.</span></span> <span data-ttu-id="52f82-161">ただし、IsSender が True に設定されている場合は、インターチェンジ受信者としてのパーティのフィールドは UI またはエンジンで使用されず、デフォルト値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-161">However, when IsSender is True, the fields for the party as an interchange receiver are not used in the UI or by the engine, but are given default values.</span></span> <span data-ttu-id="52f82-162">同様に、IsSender が False に設定されている場合は、インターチェンジ送信者としてのパーティのフィールドは UI またはエンジンで使用されず、デフォルト値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-162">Likewise, when IsSender is False, the fields for the party as an interchange sender are not used in the UI or by the engine, but are given default values.</span></span>  
  
 <span data-ttu-id="52f82-163">プロパティのデフォルトが Null の場合、フィールドで値が指定されていない限り、フィールドはバインド ファイルに含まれません。</span><span class="sxs-lookup"><span data-stu-id="52f82-163">If the default of a property is null, the field will not be included in the binding file unless that field has been given a value.</span></span>  
  
 <span data-ttu-id="52f82-164">バインド ファイルのデータは、BizTalk 管理データベース (BizTalkMgmtDb) のテーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="52f82-164">Binding file data is saved in tables of the BizTalk Management database (BizTalkMgmtDb).</span></span>