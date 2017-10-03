---
title: "アイテムのエクスポート時の動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exporting, artifacts
- artifacts, exporting
ms.assetid: accc9a81-01fb-4da7-a5a5-167835d393a2
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92a65889ea642706ae5c51849748fd8ad085a02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-when-artifacts-are-exported"></a><span data-ttu-id="b88f5-102">アイテムのエクスポート時の動作</span><span class="sxs-lookup"><span data-stu-id="b88f5-102">What Happens When Artifacts Are Exported</span></span>
<span data-ttu-id="b88f5-103">このトピックでは、アイテムがエクスポートされるときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="b88f5-103">This topic describes what happens when you export artifacts.</span></span> <span data-ttu-id="b88f5-104">アイテムのエクスポートには次の 3 つの方法があり、ここではそれぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b88f5-104">There are three ways to export artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="b88f5-105">BizTalk アプリケーションとそのアイテムを BizTalk .msi (Windows インストーラー) ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b88f5-105">Exporting a BizTalk application and its artifacts into a BizTalk .msi (Windows Installer) file</span></span>  
  
-   <span data-ttu-id="b88f5-106">ポリシーを .xml ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b88f5-106">Exporting a policy into an .xml file</span></span>  
  
-   <span data-ttu-id="b88f5-107">バインドを .xml ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b88f5-107">Exporting bindings into an .xml file</span></span>  
  
## <a name="exporting-a-biztalk-application"></a><span data-ttu-id="b88f5-108">BizTalk アプリケーションをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b88f5-108">Exporting a BizTalk application</span></span>  
 <span data-ttu-id="b88f5-109">BizTalk アプリケーションとそれに含まれるアイテムをエクスポートすると、アプリケーションの構成情報とアイテム データが BizTalk の .msi ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-109">When you export a BizTalk application and the artifacts it contains, application configuration information and artifact data is exported into a BizTalk .msi file.</span></span> <span data-ttu-id="b88f5-110">ほとんどのアイテム データは BizTalk 管理データベースからエクスポートされますが、次の例外があります。</span><span class="sxs-lookup"><span data-stu-id="b88f5-110">Most artifact data is exported from the BizTalk Management database, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="b88f5-111">ポリシー データは、グループのルール エンジン データベースからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-111">Policy data is exported from the Rule Engine database for the group.</span></span>  
  
-   <span data-ttu-id="b88f5-112">仮想ディレクトリのデータは、管理データベースにない場合は、インターネット インフォメーション サービス (IIS) メタベースからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-112">Virtual directory data is exported from the Internet Information Services (IIS) metabase if it does not exist in the Management database.</span></span> <span data-ttu-id="b88f5-113">ある場合、このとき、仮想ディレクトリが明示的に追加されていないアプリケーション (」の説明に従って[仮想ディレクトリをアプリケーションに追加する方法](../core/how-to-add-a-virtual-directory-to-an-application.md)) またはアプリケーションが .msi ファイルからこのグループにインポートされていません。別の BizTalk グループからエクスポートされました。</span><span class="sxs-lookup"><span data-stu-id="b88f5-113">This will be the case when the virtual directory has not been explicitly added to the application (as described in [How to Add a Virtual Directory to an Application](../core/how-to-add-a-virtual-directory-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span>  
  
