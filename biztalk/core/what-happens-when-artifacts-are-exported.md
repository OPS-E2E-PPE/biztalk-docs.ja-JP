---
title: アイテムのエクスポート時の動作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting, artifacts
- artifacts, exporting
ms.assetid: accc9a81-01fb-4da7-a5a5-167835d393a2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ab32fb2931f8a0294356e94d9f80f29b5b7c84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258510"
---
# <a name="what-happens-when-artifacts-are-exported"></a><span data-ttu-id="dacaf-102">アイテムのエクスポート時の動作</span><span class="sxs-lookup"><span data-stu-id="dacaf-102">What Happens When Artifacts Are Exported</span></span>
<span data-ttu-id="dacaf-103">このトピックでは、成果物をエクスポートするときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="dacaf-103">This topic describes what happens when you export artifacts.</span></span> <span data-ttu-id="dacaf-104">このトピックで説明されている成果物をエクスポートする 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="dacaf-104">There are three ways to export artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="dacaf-105">BizTalk アプリケーションとそのアイテムを BizTalk .msi (Windows インストーラー) ファイルにエクスポート</span><span class="sxs-lookup"><span data-stu-id="dacaf-105">Exporting a BizTalk application and its artifacts into a BizTalk .msi (Windows Installer) file</span></span>  
  
-   <span data-ttu-id="dacaf-106">ポリシーを .xml ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dacaf-106">Exporting a policy into an .xml file</span></span>  
  
-   <span data-ttu-id="dacaf-107">バインドを .xml ファイルにエクスポート</span><span class="sxs-lookup"><span data-stu-id="dacaf-107">Exporting bindings into an .xml file</span></span>  
  
## <a name="exporting-a-biztalk-application"></a><span data-ttu-id="dacaf-108">BizTalk アプリケーションをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dacaf-108">Exporting a BizTalk application</span></span>  
 <span data-ttu-id="dacaf-109">BizTalk アプリケーションとが含まれているアイテムをエクスポートするときに、アプリケーションの構成情報とアイテム データは、BizTalk の .msi ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-109">When you export a BizTalk application and the artifacts it contains, application configuration information and artifact data is exported into a BizTalk .msi file.</span></span> <span data-ttu-id="dacaf-110">ほとんどのアイテム データは、次の例外で、BizTalk 管理データベースからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-110">Most artifact data is exported from the BizTalk Management database, with the following exceptions:</span></span>  
  
- <span data-ttu-id="dacaf-111">ポリシー データは、グループのルール エンジン データベースからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-111">Policy data is exported from the Rule Engine database for the group.</span></span>  
  
- <span data-ttu-id="dacaf-112">仮想ディレクトリのデータは、管理データベースが存在しない場合、インターネット インフォメーション サービス (IIS) メタベースからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-112">Virtual directory data is exported from the Internet Information Services (IIS) metabase if it does not exist in the Management database.</span></span> <span data-ttu-id="dacaf-113">仮想ディレクトリが明示的に追加されていないアプリケーションと、ケースになります (」の説明に従って[仮想ディレクトリをアプリケーションに追加する方法](../core/how-to-add-a-virtual-directory-to-an-application.md)) またはアプリケーションが .msi ファイルからこのグループにインポートされていません。別の BizTalk グループからエクスポートされました。</span><span class="sxs-lookup"><span data-stu-id="dacaf-113">This will be the case when the virtual directory has not been explicitly added to the application (as described in [How to Add a Virtual Directory to an Application](../core/how-to-add-a-virtual-directory-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span>  
  
