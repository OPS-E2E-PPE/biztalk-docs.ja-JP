---
title: "IntelliSense を使用して、インターセプター構成ファイルを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7be3f79545db81a0127fc8d004d71c758069a55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a><span data-ttu-id="4d241-102">IntelliSense を使用したインターセプター構成ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4d241-102">Using IntelliSense to Create an Interceptor Configuration File</span></span>
<span data-ttu-id="4d241-103">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の Intellisense およびスキーマ検証を使用して、図式的に有効なインターセプター構成ファイルを構築できます。</span><span class="sxs-lookup"><span data-stu-id="4d241-103">You can use IntelliSense and schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to help you construct interceptor configuration files that are schematically valid.</span></span> <span data-ttu-id="4d241-104">BAM 管理ユーティリティは、基本的なインターセプター構成スキーマに対してインターセプター構成ファイルを検証し、ファイルが無効な場合はスキーマを展開しません。</span><span class="sxs-lookup"><span data-stu-id="4d241-104">The BAM management utility validates your interceptor configuration file against the base interceptor configuration schema and, if the file is not valid, does not deploy the schema.</span></span> <span data-ttu-id="4d241-105">ファイルが基本的なインターセプター構成スキーマに対する検証に合格すると、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] スキーマや [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] スキーマなど、テクノロジ固有のスキーマに対して実行時に検証が行われ、エラーが発生した場合は傍受を行いません。</span><span class="sxs-lookup"><span data-stu-id="4d241-105">If the file passes validation against the base interceptor configuration schema, it is validated against technology-specific schemas like the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema or the [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema during run time and if errors are encountered, no interception will occur.</span></span> <span data-ttu-id="4d241-106">インターセプター構成ファイルを構築するときに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のスキーマ検証を使用することで、これらのエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="4d241-106">You can avoid these errors by using schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when constructing your interceptor configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d241-107">BAM インターセプタ構成 XSD ファイルのサンプルは、SDK ファイルと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4d241-107">The sample BAM interceptor configuration XSD files are installed with the SDK files.</span></span> <span data-ttu-id="4d241-108">このファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs にあります。</span><span class="sxs-lookup"><span data-stu-id="4d241-108">They can be found at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:</span></span>  
>   
>  -   <span data-ttu-id="4d241-109">CommonInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="4d241-109">CommonInterceptorConfiguration.xsd</span></span>  
> -   <span data-ttu-id="4d241-110">WcfInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="4d241-110">WcfInterceptorConfiguration.xsd</span></span>  
> -   <span data-ttu-id="4d241-111">WorkflowInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="4d241-111">WorkflowInterceptorConfiguration.xsd</span></span>  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a><span data-ttu-id="4d241-112">インターセプタ スキーマのコピーを取得するには</span><span class="sxs-lookup"><span data-stu-id="4d241-112">To obtain a copy of the interceptor schemas</span></span>  
  
1.  <span data-ttu-id="4d241-113">メモ帳または任意のテキスト エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="4d241-113">Open Notepad or another text editor.</span></span>  
  
2.  <span data-ttu-id="4d241-114">移動し、[インターセプタ構成スキーマ](../core/interceptor-configuration-schema.md)トピックです。</span><span class="sxs-lookup"><span data-stu-id="4d241-114">Navigate to the [Interceptor Configuration Schema](../core/interceptor-configuration-schema.md) topic.</span></span>  
  
3.  <span data-ttu-id="4d241-115">開いているテキスト エディターで、新しいドキュメントにコンテンツを貼り付けるし、名前を使用してテキスト ファイルとしてファイルを保存**CommonInterceptorConfiguration.xsd** (または独自の 1 つ)、ハード ディスクにします。</span><span class="sxs-lookup"><span data-stu-id="4d241-115">Paste the contents into a new document in the open text editor, and then save the file as a text file using the name **CommonInterceptorConfiguration.xsd** (or one of your own choosing) to your hard disk.</span></span>  
  
4.  <span data-ttu-id="4d241-116">これらの手順を繰り返します、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]スキーマと[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]ファイル名を使用してスキーマ トピック**WorkflowInterceptorConfiguration.xsd**と**である WcfInterceptorConfiguration.xsd**または名独自の次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="4d241-116">Repeat these steps for the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema and [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema topics using the file names **WorkflowInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** or names of your own choosing.</span></span>  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a><span data-ttu-id="4d241-117">インターセプター構成ファイルで Intellisense を使用するには</span><span class="sxs-lookup"><span data-stu-id="4d241-117">To use IntelliSense with your interceptor configuration file</span></span>  
  
1.  <span data-ttu-id="4d241-118">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。</span><span class="sxs-lookup"><span data-stu-id="4d241-118">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="4d241-119">をクリックして**ファイル**、 をクリックして**新規**、クリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="4d241-119">Click **File**, click **New**, and then click **File**.</span></span>  
  
3.  <span data-ttu-id="4d241-120">**新しいファイル**ダイアログ ボックスで、 **XML ファイル** をクリックし、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="4d241-120">In the **New File** dialog box, select **XML File** and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="4d241-121">編集ウィンドウを右クリックし、をクリックしてプロパティ ウィンドウを表示する**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="4d241-121">View the Properties pane by right-clicking the edit pane, and then clicking **Properties**.</span></span>  
  
5.  <span data-ttu-id="4d241-122">プロパティ ウィンドウで、をクリックして**スキーマ**、クリックして、省略記号 (**.**).</span><span class="sxs-lookup"><span data-stu-id="4d241-122">In the Properties pane, click **Schemas**, and then click the ellipsis (**…**).</span></span>  
  
6.  <span data-ttu-id="4d241-123">**XML スキーマ**ダイアログ ボックスで、をクリックして**追加**クリックし、スキーマの場所に移動し、 **CommonInterceptorConfiguration.xsd**と**ある WcfInterceptorConfiguration.xsd**で作業している場合、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]インターセプター構成ファイル、または**WorkflowInterceptorConfiguration.xsd**で作業している場合、 [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]インターセプター構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="4d241-123">In the **XML Schemas** dialog box, click **Add** and then navigate to the location of the schemas and select **CommonInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor configuration file, or **WorkflowInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor configuration file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d241-124">別の名前でファイルを保存した場合は、その名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d241-124">If you saved the files using different names, select those files instead.</span></span>  
  
7.  <span data-ttu-id="4d241-125">インターセプター構成ファイルを開くと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] によりファイルが検証され、ファイルを作成および変更するときに Intellisense のヘルプが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4d241-125">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] will now validate your interceptor configuration file when it is opened and supply IntelliSense help as you create and modify the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d241-126">参照</span><span class="sxs-lookup"><span data-stu-id="4d241-126">See Also</span></span>  
 <span data-ttu-id="4d241-127">[Windows Workflow Foundation スキーマ](../core/windows-workflow-foundation-schema.md) </span><span class="sxs-lookup"><span data-stu-id="4d241-127">[Windows Workflow Foundation Schema](../core/windows-workflow-foundation-schema.md) </span></span>  
 [<span data-ttu-id="4d241-128">Windows Communication Foundation スキーマ</span><span class="sxs-lookup"><span data-stu-id="4d241-128">Windows Communication Foundation Schema</span></span>](../core/windows-communication-foundation-schema.md)