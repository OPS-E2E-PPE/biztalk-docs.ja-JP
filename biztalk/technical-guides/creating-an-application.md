---
title: アプリケーションを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772ba15d357715d5ceeca3c229167a96f7ef6c60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987547"
---
# <a name="creating-an-application"></a><span data-ttu-id="6e153-102">アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e153-102">Creating an Application</span></span>
<span data-ttu-id="6e153-103">BizTalk アプリケーションを作成する 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="6e153-103">There are three ways to create a BizTalk application.</span></span> <span data-ttu-id="6e153-104">名前付け、参照、およびアプリケーションにアイテムを展開するいくつかのオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="6e153-104">There are also several options for naming, referencing, and deploying artifacts to applications.</span></span>  
  
## <a name="creating-a-biztalk-application"></a><span data-ttu-id="6e153-105">BizTalk アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e153-105">Creating a BizTalk Application</span></span>  
 <span data-ttu-id="6e153-106">3 つの方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e153-106">The three ways are as follows:</span></span>  
  
1. <span data-ttu-id="6e153-107">BizTalk アプリケーションを作成するには、BizTalk Server 管理コンソールの [新しいアプリケーション] コマンドまたは BTSTask コマンド ライン ツールの AddApp コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e153-107">Create the BizTalk application by using the New Application command of the BizTalk Server Administration console or the AddApp command of the BTSTask command-line tool.</span></span> <span data-ttu-id="6e153-108">詳細については、これらのコマンドを使用して、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)します。</span><span class="sxs-lookup"><span data-stu-id="6e153-108">For more information about using these commands, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
2. <span data-ttu-id="6e153-109">他のアプリケーションからエクスポートした .msi ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6e153-109">Import an .msi file that was exported from another application.</span></span> <span data-ttu-id="6e153-110">アプリケーションが現在の BizTalk グループに存在しない場合、アプリケーション (そのアイテムを含む) は現在の BizTalk グループに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e153-110">If the application does not already exist in the current BizTalk group, the application, including its artifacts, is automatically created in the current BizTalk group.</span></span> <span data-ttu-id="6e153-111">アプリケーションのインポートに関する詳細については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)します。</span><span class="sxs-lookup"><span data-stu-id="6e153-111">For more information about importing applications, see [How to Import a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).</span></span>  
  
3. <span data-ttu-id="6e153-112">Visual Studio から BizTalk アプリケーションへ BizTalk アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="6e153-112">Deploy BizTalk assemblies from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="6e153-113">Visual Studio でプロジェクトの配置プロパティで指定されたアプリケーションが現在の BizTalk グループに存在しない場合に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e153-113">If the application specified in the deployment properties for a project in Visual Studio does not exist in the current BizTalk group, it will be automatically created.</span></span> <span data-ttu-id="6e153-114">Visual Studio からアセンブリを展開の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)します。</span><span class="sxs-lookup"><span data-stu-id="6e153-114">For more information about deploying an assembly from Visual Studio, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>  
  
   <span data-ttu-id="6e153-115">.Msi ファイルを使用してアプリケーションを展開するには、コピー先のアプリケーションは存在しますが必要ありませんが、自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e153-115">To deploy an application using an .msi file, the destination application does not need to exist, but will be automatically created.</span></span> <span data-ttu-id="6e153-116">ただし、別のアプリケーションへのバインドをインポートするコピー先のアプリケーションが既に存在します。</span><span class="sxs-lookup"><span data-stu-id="6e153-116">However, to import bindings from one application to another, the destination application must already exist.</span></span> <span data-ttu-id="6e153-117">それ以外の場合は、上記の手順のいずれかを実行して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e153-117">If not, you need to create it by performing one of the procedures listed above.</span></span>  
  
   <span data-ttu-id="6e153-118">特定のアプリケーションを作成するために必要な手順の詳細については、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)します。</span><span class="sxs-lookup"><span data-stu-id="6e153-118">For more information about the specific steps required to create an application, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
## <a name="application-options"></a><span data-ttu-id="6e153-119">アプリケーションのオプション</span><span class="sxs-lookup"><span data-stu-id="6e153-119">Application Options</span></span>  
 <span data-ttu-id="6e153-120">新しいアプリケーションを作成する前に、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e153-120">Before creating a new application, you should do the following:</span></span>  
  
-   <span data-ttu-id="6e153-121">アプリケーションの BizTalk グループ内で一意の名前を決定します。</span><span class="sxs-lookup"><span data-stu-id="6e153-121">Determine a name that is unique within the BizTalk group for the application.</span></span>  
  
-   <span data-ttu-id="6e153-122">新しいアプリケーションで再利用するアイテムを含む任意のアプリケーションに新しいアプリケーションからの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e153-122">Add a reference from the new application to any application containing artifacts that you want to reuse in the new application.</span></span> <span data-ttu-id="6e153-123">アプリケーション間の依存関係の詳細については、次を参照してください。[依存関係とアプリケーションの展開](http://go.microsoft.com/fwlink/?LinkId=155008)(http://go.microsoft.com/fwlink/?LinkId=155008)します。</span><span class="sxs-lookup"><span data-stu-id="6e153-123">For more information about dependencies between applications, see [Dependencies and Application Deployment](http://go.microsoft.com/fwlink/?LinkId=155008) (http://go.microsoft.com/fwlink/?LinkId=155008).</span></span>  
  
-   <span data-ttu-id="6e153-124">別のアプリケーションに配置するか、共有アイテムなどの別のアプリケーションにいくつかの成果物を配置するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6e153-124">Determine whether you want to deploy some artifacts into separate applications, for example, shared artifacts that should be deployed into their own separate application.</span></span>