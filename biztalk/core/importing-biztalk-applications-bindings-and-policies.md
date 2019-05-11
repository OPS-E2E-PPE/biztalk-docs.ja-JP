---
title: BizTalk アプリケーション、バインド、およびポリシーのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing, applications
- importing, policies
- applications, importing
- policies, importing
- importing, bindings
- bindings, importing
ms.assetid: 678bdb03-efaa-4053-9048-b71fc539d191
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7891d36e922f49efd8a5ce4f8986fcad8aa162aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382506"
---
# <a name="importing-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="7e1d8-102">BizTalk アプリケーション、バインド、およびポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="7e1d8-102">Importing BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="7e1d8-103">このセクションのトピックでは、BizTalk グループまたはアプリケーションに BizTalk アプリケーション、バインドおよびポリシーをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-103">The topics in this section describe how to import BizTalk applications, bindings and policies into a BizTalk group or application.</span></span> <span data-ttu-id="7e1d8-104">説明したよう[BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)アプリケーションをエクスポートし、アプリケーションのアイテムを別の BizTalk グループ内のアプリケーションにインポートするのに使用できる Windows インストーラー (.msi) ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-104">As mentioned in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md), exporting an application creates a Windows Installer (.msi) file that you can then use to import the application's artifacts into an application in a different BizTalk group.</span></span> <span data-ttu-id="7e1d8-105">グループにも、インポート用に指定したアプリケーションがまだ存在しない場合、アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-105">If the application that you specify for the import does not already exist in the group, the application is created.</span></span> <span data-ttu-id="7e1d8-106">さらに、アプリケーションのアイテムが登録されているし、データ グループの BizTalk データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-106">In addition, application's artifacts are registered and their data stored in the BizTalk databases of the group.</span></span> <span data-ttu-id="7e1d8-107">詳細については、次を参照してください。[何の動作とアイテムのインポート](../core/what-happens-when-artifacts-are-imported.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-107">For more information, see [What Happens When Artifacts Are Imported](../core/what-happens-when-artifacts-are-imported.md).</span></span>  
  
 <span data-ttu-id="7e1d8-108">インポートすることも、BizTalk グループまたはアプリケーションに BizTalk グループ、アプリケーション、またはアセンブリからエクスポートしたバインド」の説明に従って[バインドのエクスポート](../core/exporting-bindings6.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-108">You can also import into a BizTalk group or application the bindings that you exported from a BizTalk group, application, or assembly, as described in [Exporting Bindings](../core/exporting-bindings6.md).</span></span> <span data-ttu-id="7e1d8-109">バインドをインポートするときに、BizTalk グループ、アプリケーション、またはアセンブリ内の同じ名前のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-109">When you import bindings, they overwrite any bindings of the same name in the BizTalk group, application, or assembly.</span></span>  
  
 <span data-ttu-id="7e1d8-110">さらに、できるポリシーをインポートする BizTalk グループまたはアプリケーションからエクスポートした BizTalk グループに」の説明に従って[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-110">In addition, you can import a policy into a BizTalk group that you exported from a BizTalk group or application, as described in [How to Export a Policy](../core/how-to-export-a-policy.md).</span></span> <span data-ttu-id="7e1d8-111">新しいグループのアプリケーションには、ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e1d8-111">Applications in the new group can then use the policy.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e1d8-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7e1d8-112">In This Section</span></span>  
  
-   [<span data-ttu-id="7e1d8-113">BizTalk アプリケーションをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="7e1d8-113">How to Import a BizTalk Application</span></span>](../core/how-to-import-a-biztalk-application.md)  
  
-   [<span data-ttu-id="7e1d8-114">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="7e1d8-114">Importing Bindings</span></span>](../core/importing-bindings2.md)  
  
-   [<span data-ttu-id="7e1d8-115">ポリシーをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="7e1d8-115">How to Import a Policy</span></span>](../core/how-to-import-a-policy.md)