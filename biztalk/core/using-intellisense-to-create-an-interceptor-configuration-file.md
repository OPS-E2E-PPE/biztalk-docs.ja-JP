---
title: IntelliSense を使用して、インターセプター構成ファイルを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 502b9f1d213a9440bb19820f9998604267045a44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396863"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a><span data-ttu-id="e414a-102">IntelliSense を使用したインターセプター構成ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e414a-102">Using IntelliSense to Create an Interceptor Configuration File</span></span>
<span data-ttu-id="e414a-103">IntelliSense およびスキーマ検証を使用する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]概略的に有効なインターセプター構成ファイルを作成するお手伝いをします。</span><span class="sxs-lookup"><span data-stu-id="e414a-103">You can use IntelliSense and schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to help you construct interceptor configuration files that are schematically valid.</span></span> <span data-ttu-id="e414a-104">BAM 管理ユーティリティでは、基本的なインターセプター構成スキーマに対してインターセプター構成ファイルを検証し、ファイルが有効でない場合、スキーマをデプロイしません。</span><span class="sxs-lookup"><span data-stu-id="e414a-104">The BAM management utility validates your interceptor configuration file against the base interceptor configuration schema and, if the file is not valid, does not deploy the schema.</span></span> <span data-ttu-id="e414a-105">ファイルには、基本的なインターセプター構成スキーマに対して検証が成功した場合は、ようなテクノロジに固有のスキーマに対して検証、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]スキーマまたは[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]スキーマ中に実行時間とインターセプトはないエラーが発生した場合発生します。</span><span class="sxs-lookup"><span data-stu-id="e414a-105">If the file passes validation against the base interceptor configuration schema, it is validated against technology-specific schemas like the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema or the [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema during run time and if errors are encountered, no interception will occur.</span></span> <span data-ttu-id="e414a-106">スキーマの検証を使用してこれらのエラーを回避できます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]インターセプタ構成ファイルを作成するときにします。</span><span class="sxs-lookup"><span data-stu-id="e414a-106">You can avoid these errors by using schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when constructing your interceptor configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e414a-107">サンプルの BAM インターセプタ構成 XSD ファイルは、SDK ファイルと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e414a-107">The sample BAM interceptor configuration XSD files are installed with the SDK files.</span></span> <span data-ttu-id="e414a-108">見つかります[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\bam\interceptorxsds:</span><span class="sxs-lookup"><span data-stu-id="e414a-108">They can be found at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:</span></span>  
> 
> - <span data-ttu-id="e414a-109">CommonInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="e414a-109">CommonInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="e414a-110">WcfInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="e414a-110">WcfInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="e414a-111">WorkflowInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="e414a-111">WorkflowInterceptorConfiguration.xsd</span></span>  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a><span data-ttu-id="e414a-112">インターセプタ スキーマのコピーを入手するには</span><span class="sxs-lookup"><span data-stu-id="e414a-112">To obtain a copy of the interceptor schemas</span></span>  
  
1. <span data-ttu-id="e414a-113">メモ帳または別のテキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="e414a-113">Open Notepad or another text editor.</span></span>  
  
2. <span data-ttu-id="e414a-114">移動し、[インターセプタ構成スキーマ](../core/interceptor-configuration-schema.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="e414a-114">Navigate to the [Interceptor Configuration Schema](../core/interceptor-configuration-schema.md) topic.</span></span>  
  
3. <span data-ttu-id="e414a-115">開いているテキスト エディターで新しいドキュメントに内容を貼り付けるし、名前を使用してテキスト ファイルとして保存します**CommonInterceptorConfiguration.xsd** (または、独自に選択のいずれか) をハード_ディスクにします。</span><span class="sxs-lookup"><span data-stu-id="e414a-115">Paste the contents into a new document in the open text editor, and then save the file as a text file using the name **CommonInterceptorConfiguration.xsd** (or one of your own choosing) to your hard disk.</span></span>  
  
4. <span data-ttu-id="e414a-116">これらの手順を繰り返します、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]スキーマと[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]ファイル名を使用してスキーマ トピック**WorkflowInterceptorConfiguration.xsd**と**WcfInterceptorConfiguration.xsd**または名独自の次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="e414a-116">Repeat these steps for the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema and [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema topics using the file names **WorkflowInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** or names of your own choosing.</span></span>  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a><span data-ttu-id="e414a-117">インターセプタ構成ファイルで IntelliSense を使用するには</span><span class="sxs-lookup"><span data-stu-id="e414a-117">To use IntelliSense with your interceptor configuration file</span></span>  
  
1. <span data-ttu-id="e414a-118">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。</span><span class="sxs-lookup"><span data-stu-id="e414a-118">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="e414a-119">をクリックして**ファイル**、 をクリックして**新規**、 をクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="e414a-119">Click **File**, click **New**, and then click **File**.</span></span>  
  
3. <span data-ttu-id="e414a-120">**新しいファイル**ダイアログ ボックスで、 **XML ファイル** をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="e414a-120">In the **New File** dialog box, select **XML File** and then click **Open**.</span></span>  
  
4. <span data-ttu-id="e414a-121">プロパティ ペインを表示、編集ウィンドウを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e414a-121">View the Properties pane by right-clicking the edit pane, and then clicking **Properties**.</span></span>  
  
5. <span data-ttu-id="e414a-122">プロパティ ペインで次のようにクリックします**スキーマ**、クリックして、省略記号 (**...**).</span><span class="sxs-lookup"><span data-stu-id="e414a-122">In the Properties pane, click **Schemas**, and then click the ellipsis (**…**).</span></span>  
  
6. <span data-ttu-id="e414a-123">**XML スキーマ**ダイアログ ボックスで、をクリックして**追加**クリックし、スキーマの場所に移動します**CommonInterceptorConfiguration.xsd**と**WcfInterceptorConfiguration.xsd**で作業している場合、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]インターセプター構成ファイル、または**WorkflowInterceptorConfiguration.xsd**で作業している場合、 [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]インターセプター構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="e414a-123">In the **XML Schemas** dialog box, click **Add** and then navigate to the location of the schemas and select **CommonInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor configuration file, or **WorkflowInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor configuration file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e414a-124">別の名前を使用して、ファイルを保存した場合は、それらのファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e414a-124">If you saved the files using different names, select those files instead.</span></span>  
  
7. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="e414a-125">これで開かれたときに、インターセプタ構成ファイルを検証を作成し、ファイルを変更する際に IntelliSense のヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="e414a-125">will now validate your interceptor configuration file when it is opened and supply IntelliSense help as you create and modify the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e414a-126">参照</span><span class="sxs-lookup"><span data-stu-id="e414a-126">See Also</span></span>  
 <span data-ttu-id="e414a-127">[Windows Workflow Foundation スキーマ](../core/windows-workflow-foundation-schema.md) </span><span class="sxs-lookup"><span data-stu-id="e414a-127">[Windows Workflow Foundation Schema](../core/windows-workflow-foundation-schema.md) </span></span>  
 [<span data-ttu-id="e414a-128">Windows Communication Foundation スキーマ</span><span class="sxs-lookup"><span data-stu-id="e414a-128">Windows Communication Foundation Schema</span></span>](../core/windows-communication-foundation-schema.md)