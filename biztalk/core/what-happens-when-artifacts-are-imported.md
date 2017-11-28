---
title: "アイテムのインポート時の動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing, artifacts
- artifacts, importing
ms.assetid: a83957df-6e16-419a-b693-87985b498cc4
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d87e814fd43545d18db0d6e4fd0c585279eb5261
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-when-artifacts-are-imported"></a><span data-ttu-id="3219d-102">アイテムのインポート時の動作</span><span class="sxs-lookup"><span data-stu-id="3219d-102">What Happens When Artifacts Are Imported</span></span>
<span data-ttu-id="3219d-103">このトピックでは、アイテムがインポートされるときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="3219d-103">This topic describes what happens to artifacts when they are imported.</span></span> <span data-ttu-id="3219d-104">アイテムのインポートには次の 3 つの方法があり、ここではそれぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3219d-104">There are three ways to import artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="3219d-105">BizTalk .msi ファイル内のアイテムを BizTalk グループまたはアプリケーションにインポートする。</span><span class="sxs-lookup"><span data-stu-id="3219d-105">Importing artifacts in a BizTalk .msi file into a BizTalk group or application</span></span>  
  
-   <span data-ttu-id="3219d-106">.xml ポリシー ファイルを BizTalk グループにインポートする。</span><span class="sxs-lookup"><span data-stu-id="3219d-106">Importing an .xml policy file into a BizTalk group</span></span>  
  
-   <span data-ttu-id="3219d-107">バインド ファイルを BizTalk グループまたはアプリケーションにインポートする。</span><span class="sxs-lookup"><span data-stu-id="3219d-107">Importing a binding file into a BizTalk group or application</span></span>  
  
## <a name="importing-a-biztalk-msi-file"></a><span data-ttu-id="3219d-108">BizTalk .msi ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="3219d-108">Importing a BizTalk .msi file</span></span>  
 <span data-ttu-id="3219d-109">BizTalk .msi ファイルを BizTalk グループまたはアプリケーションにインポートすると、そのファイルに含まれているアイテムが BizTalk Server で次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-109">When you import a BizTalk .msi file into a BizTalk group or application, BizTalk Server handles the artifacts that it contains as follows:</span></span>  
  
-   <span data-ttu-id="3219d-110">インポート時にこのアプリケーションからグループ内の他のアプリケーションへの参照を追加した場合は、その参照が BizTalk 管理データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-110">If during import you added any references from this application to other applications in the group, the reference is added to the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="3219d-111">このオプションを指定すると、アプリケーション内の既存のアイテムが、完全な名前とバージョン番号 (該当する場合) が同じである .msi ファイル内のアイテムで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="3219d-111">If you specified this option, existing artifacts in the application are overwritten by artifacts in the .msi file that have the same full name and version number (if applicable).</span></span>  
  
-   <span data-ttu-id="3219d-112">アプリケーションにバインド ファイルが追加されている場合に、インポート時にそのファイルのターゲット環境を選択すると、それらのバインドが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-112">If binding files have been added to the application, and you select their target environment during import, the bindings are applied.</span></span>  
  
-   <span data-ttu-id="3219d-113">インポート時に実行されるように構成されている処理前または処理後のスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-113">Pre- or post-processing scripts that are configured to run on import will run.</span></span>  
  
-   <span data-ttu-id="3219d-114">ファイルベースのアイテム データがシリアル化され、BizTalk 管理データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-114">File-based artifact data is serialized and stored in the BizTalk Management database.</span></span> <span data-ttu-id="3219d-115">これには、アセンブリ、仮想ディレクトリ、ファイル、スクリプト、証明書、および BAM アイテムのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3219d-115">This includes data for assemblies, virtual directories, files, scripts, certificates, and BAM artifacts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3219d-116">セキュリティ上の理由により、各証明書の秘密キーはエクスポート時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-116">For security reasons, the private key is removed from each certificate when it is exported.</span></span> <span data-ttu-id="3219d-117">したがって、BizTalk 管理データベースには秘密キーが格納されません。</span><span class="sxs-lookup"><span data-stu-id="3219d-117">Therefore, no private keys are stored in the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="3219d-118">ポリシー データがルール エンジン データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-118">Policy data is stored in the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="3219d-119">BAM アイテムが BAM プライマリ インポート データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-119">BAM artifacts are stored in the BAM Primary Import database.</span></span> <span data-ttu-id="3219d-120">BAM 定義が展開されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-120">BAM definitions are deployed.</span></span>  
  
