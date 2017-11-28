---
title: "Files1 のバインドのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- CLASSPATH environment variable
- importing binding files
- cleaning target computer
ms.assetid: b2a9b19b-2d3d-45ea-bd92-a2501791b86a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fca64580b692f01834b48085aa2d88085fb743
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="62c9d-102">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="62c9d-102">Importing Binding Files</span></span>
<span data-ttu-id="62c9d-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。</span><span class="sxs-lookup"><span data-stu-id="62c9d-103">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="62c9d-104">CLASSPATH が PeopleSoft 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="62c9d-104">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="62c9d-105">新しいコンピュータで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="62c9d-105">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="62c9d-106">新しいコンピュータで、応答用のフォルダが存在し、同じである。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="62c9d-106">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="62c9d-107">PeopleSoft Enterprise システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="62c9d-107">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="62c9d-108">詳細については、次を参照してください。[展開の制限事項](../core/deployment-limitations3.md)です。</span><span class="sxs-lookup"><span data-stu-id="62c9d-108">For more information, see [Deployment Limitations](../core/deployment-limitations3.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62c9d-109">展開すると、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="62c9d-109">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="62c9d-110">バインド ファイルとアセンブリを展開先のコンピュータに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="62c9d-110">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="62c9d-111">バインド ファイルをインポートする手順については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ドキュメントの「BizTalk グループにバインドをインポートする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62c9d-111">For step-by-step directions about importing binding files, see the topic "How to Import Bindings into a BizTalk Group" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="62c9d-112">展開先のコンピューターのクリーニング</span><span class="sxs-lookup"><span data-stu-id="62c9d-112">Cleaning the Target Computer</span></span>  
 <span data-ttu-id="62c9d-113">展開先のコンピュータをクリーニングして新しいアプリケーションを展開するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="62c9d-113">Follow these steps to clean the target computer for deploying the new application.</span></span>  
  
#### <a name="to-clean-the-target-computer"></a><span data-ttu-id="62c9d-114">展開先のコンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="62c9d-114">To clean the target computer</span></span>  
  
-   <span data-ttu-id="62c9d-115">送信ポートを削除して、受信場所、オーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="62c9d-115">Remove send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="62c9d-116">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="62c9d-116">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="62c9d-117">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信**</span><span class="sxs-lookup"><span data-stu-id="62c9d-117">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
     <span data-ttu-id="62c9d-118">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信**</span><span class="sxs-lookup"><span data-stu-id="62c9d-118">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
     <span data-ttu-id="62c9d-119">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="62c9d-119">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="62c9d-120">**cscript RemoveSendPort.vbs\<送信ポートの名前 >**</span><span class="sxs-lookup"><span data-stu-id="62c9d-120">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c9d-121">参照</span><span class="sxs-lookup"><span data-stu-id="62c9d-121">See Also</span></span>  
 [<span data-ttu-id="62c9d-122">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="62c9d-122">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies5.md)