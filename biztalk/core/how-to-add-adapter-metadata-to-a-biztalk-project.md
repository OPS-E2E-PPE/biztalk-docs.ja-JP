---
title: "アダプター メタデータを BizTalk プロジェクトに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b343ff085cee7049ea916a38fe1216e097200fbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="79879-102">アダプター メタデータを BizTalk プロジェクトに追加する方法</span><span class="sxs-lookup"><span data-stu-id="79879-102">How to Add Adapter Metadata to a BizTalk Project</span></span>
<span data-ttu-id="79879-103">アダプター メタデータの追加ウィザードを使用すると、アダプター メタデータを BizTalk プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="79879-103">The Add Adapter Metadata Wizard enables you to add adapter metadata to a BizTalk project.</span></span> <span data-ttu-id="79879-104">このデータには、オーケストレーションからアダプターと通信するために必要なスキーマ、メッセージの種類、およびポートの種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="79879-104">This data includes schemas, message types, and port types needed to communicate with an adapter from an orchestration.</span></span> <span data-ttu-id="79879-105">FTP などのアプリケーション アダプターと共にアダプター メタデータの追加ウィザードを使用することで、これらのアプリケーション アダプターに対応するスキーマをシステムに取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="79879-105">Use the Add Adapter Metadata Wizard with application adapters, such as FTP, to pull schemas corresponding to these application adapters into the system.</span></span> <span data-ttu-id="79879-106">HTTP などのトランスポート アダプターでは通常、スキーマが使用されません。</span><span class="sxs-lookup"><span data-stu-id="79879-106">Note that transport adapters such as HTTP do not typically use schemas.</span></span>  
  
 <span data-ttu-id="79879-107">次の手順は、アダプターのメタデータを追加する一般的な手順です。</span><span class="sxs-lookup"><span data-stu-id="79879-107">The following procedure walks you through the generic steps to add metadata for an adapter.</span></span>  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="79879-108">BizTalk プロジェクトにアダプター メタデータを追加するには</span><span class="sxs-lookup"><span data-stu-id="79879-108">To add adapter metadata to a BizTalk project</span></span>  
  
1.  <span data-ttu-id="79879-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクト、ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="79879-109">In your [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="79879-110">**生成した項目の追加 - \<** *プロジェクト名* **>**   ダイアログ ボックスで、**テンプレート** セクションで、選択**アダプターの追加**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="79879-110">In the **Add Generated Items - \<***Project name***>** dialog box, in the **Templates** section, select **Add Adapter**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="79879-111">アダプター メタデータの追加ウィザードで、**アダプターの選択** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79879-111">In the Add Adapter Metadata Wizard, on the **Select Adapter** page, do the following.</span></span>  
  
    |<span data-ttu-id="79879-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="79879-112">Use this</span></span>|<span data-ttu-id="79879-113">目的</span><span class="sxs-lookup"><span data-stu-id="79879-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="79879-114">[アダプター] ボックス</span><span class="sxs-lookup"><span data-stu-id="79879-114">Adapter list box</span></span>|<span data-ttu-id="79879-115">プロジェクトに追加する登録済みのアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="79879-115">Select the registered adapter to add to the project.</span></span>|  
    |<span data-ttu-id="79879-116">SQL Server</span><span class="sxs-lookup"><span data-stu-id="79879-116">SQL Server</span></span>|<span data-ttu-id="79879-117">BizTalk データベース サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="79879-117">Enter the BizTalk database server name.</span></span>|  
    |<span data-ttu-id="79879-118">データベース</span><span class="sxs-lookup"><span data-stu-id="79879-118">Database</span></span>|<span data-ttu-id="79879-119">選択したサーバーの BizTalk 管理データベースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="79879-119">Displays the list of BizTalk Management databases for the chosen server.</span></span>|  
    |<span data-ttu-id="79879-120">ポート</span><span class="sxs-lookup"><span data-stu-id="79879-120">Port</span></span>|<span data-ttu-id="79879-121">省略可。</span><span class="sxs-lookup"><span data-stu-id="79879-121">Optional.</span></span> <span data-ttu-id="79879-122">作成されて、BizTalk 管理データベースに格納されているポートの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="79879-122">Displays the list of ports created and stored in the BizTalk Management database.</span></span> <span data-ttu-id="79879-123">選択したアダプターで使用できるように構成されているポートだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79879-123">Only ports configured to work with the selected adapter are shown.</span></span>|  
  
     <span data-ttu-id="79879-124">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79879-124">Click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79879-125">文字が含まれている生成されたスキーマを追加しようとすると、 **System.XML.XMLConvert**クラスは、コンパイル エラーの結果をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="79879-125">Attempting to add generated schemas that contain characters that the **System.XML.XMLConvert** class does not support results in a compilation error.</span></span>  
  
4.  <span data-ttu-id="79879-126">静的なアダプターを使用している場合、 **[インポートするサービス**] ページで、ツリー ビューから利用可能なサービスのセットを選択してをクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="79879-126">If you are using a static adapter, on the **Select Services to Import** page, select a set of available services from the tree view, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="79879-127">- または -</span><span class="sxs-lookup"><span data-stu-id="79879-127">–Or–</span></span>  
  
     <span data-ttu-id="79879-128">動的アダプターを使用している場合は、カスタム ユーザー インターフェイスの手順に従ってウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="79879-128">If you are using a dynamic adapter, follow the steps in the custom user interface to complete the wizard.</span></span>  
  
 <span data-ttu-id="79879-129">ウィザードが完了すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーに、.odx ファイルおよび .xsd ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79879-129">After you complete the wizard, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] lists the .odx and .xsd files in Solution Explorer.</span></span>