-   <span data-ttu-id="b88f5-114">証明書データは、管理データベースにない場合は、ローカル コンピューター上の "その他のユーザー" 証明書ストアからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-114">Certificate data is exported from the Other People certificate store on the local computer, if it does not exist in the Management database.</span></span> <span data-ttu-id="b88f5-115">ある場合、この証明書が明示的に追加されていないアプリケーションとき (」の説明に従って[アプリケーションに証明書を追加する方法](../core/how-to-add-a-certificate-to-an-application.md)) された .msi ファイルからこのグループにアプリケーションがインポートされていないか別の BizTalk グループからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-115">This will be the case when the certificate has not been explicitly added to the application (as described in [How to Add a Certificate to an Application](../core/how-to-add-a-certificate-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span> <span data-ttu-id="b88f5-116">アプリケーションを証明書が関連付けられている受信ポートと共にエクスポートすると、証明書がエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-116">Certificates are exported when you export an application with a receive port that has a certificate associated with it.</span></span> <span data-ttu-id="b88f5-117">エクスポートでは、秘密キーは証明書から削除されます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-117">Private keys are removed from certificates on export.</span></span>  
  
 <span data-ttu-id="b88f5-118">この .msi ファイルを使用して、アプリケーションのアイテムとそのすべてのデータを、別の BizTalk グループのアプリケーションにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-118">You can use this .msi file to import the application's artifacts, including all of their data, into an application in another BizTalk group.</span></span> <span data-ttu-id="b88f5-119">この .msi ファイルを使用すると、コンピューターにアプリケーションをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-119">You can also use this .msi file to install the application on a computer.</span></span>  
  
## <a name="exporting-a-policy"></a><span data-ttu-id="b88f5-120">ポリシーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b88f5-120">Exporting a policy</span></span>  
 <span data-ttu-id="b88f5-121">管理コンソールを使用して、BizTalk グループまたはアプリケーションのポリシーをエクスポートすると、ポリシー情報を格納した .xml ポリシー ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-121">When you use the administration console to export a policy for either a BizTalk group or application, it generates an .xml policy file containing the policy information.</span></span> <span data-ttu-id="b88f5-122">このポリシー ファイルを別の BizTalk グループにインポートしてそこにポリシーを作成し、そのグループのアプリケーションがポリシーを使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-122">You can import this policy file into another BizTalk group to create the policy there, so that applications in the group can use it.</span></span> <span data-ttu-id="b88f5-123">また、アプリケーションのポリシー情報は、BTSTask を使用してエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-123">You can also export policy information for an application by using BTSTask.</span></span> <span data-ttu-id="b88f5-124">ただし、BTSTask にはポリシーの .xml ファイルをエクスポートするコマンドはありません。</span><span class="sxs-lookup"><span data-stu-id="b88f5-124">BTSTask, however, does not have a command to export a policy .xml file.</span></span> <span data-ttu-id="b88f5-125">代わりに、ポリシーのみを含むアプリケーションの .msi ファイルをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-125">Instead, you can export an application .msi file that contains only the policy.</span></span> <span data-ttu-id="b88f5-126">その後、別のグループのアプリケーションにその .msi ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-126">You can then import the .msi file into an application in another group.</span></span>  
  
## <a name="exporting-bindings"></a><span data-ttu-id="b88f5-127">バインドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="b88f5-127">Exporting bindings</span></span>  
 <span data-ttu-id="b88f5-128">管理コンソールまたは BTSTask を使用して、BizTalk グループ、アプリケーション、またはアセンブリのバインドをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-128">You can use either the administration console or BTSTask to export bindings for a BizTalk group, application, or assembly.</span></span> <span data-ttu-id="b88f5-129">エクスポートを行うと、BizTalk Server によって、グループ、アプリケーション、またはアセンブリのバインド情報を含む .xml ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-129">When you do this, BizTalk Server generates an .xml file containing the binding information for the group, application, or assembly.</span></span> <span data-ttu-id="b88f5-130">バインドをエクスポートするときは、グループのグローバル パーティ情報もエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-130">When you export bindings, you can also export global party information for the group.</span></span> <span data-ttu-id="b88f5-131">その後、このバインド ファイルをアプリケーションに追加したり、BizTalk グループまたはアプリケーションにインポートしたりできます。</span><span class="sxs-lookup"><span data-stu-id="b88f5-131">You can then either add this binding file to an application or import it into a BizTalk group or application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88f5-132">参照</span><span class="sxs-lookup"><span data-stu-id="b88f5-132">See Also</span></span>  
 <span data-ttu-id="b88f5-133">[アプリケーションの展開時の成果物を処理します。](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="b88f5-133">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="b88f5-134">[BizTalk アプリケーション、バインド、およびポリシーをエクスポートします。](../core/exporting-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="b88f5-134">[Exporting BizTalk Applications, Bindings, and Policies](../core/exporting-biztalk-applications-bindings-and-policies.md) </span></span>  
 <span data-ttu-id="b88f5-135">[BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="b88f5-135">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="b88f5-136">バインド ファイルをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="b88f5-136">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)