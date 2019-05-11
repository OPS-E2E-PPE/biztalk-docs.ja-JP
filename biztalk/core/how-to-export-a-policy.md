---
title: ポリシーをエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], exporting
- policies, exporting
- exporting, policies
ms.assetid: 2e46d96a-7762-479b-be20-bd590b2a4f0a
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a6f199ebda349192e8b950af7023c45b4e4c97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337813"
---
# <a name="how-to-export-a-policy"></a><span data-ttu-id="32251-102">ポリシーをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="32251-102">How to Export a Policy</span></span>
<span data-ttu-id="32251-103">ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、1 つ以上のポリシーと関連付けられたボキャブラリをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32251-103">This topic describes how to use the BizTalk Server Administration console or the command line to export one or more policies and associated vocabularies.</span></span>  
  
 <span data-ttu-id="32251-104">ポリシーをエクスポートする際には、次の重要事項を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="32251-104">When exporting a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="32251-105">BizTalk Server 管理コンソールを使用すると、BizTalk グループまたは BizTalk アプリケーションからポリシーとボキャブラリのそれぞれをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="32251-105">Using the BizTalk Server Administration console, you can export policies from a BizTalk group or a BizTalk application as well as the vocabularies to export.</span></span> <span data-ttu-id="32251-106">BTSTask を使用すると、アプリケーションからポリシーをエクスポートすることができ、関連付けられているすべてのボキャブラリも同様にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="32251-106">Using BTSTask, you can export policies from an application, and all of the associated vocabularies will be exported as well.</span></span> <span data-ttu-id="32251-107">エクスポートするボキャブラリを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="32251-107">You cannot select the vocabularies to export.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="32251-108">管理コンソールを使用した場合は、エクスポートするボキャブラリを選択できます。</span><span class="sxs-lookup"><span data-stu-id="32251-108">When using the administration console, you can select which vocabularies to export.</span></span> <span data-ttu-id="32251-109">ポリシーに関連付けられているすべてのボキャブラリをエクスポートするよう選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32251-109">We recommend that you select for export all of the vocabularies associated with a policy.</span></span> <span data-ttu-id="32251-110">これにより、エクスポート先の環境に、必要なボキャブラリを確実に存在させることができます。</span><span class="sxs-lookup"><span data-stu-id="32251-110">This way, you can be sure that the required vocabularies are present in the destination environment.</span></span> <span data-ttu-id="32251-111">必要なボキャブラリが既にエクスポート先の環境に展開されていたとしても、関連付けられているポリシーが削除された場合は、ボキャブラリも同様に削除されます。</span><span class="sxs-lookup"><span data-stu-id="32251-111">Even if the required vocabularies were previously deployed to the destination environment, if their associated policy was deleted, they would have been deleted as well.</span></span> <span data-ttu-id="32251-112">これは、ポリシーを削除すると、そのボキャブラリについても、別のポリシーで使用されている以外のものはすべて削除されるためです。</span><span class="sxs-lookup"><span data-stu-id="32251-112">This is because when you delete a policy, all of its vocabularies that are not being used by another policy are deleted.</span></span>  
  