-   <span data-ttu-id="3219d-121">"MSI ファイル インポートのグローバル アセンブリ キャッシュに追加します" 展開オプションが設定されている BizTalk アセンブリと .NET アセンブリが、グローバル アセンブリ キャッシュ (GAC) に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-121">BizTalk assemblies and .NET assemblies that have the "Add to GAC on import" deployment option configured are added to the global assembly cache (GAC).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3219d-122">アイテム データは BizTalk Server のデータベースに格納されるため、後からアプリケーションを .msi ファイルにエクスポートしたときに、BizTalk Server はアプリケーションとそのアイテムに関連するすべての構成情報とデータをこれらのデータベースから取得し、.msi ファイルに取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3219d-122">Because the artifact data is stored in the BizTalk Server databases, when you later export the application into an .msi file, BizTalk Server can retrieve from the databases all of the configuration information and data associated with the application and its artifacts and include it in the .msi file.</span></span> <span data-ttu-id="3219d-123">.msi ファイルを別の BizTalk グループにインポートすると、すべてのアイテム構成情報とデータが新しいグループで再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-123">When you import the .msi file into another BizTalk group, all of the artifact configuration information and data is recreated in the new group.</span></span>  
  
 <span data-ttu-id="3219d-124">アプリケーションをインポートした後に、管理コンソールまたは BTSTask を使用して、アプリケーション内のアイテム全体を 1 つのエンティティとして、または各アイテムを個別に、表示、管理、展開できます。</span><span class="sxs-lookup"><span data-stu-id="3219d-124">After you import an application, you can view, manage, and deploy the artifacts in the application either together as a single entity or individually by using the Administration console or BTSTask.</span></span> <span data-ttu-id="3219d-125">詳細については、次を参照してください。[アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)です。</span><span class="sxs-lookup"><span data-stu-id="3219d-125">For more information, see [Application Deployment and Management Tools](../core/application-deployment-and-management-tools.md).</span></span>  
  
## <a name="importing-a-policy"></a><span data-ttu-id="3219d-126">ポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="3219d-126">Importing a policy</span></span>  
 <span data-ttu-id="3219d-127">.xml ファイルからポリシーをインポートすると、そのポリシーがルール エンジン データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-127">When you import a policy from an .xml file, the policy is added to the Rule Engine database.</span></span> <span data-ttu-id="3219d-128">BizTalk .msi ファイル内のポリシーをインポートする場合とは異なり、ポリシーは BizTalk 管理データベース内のどのアプリケーションにも関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="3219d-128">Unlike when you import a policy within a BizTalk .msi file, the policy is not associated with any application in the BizTalk Management database.</span></span> <span data-ttu-id="3219d-129">[ポリシー] ノードで、ポリシーが表示されます、\<すべてのアイテム >、BizTalk Server 管理コンソール内のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3219d-129">The policy displays in the Policies node of the \<All Artifacts> folder in the BizTalk Server Administration console.</span></span> <span data-ttu-id="3219d-130">インポートしたポリシーは、グループ内のアプリケーションが使用できるように公開できます。</span><span class="sxs-lookup"><span data-stu-id="3219d-130">After importing the policy you can publish it to make it available for applications in the group to use.</span></span> <span data-ttu-id="3219d-131">詳細については、次を参照してください。[ポリシーの管理](../core/managing-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="3219d-131">For more information, see [Managing Policies](../core/managing-policies.md).</span></span>  
  
## <a name="importing-a-binding-file"></a><span data-ttu-id="3219d-132">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="3219d-132">Importing a binding file</span></span>  
 <span data-ttu-id="3219d-133">バインド ファイルを BizTalk グループにインポートすると、そのファイル内のバインドによって、グループ内でそれらのバインドと同じ名前を持つ既存のバインドがすべて上書きされ、構成が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-133">When you import a binding file into a BizTalk group, any bindings that currently exist in the group having the same name as bindings in the imported file are overwritten by the bindings in the imported file, and the configuration is applied.</span></span>  
  
 <span data-ttu-id="3219d-134">バインド ファイルを BizTalk アプリケーションに個別にインポートするか、またはアプリケーションの一部としてインポートすると、そのファイル内のバインドによって、アプリケーション内でそれらのバインドと同じ名前を持つバインドがすべて上書きされ、構成が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-134">When you import a binding file into a BizTalk application either individually or as part of an application, any bindings that currently exist in the application having the same name as bindings in the file are overwritten by the imported bindings, and the configuration is applied.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3219d-135">セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="3219d-135">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="3219d-136">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3219d-136">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="3219d-137">BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。</span><span class="sxs-lookup"><span data-stu-id="3219d-137">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="3219d-138">手順については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。</span><span class="sxs-lookup"><span data-stu-id="3219d-138">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="3219d-139">関連項目[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="3219d-139">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3219d-140">参照</span><span class="sxs-lookup"><span data-stu-id="3219d-140">See Also</span></span>  
 <span data-ttu-id="3219d-141">[アプリケーションの展開時の成果物を処理します。](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="3219d-141">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="3219d-142">[BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="3219d-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="3219d-143">依存関係とアプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="3219d-143">Dependencies and Application Deployment</span></span>](../core/dependencies-and-application-deployment.md)