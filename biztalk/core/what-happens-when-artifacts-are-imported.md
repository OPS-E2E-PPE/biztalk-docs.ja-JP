---
title: アイテムのインポート時の動作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing, artifacts
- artifacts, importing
ms.assetid: a83957df-6e16-419a-b693-87985b498cc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52098eaa69fd2cefc25e6c7ba27908ec6a5a9bd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395173"
---
# <a name="what-happens-when-artifacts-are-imported"></a><span data-ttu-id="3cf57-102">アイテムのインポート時の動作</span><span class="sxs-lookup"><span data-stu-id="3cf57-102">What Happens When Artifacts Are Imported</span></span>
<span data-ttu-id="3cf57-103">このトピックでは、インポートされたアイテムの処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-103">This topic describes what happens to artifacts when they are imported.</span></span> <span data-ttu-id="3cf57-104">このトピックで説明されている成果物をインポートする次の 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="3cf57-104">There are three ways to import artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="3cf57-105">BizTalk グループまたはアプリケーションに BizTalk の .msi ファイル内のアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf57-105">Importing artifacts in a BizTalk .msi file into a BizTalk group or application</span></span>  
  
-   <span data-ttu-id="3cf57-106">.Xml ポリシー ファイルを BizTalk グループにインポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf57-106">Importing an .xml policy file into a BizTalk group</span></span>  
  
-   <span data-ttu-id="3cf57-107">BizTalk グループまたはアプリケーションにバインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="3cf57-107">Importing a binding file into a BizTalk group or application</span></span>  
  
## <a name="importing-a-biztalk-msi-file"></a><span data-ttu-id="3cf57-108">BizTalk .msi ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3cf57-108">Importing a BizTalk .msi file</span></span>  
 <span data-ttu-id="3cf57-109">BizTalk グループまたはアプリケーションに BizTalk の .msi ファイルをインポートすると、BizTalk Server は、次のように含まれるアイテムを処理します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-109">When you import a BizTalk .msi file into a BizTalk group or application, BizTalk Server handles the artifacts that it contains as follows:</span></span>  
  
-   <span data-ttu-id="3cf57-110">インポート中には、グループ内の他のアプリケーションには、このアプリケーションからの参照が追加された場合、参照は、BizTalk 管理データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-110">If during import you added any references from this application to other applications in the group, the reference is added to the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="3cf57-111">このオプションを指定した場合、アプリケーションの既存のアイテムが同じ完全名とバージョン番号 (該当する場合) が .msi ファイル内のアイテムで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-111">If you specified this option, existing artifacts in the application are overwritten by artifacts in the .msi file that have the same full name and version number (if applicable).</span></span>  
  
-   <span data-ttu-id="3cf57-112">アプリケーションに追加されたバインド ファイルのインポート中に、ターゲット環境を選択した場合は、バインドが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-112">If binding files have been added to the application, and you select their target environment during import, the bindings are applied.</span></span>  
  
-   <span data-ttu-id="3cf57-113">インポート時に実行するように構成する前または処理後のスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-113">Pre- or post-processing scripts that are configured to run on import will run.</span></span>  
  
-   <span data-ttu-id="3cf57-114">成果物のファイル ベースのデータがシリアル化され、BizTalk 管理データベースに格納されています。</span><span class="sxs-lookup"><span data-stu-id="3cf57-114">File-based artifact data is serialized and stored in the BizTalk Management database.</span></span> <span data-ttu-id="3cf57-115">これには、アセンブリ、仮想ディレクトリ、ファイル、スクリプト、証明書、および BAM アイテムのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-115">This includes data for assemblies, virtual directories, files, scripts, certificates, and BAM artifacts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3cf57-116">セキュリティ上の理由から、秘密キーは、エクスポートされるときに各証明書から削除されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-116">For security reasons, the private key is removed from each certificate when it is exported.</span></span> <span data-ttu-id="3cf57-117">そのため、BizTalk 管理データベースに秘密キーは格納されません。</span><span class="sxs-lookup"><span data-stu-id="3cf57-117">Therefore, no private keys are stored in the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="3cf57-118">ポリシー データは、ルール エンジン データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-118">Policy data is stored in the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="3cf57-119">BAM アイテムは、BAM プライマリ インポート データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-119">BAM artifacts are stored in the BAM Primary Import database.</span></span> <span data-ttu-id="3cf57-120">BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-120">BAM definitions are deployed.</span></span>  
  