- <span data-ttu-id="dacaf-114">管理データベースが存在しない場合、ローカル コンピューターでは、その他のユーザーの証明書ストアから証明書データがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-114">Certificate data is exported from the Other People certificate store on the local computer, if it does not exist in the Management database.</span></span> <span data-ttu-id="dacaf-115">証明書が明示的に追加されていないアプリケーションと、ケースになります (」の説明に従って[アプリケーションに証明書を追加する方法](../core/how-to-add-a-certificate-to-an-application.md)) またはアプリケーションがされた .msi ファイルからこのグループにインポートされていません。別の BizTalk グループからエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-115">This will be the case when the certificate has not been explicitly added to the application (as described in [How to Add a Certificate to an Application](../core/how-to-add-a-certificate-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span> <span data-ttu-id="dacaf-116">関連付けられている証明書を持つ受信ポートでアプリケーションをエクスポートするときに、証明書がエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-116">Certificates are exported when you export an application with a receive port that has a certificate associated with it.</span></span> <span data-ttu-id="dacaf-117">エクスポート時に証明書から秘密キーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-117">Private keys are removed from certificates on export.</span></span>  
  
  <span data-ttu-id="dacaf-118">この .msi ファイルを使用して、別の BizTalk グループ内のアプリケーションも含めてすべてのデータ、アプリケーションのアイテムをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-118">You can use this .msi file to import the application's artifacts, including all of their data, into an application in another BizTalk group.</span></span> <span data-ttu-id="dacaf-119">コンピューターでアプリケーションをインストールするのにこの .msi ファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-119">You can also use this .msi file to install the application on a computer.</span></span>  
  
## <a name="exporting-a-policy"></a><span data-ttu-id="dacaf-120">ポリシーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dacaf-120">Exporting a policy</span></span>  
 <span data-ttu-id="dacaf-121">BizTalk グループまたはアプリケーションのポリシーをエクスポートする管理コンソールを使用する場合は、ポリシー情報を含む .xml ポリシー ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-121">When you use the administration console to export a policy for either a BizTalk group or application, it generates an .xml policy file containing the policy information.</span></span> <span data-ttu-id="dacaf-122">グループ内のアプリケーションで使用できるように、ポリシーを作成する別の BizTalk グループにこのポリシー ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-122">You can import this policy file into another BizTalk group to create the policy there, so that applications in the group can use it.</span></span> <span data-ttu-id="dacaf-123">BTSTask を使用して、アプリケーションのポリシー情報をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-123">You can also export policy information for an application by using BTSTask.</span></span> <span data-ttu-id="dacaf-124">ただし、BTSTask には、ポリシーの .xml ファイルをエクスポートするコマンドはありません。</span><span class="sxs-lookup"><span data-stu-id="dacaf-124">BTSTask, however, does not have a command to export a policy .xml file.</span></span> <span data-ttu-id="dacaf-125">代わりに、ポリシーのみを含んでいるアプリケーションの .msi ファイルをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-125">Instead, you can export an application .msi file that contains only the policy.</span></span> <span data-ttu-id="dacaf-126">別のグループ内のアプリケーションを .msi ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-126">You can then import the .msi file into an application in another group.</span></span>  
  
## <a name="exporting-bindings"></a><span data-ttu-id="dacaf-127">バインドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="dacaf-127">Exporting bindings</span></span>  
 <span data-ttu-id="dacaf-128">管理コンソールまたは BTSTask を使用して、BizTalk グループ、アプリケーション、またはアセンブリのバインドをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-128">You can use either the administration console or BTSTask to export bindings for a BizTalk group, application, or assembly.</span></span> <span data-ttu-id="dacaf-129">これを行うと、BizTalk Server は、グループ、アプリケーション、またはアセンブリのバインド情報を含む .xml ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="dacaf-129">When you do this, BizTalk Server generates an .xml file containing the binding information for the group, application, or assembly.</span></span> <span data-ttu-id="dacaf-130">バインドをエクスポートするときに、グループのグローバル パーティ情報をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dacaf-130">When you export bindings, you can also export global party information for the group.</span></span> <span data-ttu-id="dacaf-131">アプリケーションにこのバインド ファイルを追加するか、BizTalk グループまたはアプリケーションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="dacaf-131">You can then either add this binding file to an application or import it into a BizTalk group or application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dacaf-132">参照</span><span class="sxs-lookup"><span data-stu-id="dacaf-132">See Also</span></span>  
 <span data-ttu-id="dacaf-133">[アプリケーション展開中にアイテムを処理します。](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="dacaf-133">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="dacaf-134">[BizTalk アプリケーション、バインド、およびポリシーのエクスポート](../core/exporting-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="dacaf-134">[Exporting BizTalk Applications, Bindings, and Policies](../core/exporting-biztalk-applications-bindings-and-policies.md) </span></span>  
 <span data-ttu-id="dacaf-135">[BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="dacaf-135">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="dacaf-136">アプリケーションにバインド ファイルを追加する方法</span><span class="sxs-lookup"><span data-stu-id="dacaf-136">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)