-   <span data-ttu-id="32251-113">インポートできます、ポリシーを別の BizTalk グループまたは別の BizTalk グループ内のアプリケーション」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="32251-113">You can then import the policy or policies into a different BizTalk group or an application in a different BizTalk group, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
-   <span data-ttu-id="32251-114">ポリシーをエクスポートするには、そのポリシーが BizTalk グループのルール エンジン データベースにあらかじめ存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="32251-114">Before you can export a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="32251-115">」の説明に従って、ルール エンジン データベースにポリシーをインポートするためにいくつかの方法がある[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="32251-115">There are several ways to import a policy into the Rule Engine database, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="32251-116">ルール エンジン展開ウィザードを使用してルール エンジン データベースからポリシーを削除すると、そのポリシーは、管理コンソールでは表示されたままになりますが、エクスポートすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="32251-116">When you remove a policy from the Rule Engine database by using the Rule Engine Deployment Wizard, it will still display in the administration console, but you will not be able to export it.</span></span> <span data-ttu-id="32251-117">ルール エンジン展開ウィザードの詳細については、次を参照してください。[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。</span><span class="sxs-lookup"><span data-stu-id="32251-117">For more information about the Rule Engine Deployment Wizard, see [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="32251-118">エクスポートに管理コンソールを使用する場合、ポリシーとボキャブラリは .xml ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="32251-118">When you use the administration console for exporting, the policies and vocabularies are exported into an .xml file.</span></span> <span data-ttu-id="32251-119">エクスポートに BTSTask コマンド ライン ツールを使用する場合、ポリシーとボキャブラリはアプリケーションの .msi ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="32251-119">When you use the BTSTask command-line tool for exporting, the policies and vocabularies are exported into an application .msi file.</span></span>  
  
-   <span data-ttu-id="32251-120">BTSTask にはポリシーをエクスポートする専用のコマンドはありませんが、BTSTask の ExportApp コマンドを使用して、他のアイテムを含めずに目的のポリシーだけを選択的にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="32251-120">BTSTask does not provide a specific command for exporting policies; however you can use the ExportApp command of BTSTask to selectively export only the policies you want, and no other artifacts.</span></span> <span data-ttu-id="32251-121">これにより、そのポリシーを含んだアプリケーションの .msi ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="32251-121">This generates an application .msi file containing the policies.</span></span> <span data-ttu-id="32251-122">ImportApp コマンドを使用して、その .msi ファイルを別の BizTalk グループにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="32251-122">You can use the ImportApp command to import the .msi file into a different BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32251-123">前提条件</span><span class="sxs-lookup"><span data-stu-id="32251-123">Prerequisites</span></span>  
 <span data-ttu-id="32251-124">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32251-124">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="32251-125">BizTalk Server 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32251-125">You must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="32251-126">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="32251-126">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="32251-127">ビジネス ルール エンジンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32251-127">The Business Rule Engine must be installed.</span></span> <span data-ttu-id="32251-128">詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)します。</span><span class="sxs-lookup"><span data-stu-id="32251-128">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
-   <span data-ttu-id="32251-129">エクスポートするポリシーが、BizTalk グループのルール エンジン データベースに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="32251-129">The policy that you want to export must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="32251-130">アプリケーションからポリシーをエクスポートする場合は、アプリケーションにも追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32251-130">If you want to export the policy from an application, it must have also been added to the application as well.</span></span>  
  
## <a name="to-export-a-policy"></a><span data-ttu-id="32251-131">ポリシーをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="32251-131">To export a policy</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="32251-132">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="32251-132">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="32251-133">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="32251-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="32251-134">コンソール ツリーで、展開**BizTalk Server 管理**BizTalk グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="32251-134">In the console tree, expand **BizTalk Server Administration** and expand the BizTalk group.</span></span>  
  
3. <span data-ttu-id="32251-135">すべての BizTalk グループの右クリックでポリシーをエクスポートするポリシーを選択する場合、**アプリケーション**フォルダー、をクリックして**エクスポート**、 をクリックし、**ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="32251-135">If you want to select the policies to export from all of the policies in a BizTalk group right-click the **Applications** folder, click **Export**, and then click **Policies**.</span></span>  
  
    <span data-ttu-id="32251-136">OR</span><span class="sxs-lookup"><span data-stu-id="32251-136">OR</span></span>  
  
    <span data-ttu-id="32251-137">特定のアプリケーションでポリシーをエクスポートする場合は、アプリケーション フォルダーを展開、アプリケーションを右クリックし、をクリックして**エクスポート**、 をクリックし、**ポリシー**します。</span><span class="sxs-lookup"><span data-stu-id="32251-137">If you want to export the policies in a particular application, expand the Applications folder, right-click the application, click **Export**, and then click **Policies**.</span></span>  
  
    <span data-ttu-id="32251-138">OR</span><span class="sxs-lookup"><span data-stu-id="32251-138">OR</span></span>  
  
    <span data-ttu-id="32251-139">特定のポリシーだけをエクスポートする場合は、ポリシーを含んでいる [ポリシー] フォルダーをクリックして、ポリシーを右クリックしておよびクリックして**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="32251-139">If you want to export only a particular policy, click the Policies folder that contains the policy, right-click the policy, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="32251-140">ポリシーのエクスポート ページで**エクスポートするポリシー**、エクスポートするポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="32251-140">On the Export Policies page, in **Policies to export**, select the policies to export.</span></span>  
  
5. <span data-ttu-id="32251-141">**をエクスポートするボキャブラリ**エクスポートしないボキャブラリのチェック ボックスをオフをエクスポートするボキャブラリのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="32251-141">In **Vocabularies to export**, select the check boxes of the vocabularies to export, and clear the checkboxes of any vocabularies you do not want to export.</span></span> <span data-ttu-id="32251-142">エクスポートするポリシーで使用されるボキャブラリは自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="32251-142">The vocabularies used by this policy are automatically selected.</span></span>  
  
6. <span data-ttu-id="32251-143">**エクスポートするファイル**に、ポリシーまたはポリシーをエクスポートする XML ファイルのパスを入力し、クリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="32251-143">In **File to export** into, type the path of the XML file to which to export the policy or policies, and then click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="32251-144">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="32251-144">Using the command line</span></span>  
  
1.  <span data-ttu-id="32251-145">/ResourceSpec オプションを使用するポリシーをエクスポートする」の説明に従って、BizTalk アプリケーションにアイテムを一覧表示する XML ファイルを生成する、BTSTask の ListApp コマンドを使用して[ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="32251-145">Use the BTSTask ListApp command with the /ResourceSpec option to generate an XML file that lists the artifacts in the BizTalk application from which you want to export a policy, as described in [ListApp Command](../core/listapp-command.md).</span></span>  
  
2.  <span data-ttu-id="32251-146">前の手順で生成した XML ファイルを編集して、エクスポートするポリシー以外のアイテムをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="32251-146">Edit the XML file generated in the previous step, deleting all of the artifacts except for the policy or policies that you want to export.</span></span>  
  
3.  <span data-ttu-id="32251-147">BTSTask の ExportApp コマンドを使用します。ここでは、/ResourceSpec パラメーターに変更後の XML ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="32251-147">Use the BTSTask ExportApp command, and specify the modified XML file for the /ResourceSpec parameter.</span></span> <span data-ttu-id="32251-148">詳細については、次を参照してください。 [ExportApp コマンド](../core/exportapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="32251-148">For more information, see [ExportApp Command](../core/exportapp-command.md).</span></span>  
  
     <span data-ttu-id="32251-149">BTSTask によって、指定したポリシーとそれに関連付けられているすべてのボキャブラリがアプリケーションの .msi ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="32251-149">BTSTask exports the specified policies and all of their associated vocabularies into an application .msi file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32251-150">参照</span><span class="sxs-lookup"><span data-stu-id="32251-150">See Also</span></span>  
 <span data-ttu-id="32251-151">[BizTalk アプリケーション、バインド、およびポリシーのエクスポート](../core/exporting-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="32251-151">[Exporting BizTalk Applications, Bindings, and Policies](../core/exporting-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="32251-152">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="32251-152">Managing Policies</span></span>](../core/managing-policies.md)