-   <span data-ttu-id="3cf57-121">BizTalk アセンブリと"インポート時に GAC に追加 の展開オプションを構成する .NET アセンブリは、グローバル アセンブリ キャッシュ (GAC) に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-121">BizTalk assemblies and .NET assemblies that have the "Add to GAC on import" deployment option configured are added to the global assembly cache (GAC).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cf57-122">BizTalk Server がアプリケーションに関連付けられているすべての構成情報とデータのデータベースから取得できます後でアプリケーションを .msi ファイルをエクスポートするときに、BizTalk Server データベースのアイテムのデータが格納されているため、成果物、.msi ファイルに含めます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-122">Because the artifact data is stored in the BizTalk Server databases, when you later export the application into an .msi file, BizTalk Server can retrieve from the databases all of the configuration information and data associated with the application and its artifacts and include it in the .msi file.</span></span> <span data-ttu-id="3cf57-123">.Msi ファイルを別の BizTalk グループにインポートしたすべての成果物の構成情報とデータが新しいグループに再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-123">When you import the .msi file into another BizTalk group, all of the artifact configuration information and data is recreated in the new group.</span></span>  
  
 <span data-ttu-id="3cf57-124">アプリケーションをインポートした後は、表示して管理、および 1 つのエンティティとしてグループ化または個別に管理コンソールまたは BTSTask を使用して、アプリケーションで成果物を配置できます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-124">After you import an application, you can view, manage, and deploy the artifacts in the application either together as a single entity or individually by using the Administration console or BTSTask.</span></span> <span data-ttu-id="3cf57-125">詳細については、次を参照してください。[アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-125">For more information, see [Application Deployment and Management Tools](../core/application-deployment-and-management-tools.md).</span></span>  
  
## <a name="importing-a-policy"></a><span data-ttu-id="3cf57-126">ポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="3cf57-126">Importing a policy</span></span>  
 <span data-ttu-id="3cf57-127">.Xml ファイルからポリシーをインポートすると、ポリシーがルール エンジン データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-127">When you import a policy from an .xml file, the policy is added to the Rule Engine database.</span></span> <span data-ttu-id="3cf57-128">BizTalk .msi ファイル内のポリシーをインポートするとは異なり、ポリシーは、BizTalk 管理データベース内の任意のアプリケーションに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="3cf57-128">Unlike when you import a policy within a BizTalk .msi file, the policy is not associated with any application in the BizTalk Management database.</span></span> <span data-ttu-id="3cf57-129">[ポリシー] ノードで、ポリシーが表示されます、\<すべての成果物\>BizTalk Server 管理コンソール内のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="3cf57-129">The policy displays in the Policies node of the \<All Artifacts\> folder in the BizTalk Server Administration console.</span></span> <span data-ttu-id="3cf57-130">ポリシーをインポートした後で、グループを使用するアプリケーションの使用可能にすることを発行できます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-130">After importing the policy you can publish it to make it available for applications in the group to use.</span></span> <span data-ttu-id="3cf57-131">詳細については、次を参照してください。[ポリシーの管理](../core/managing-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-131">For more information, see [Managing Policies](../core/managing-policies.md).</span></span>  
  
## <a name="importing-a-binding-file"></a><span data-ttu-id="3cf57-132">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="3cf57-132">Importing a binding file</span></span>  
 <span data-ttu-id="3cf57-133">バインド ファイルを BizTalk グループにインポートして、インポートされたファイルのバインドと同じ名前を持つグループに現在存在するすべてのバインドは、インポートされたファイルのバインドで上書きされます構成が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-133">When you import a binding file into a BizTalk group, any bindings that currently exist in the group having the same name as bindings in the imported file are overwritten by the bindings in the imported file, and the configuration is applied.</span></span>  
  
 <span data-ttu-id="3cf57-134">ファイルをインポートするバインドを BizTalk アプリケーションにも個別にまたはアプリケーションの一部として、すべてのバインドされているアプリケーション内に存在ファイルのバインドはインポートされたバインディングによって上書きされますと、同じ名前を持つときに、構成が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-134">When you import a binding file into a BizTalk application either individually or as part of an application, any bindings that currently exist in the application having the same name as bindings in the file are overwritten by the imported bindings, and the configuration is applied.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3cf57-135">セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="3cf57-135">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="3cf57-136">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf57-136">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="3cf57-137">BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-137">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="3cf57-138">手順については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-138">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="3cf57-139">参照してください[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="3cf57-139">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf57-140">参照</span><span class="sxs-lookup"><span data-stu-id="3cf57-140">See Also</span></span>  
 <span data-ttu-id="3cf57-141">[アプリケーション展開中にアイテムを処理します。](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="3cf57-141">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="3cf57-142">[BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="3cf57-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="3cf57-143">依存関係とアプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="3cf57-143">Dependencies and Application Deployment</span></span>](../core/dependencies-and-application-deployment.md)