---
title: "アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4caf0531ee6cf952bfd343605b9b470c04c636d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-application"></a><span data-ttu-id="90042-102">アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="90042-102">Creating an Application</span></span>
<span data-ttu-id="90042-103">BizTalk アプリケーションを作成する 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="90042-103">There are three ways to create a BizTalk application.</span></span> <span data-ttu-id="90042-104">名前付け、参照、およびアプリケーションにアイテムを展開するためのいくつかのオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="90042-104">There are also several options for naming, referencing, and deploying artifacts to applications.</span></span>  
  
## <a name="creating-a-biztalk-application"></a><span data-ttu-id="90042-105">BizTalk アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="90042-105">Creating a BizTalk Application</span></span>  
 <span data-ttu-id="90042-106">3 つの方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="90042-106">The three ways are as follows:</span></span>  
  
1.  <span data-ttu-id="90042-107">BizTalk アプリケーションを作成するには、BizTalk Server 管理コンソールの [新しいアプリケーション] コマンドまたは BTSTask コマンド ライン ツールの AddApp コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="90042-107">Create the BizTalk application by using the New Application command of the BizTalk Server Administration console or the AddApp command of the BTSTask command-line tool.</span></span> <span data-ttu-id="90042-108">詳細については、これらのコマンドを使用して、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。</span><span class="sxs-lookup"><span data-stu-id="90042-108">For more information about using these commands, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
2.  <span data-ttu-id="90042-109">他のアプリケーションからエクスポートした .msi ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="90042-109">Import an .msi file that was exported from another application.</span></span> <span data-ttu-id="90042-110">アプリケーションが現在の BizTalk グループに存在しない場合、アプリケーション (そのアイテムを含む) は現在の BizTalk グループに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="90042-110">If the application does not already exist in the current BizTalk group, the application, including its artifacts, is automatically created in the current BizTalk group.</span></span> <span data-ttu-id="90042-111">アプリケーションのインポートの詳細については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。</span><span class="sxs-lookup"><span data-stu-id="90042-111">For more information about importing applications, see [How to Import a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).</span></span>  
  
3.  <span data-ttu-id="90042-112">Visual Studio から BizTalk アプリケーションへ BizTalk アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="90042-112">Deploy BizTalk assemblies from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="90042-113">Visual Studio でプロジェクトの展開プロパティで指定されたアプリケーションが現在の BizTalk グループに存在しない場合に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="90042-113">If the application specified in the deployment properties for a project in Visual Studio does not exist in the current BizTalk group, it will be automatically created.</span></span> <span data-ttu-id="90042-114">Visual Studio からアセンブリを展開する詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。</span><span class="sxs-lookup"><span data-stu-id="90042-114">For more information about deploying an assembly from Visual Studio, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>  
  
 <span data-ttu-id="90042-115">.Msi ファイルを使用してアプリケーションを展開する送信先アプリケーションする必要はありませんが存在するが、自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="90042-115">To deploy an application using an .msi file, the destination application does not need to exist, but will be automatically created.</span></span> <span data-ttu-id="90042-116">ただし、別のアプリケーションへのバインドをインポートする送信先アプリケーション存在しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="90042-116">However, to import bindings from one application to another, the destination application must already exist.</span></span> <span data-ttu-id="90042-117">それ以外の場合は、上記の手順のいずれかの操作を実行することによって作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90042-117">If not, you need to create it by performing one of the procedures listed above.</span></span>  
  
 <span data-ttu-id="90042-118">特定のアプリケーションを作成するために必要な手順の詳細については、次を参照してください。[アプリケーションを作成する方法](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。</span><span class="sxs-lookup"><span data-stu-id="90042-118">For more information about the specific steps required to create an application, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
## <a name="application-options"></a><span data-ttu-id="90042-119">アプリケーションのオプション</span><span class="sxs-lookup"><span data-stu-id="90042-119">Application Options</span></span>  
 <span data-ttu-id="90042-120">新しいアプリケーションを作成する前に、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="90042-120">Before creating a new application, you should do the following:</span></span>  
  
-   <span data-ttu-id="90042-121">アプリケーションの BizTalk グループ内で一意の名前を決定します。</span><span class="sxs-lookup"><span data-stu-id="90042-121">Determine a name that is unique within the BizTalk group for the application.</span></span>  
  
-   <span data-ttu-id="90042-122">新しいアプリケーションを新しいアプリケーションで再利用するアイテムを含む任意のアプリケーションからの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="90042-122">Add a reference from the new application to any application containing artifacts that you want to reuse in the new application.</span></span> <span data-ttu-id="90042-123">アプリケーション間の依存関係の詳細については、次を参照してください。[の依存関係とアプリケーションの配置](http://go.microsoft.com/fwlink/?LinkId=155008)(http://go.microsoft.com/fwlink/?LinkId=155008)。</span><span class="sxs-lookup"><span data-stu-id="90042-123">For more information about dependencies between applications, see [Dependencies and Application Deployment](http://go.microsoft.com/fwlink/?LinkId=155008) (http://go.microsoft.com/fwlink/?LinkId=155008).</span></span>  
  
-   <span data-ttu-id="90042-124">別のアプリケーションを別のアプリケーションに展開する必要があります、たとえばに共有成果物に一部のアイテムを展開するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="90042-124">Determine whether you want to deploy some artifacts into separate applications, for example, shared artifacts that should be deployed into their own separate application.</span></span>