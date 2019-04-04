---
title: エクスポート Bindings6 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- exporting, bindings
ms.assetid: 052a429e-3237-44d4-8933-00aa5edfb212
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee3d7df759dab97dca6a2e7677abb0bad15f8cd7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022880"
---
# <a name="exporting-bindings"></a><span data-ttu-id="99272-102">バインドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="99272-102">Exporting Bindings</span></span>
<span data-ttu-id="99272-103">このセクションの各トピックでは、BizTalk Server グループ、アセンブリ、またはアプリケーションのバインドを .xml ファイルにエクスポートする方法について説明します </span><span class="sxs-lookup"><span data-stu-id="99272-103">The topics in this section describe how to export bindings for a BizTalk group, assembly, or application into an .xml file.</span></span> <span data-ttu-id="99272-104">(バインドは、ホスト、送信ポート、送信ポート グループ、受信ポート、受信場所、パーティを、オーケストレーション、パイプライン、マップ、およびスキーマと関連付ける方法を定義します)。その後、.xml ファイルから別のグループまたはアプリケーションにバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="99272-104">(Bindings define how hosts, send ports, send port groups, receive ports, receive locations, parties are associated with orchestrations, pipelines, maps, and schemas.) You can then import the bindings from the .xml file into another group or application.</span></span> <span data-ttu-id="99272-105">バインドをインポートすると、グループまたはアプリケーション内の同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="99272-105">Importing bindings overwrites any existing bindings of the same name in the group or application.</span></span> <span data-ttu-id="99272-106">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="99272-106">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="99272-107">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="99272-107">The bindings that you add do not take effect until you import the application.</span></span>  
  
 <span data-ttu-id="99272-108">以下のシナリオでバインド ファイルを使用すると、バインドを手動で構成する必要がないので、アプリケーションを迅速に展開できます。</span><span class="sxs-lookup"><span data-stu-id="99272-108">You may find that using binding files speeds application deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
- <span data-ttu-id="99272-109">ある展開環境から別の環境へアプリケーションを移動する場合</span><span class="sxs-lookup"><span data-stu-id="99272-109">Moving an application from one deployment environment to another.</span></span>  
  
- <span data-ttu-id="99272-110">アセンブリを更新する場合</span><span class="sxs-lookup"><span data-stu-id="99272-110">Updating an assembly.</span></span>  
  
- <span data-ttu-id="99272-111">複数の BizTalk グループへのバインドと共にアセンブリを展開する場合</span><span class="sxs-lookup"><span data-stu-id="99272-111">Deploying an assembly together with its bindings to multiple BizTalk groups.</span></span>  
  
  <span data-ttu-id="99272-112">これらの目的のバインド ファイルの使用に関する詳細については、[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99272-112">For more information about using binding files for these purposes, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
  <span data-ttu-id="99272-113">インポートおよびバインドの追加に関する詳細については、次を参照してください[を BizTalk グループにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-group.md)、 [BizTalk アプリケーションにバインドのインポート方法](../core/how-to-import-bindings-into-a-biztalk-application.md)、および[バインディングを追加する方法。ファイルをアプリケーションに](../core/how-to-add-a-binding-file-to-an-application2.md)します。</span><span class="sxs-lookup"><span data-stu-id="99272-113">For more information about importing and adding bindings, see [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md), [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md), and [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="99272-114">バインド ファイルには機密データが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="99272-114">The binding file may contain sensitive data.</span></span> <span data-ttu-id="99272-115">適切な措置をとり、ファイルが保護されるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="99272-115">Be sure to take steps to secure the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99272-116">セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="99272-116">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="99272-117">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99272-117">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="99272-118">BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。</span><span class="sxs-lookup"><span data-stu-id="99272-118">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="99272-119">手順については、[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99272-119">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="99272-120">参照してください[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="99272-120">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99272-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="99272-121">In This Section</span></span>  
  
-   [<span data-ttu-id="99272-122">BizTalk グループのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="99272-122">How to Export Bindings for a BizTalk Group</span></span>](../core/how-to-export-bindings-for-a-biztalk-group.md)  
  
-   [<span data-ttu-id="99272-123">BizTalk アプリケーションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="99272-123">How to Export Bindings for a BizTalk Application</span></span>](../core/how-to-export-bindings-for-a-biztalk-application.md)  
  
-   [<span data-ttu-id="99272-124">BizTalk アセンブリのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="99272-124">How to Export Bindings for a BizTalk Assembly</span></span>](../core/how-to-export-bindings-for-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="99272-125">EDI AS2 ソリューションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="99272-125">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)