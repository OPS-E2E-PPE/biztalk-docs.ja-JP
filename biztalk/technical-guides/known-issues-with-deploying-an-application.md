---
title: "アプリケーションの配置に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09970e43bd53306a6394eeffc4c2e642a8333dbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-deploying-an-application"></a><span data-ttu-id="b4585-102">アプリケーションの配置に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="b4585-102">Known Issues with Deploying an Application</span></span>
## <a name="deploying-a-biztalk-application"></a><span data-ttu-id="b4585-103">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="b4585-103">Deploying a BizTalk Application</span></span>  
 <span data-ttu-id="b4585-104">**更新されたアプリケーションを展開するには、参照を修正する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="b4585-104">**Deploying an updated application requires correcting references**</span></span>  
  
 <span data-ttu-id="b4585-105">まったく新しいアプリケーションを展開して既存のアプリケーションを置き換える場合は、このアプリケーションと他のアプリケーションとの間の参照をすべて修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4585-105">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
 <span data-ttu-id="b4585-106">**Visual Studio を使用してアプリケーションを展開すると、アプリケーションを停止できます。**</span><span class="sxs-lookup"><span data-stu-id="b4585-106">**Using Visual Studio to deploy an application can stop applications**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4585-107">運用環境にアプリケーションを配置する Visual Studio を使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4585-107">We recommend that you avoid using Visual Studio to deploy an application into a production environment.</span></span>  
  
 <span data-ttu-id="b4585-108">関連付けられていないものも含め、アプリケーションを展開するときに、実稼働環境にアプリケーションを配置する Visual Studio を使用して、ホスト インスタンスの再起動オプションが場合プロジェクト プロパティでは、すべてのホスト インスタンスは True に設定が再起動されます。このアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="b4585-108">If you use Visual Studio to deploy an application into a production environment and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="b4585-109">これにより、ローカル コンピューターのホスト インスタンスで実行されている他のすべてのアプリケーションが停止します。</span><span class="sxs-lookup"><span data-stu-id="b4585-109">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a><span data-ttu-id="b4585-110">BizTalk アプリケーションにアイテムを追加します。</span><span class="sxs-lookup"><span data-stu-id="b4585-110">Adding Artifacts to a BizTalk Application</span></span>  
 <span data-ttu-id="b4585-111">**依存関係を移動できるアイテムの移動します。**</span><span class="sxs-lookup"><span data-stu-id="b4585-111">**Moving an artifact can move dependencies**</span></span>  
  
 <span data-ttu-id="b4585-112">新しいアプリケーションにアイテムを移動するときの依存関係が存在するその他のアイテムが、新しいアプリケーションに移動した成果物が依存するアイテムを含むアプリケーションへの参照がない限り、移動されます。</span><span class="sxs-lookup"><span data-stu-id="b4585-112">When you move an artifact to a new application, any other artifacts on which it has dependencies are also moved unless the new application has a reference to the application(s) containing the artifacts that the moved artifact depends upon.</span></span> <span data-ttu-id="b4585-113">また、移動するアイテムに依存しているアイテムも、そのようなアイテムを含むアプリケーションが移動先のアプリケーションを参照している場合を除き、移動先のアプリケーションに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b4585-113">Also, any artifacts that have dependencies on the moved artifact also will be moved unless the application(s) containing them have a reference to the new application.</span></span> <span data-ttu-id="b4585-114">アイテムを移動する場合は、同時に移動するその他のアイテムの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4585-114">When moving an artifact, you will be shown the list of other artifacts that will also be moved.</span></span> <span data-ttu-id="b4585-115">アイテムの移動方法の詳細については、次を参照してください。[別のアプリケーションにアイテムを移動する方法](http://go.microsoft.com/fwlink/?LinkId=154999)(http://go.microsoft.com/fwlink/?LinkId=154999)。</span><span class="sxs-lookup"><span data-stu-id="b4585-115">For instructions on moving an artifact, see [How to Move an Artifact to a Different Application](http://go.microsoft.com/fwlink/?LinkId=154999) (http://go.microsoft.com/fwlink/?LinkId=154999).</span></span>  
  
## <a name="exporting-a-biztalk-application"></a><span data-ttu-id="b4585-116">BizTalk アプリケーションをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b4585-116">Exporting a BizTalk Application</span></span>  
 <span data-ttu-id="b4585-117">**Windows Vista で .msi ファイルをインストールするときに、誤ったエラーが表示されることができます。**</span><span class="sxs-lookup"><span data-stu-id="b4585-117">**An incorrect error can be displayed when installing an .msi file on Windows Vista**</span></span>  
  
 <span data-ttu-id="b4585-118">使用してエクスポートされた .msi パッケージをインストールするときに[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]で[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Windows Vista® で実行されている、次の誤ったエラーが表示される、"、インストーラーは、予期しないエラーがこのパッケージのインストールにしました。</span><span class="sxs-lookup"><span data-stu-id="b4585-118">When installing an .msi package exported using [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] on [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] running on Windows Vista®, you may receive the following incorrect error, "The installer has encountered an unexpected error installing this package.</span></span> <span data-ttu-id="b4585-119">このパッケージに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4585-119">This may indicate a problem with this package.</span></span> <span data-ttu-id="b4585-120">エラー コード: 2869。"</span><span class="sxs-lookup"><span data-stu-id="b4585-120">The error code is 2869."</span></span> <span data-ttu-id="b4585-121">このエラーを解決するには、最初にインポートを使用してパッケージ[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]再度エクスポートし、パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b4585-121">To correct this error, first import the package using [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and then re-export and install the package.</span></span>  
  
## <a name="importing-a-biztalk-application"></a><span data-ttu-id="b4585-122">BizTalk アプリケーションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b4585-122">Importing a BizTalk Application</span></span>  
 <span data-ttu-id="b4585-123">**パスワードは、アプリケーションに追加されたファイルのバインドから削除されません。**</span><span class="sxs-lookup"><span data-stu-id="b4585-123">**Passwords are not removed from binding files added to an application**</span></span>  
  
 <span data-ttu-id="b4585-124">セキュリティ上の理由により、パスワードは、アプリケーションのエクスポート中にアプリケーションのバインドから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b4585-124">For security reasons, during application export, passwords are removed from application bindings.</span></span> <span data-ttu-id="b4585-125">ただし、既にアプリケーションに追加されたバインド ファイルからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b4585-125">They are not, however, removed from any binding files that were added to the application.</span></span> <span data-ttu-id="b4585-126">アプリケーションをインポートした後、アプリケーションを機能させるためにパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4585-126">After importing the application, you will need to reconfigure the passwords in order for the application to function.</span></span> <span data-ttu-id="b4585-127">これは、バインド ファイルを編集するか、管理コンソールを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4585-127">You can do this by editing the binding file or by using the Administration console.</span></span> <span data-ttu-id="b4585-128">バインド ファイルの編集の詳細については、次を参照してください。[バインド ファイルのカスタマイズ](http://go.microsoft.com/fwlink/?LinkId=155000)(http://go.microsoft.com/fwlink/?LinkId=155000)。</span><span class="sxs-lookup"><span data-stu-id="b4585-128">For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkId=155000) (http://go.microsoft.com/fwlink/?LinkId=155000).</span></span> <span data-ttu-id="b4585-129">アダプターのセキュリティの構成の詳細については、次を参照してください。[を使用してアダプター](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001)。</span><span class="sxs-lookup"><span data-stu-id="b4585-129">For more information about configuring security for adapters, see [Using Adapters](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001).</span></span>  
  
 <span data-ttu-id="b4585-130">**BizTalk Server ではありませんロールバック スクリプトのインポートまたはインストール**</span><span class="sxs-lookup"><span data-stu-id="b4585-130">**BizTalk Server does not roll back scripted imports or installs**</span></span>  
  
 <span data-ttu-id="b4585-131">インポートに失敗した場合、BizTalk Server によってすべてのインポート操作がロールバックされます。ただし、カスタム スクリプトによって実行される操作は除きます。</span><span class="sxs-lookup"><span data-stu-id="b4585-131">If an import fails, BizTalk Server rolls back all import operations except for any actions performed by custom scripts.</span></span> <span data-ttu-id="b4585-132">これは、インストールにも該当し、操作をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b4585-132">This is also true for install and uninstall operations.</span></span>  
  
 <span data-ttu-id="b4585-133">**インポート後に、不足しているスキーマを報告されない可能性があります。**</span><span class="sxs-lookup"><span data-stu-id="b4585-133">**A missing schema might not be reported after an import**</span></span>  
  
 <span data-ttu-id="b4585-134">別のアプリケーションのプロパティ スキーマを使用するアプリケーションの送信ポートにフィルターを作成し、そのアプリケーションを新しい BizTalk グループにインポートした場合、そのアプリケーションをインストールおよび起動しても、フィルターは正しく機能せず、スキーマが欠落していることを伝える警告も発生しません。</span><span class="sxs-lookup"><span data-stu-id="b4585-134">If you create a filter for a send port in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="b4585-135">この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。</span><span class="sxs-lookup"><span data-stu-id="b4585-135">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4585-136">参照</span><span class="sxs-lookup"><span data-stu-id="b4585-136">See Also</span></span>  
 [<span data-ttu-id="b4585-137">アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="b4585-137">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)