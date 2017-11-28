---
title: "Oracle データベース アダプターのバインドを再利用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, reusing
- binding file
ms.assetid: f3c7af97-6da2-47bd-bdaf-6b45386c2940
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d84f20abe59436ed6fde5c773b99d23fd49e65a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reuse-oracle-database-adapter-bindings"></a><span data-ttu-id="eb5e5-102">Oracle データベース アダプターのバインドを再利用します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-102">Reuse Oracle Database Adapter bindings</span></span>
<span data-ttu-id="eb5e5-103">バインド (オーケストレーション ポート、ロール リンクなど) の論理エンドポイントとの物理的なエンドポイント間のマッピングを作成する (など、送信と受信ポート)。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="eb5e5-104">これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="eb5e5-105">バインドを作成するには BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="eb5e5-106">バインド ファイルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-106">What is a binding file?</span></span>  
 <span data-ttu-id="eb5e5-107">バインド ファイルとは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="eb5e5-108">バインド ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-108">The binding file describes:</span></span>  
  
-   <span data-ttu-id="eb5e5-109">各オーケストレーションがバインドされているホスト</span><span class="sxs-lookup"><span data-stu-id="eb5e5-109">The host to which each orchestration is bound</span></span>
  
-   <span data-ttu-id="eb5e5-110">ホストの信頼レベル</span><span class="sxs-lookup"><span data-stu-id="eb5e5-110">The trust level of the host</span></span>
  
-   <span data-ttu-id="eb5e5-111">送信ポート、受信ポート、受信場所、およびパーティが構成されているそれぞれの設定</span><span class="sxs-lookup"><span data-stu-id="eb5e5-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
 <span data-ttu-id="eb5e5-112">バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれているバインドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="eb5e5-113">これにより、さまざまな展開環境のバインドを手動で構成することによってし、アプリケーションの展開を高速化します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
 <span data-ttu-id="eb5e5-114">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="eb5e5-115">ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="eb5e5-116">バインド ファイルをインポートして、アプリケーションまたはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-116">You can then import the binding file into an application or group.</span></span>  
  
 <span data-ttu-id="eb5e5-117">バインドおよびバインド ファイルについての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb5e5-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="eb5e5-118">Prerequisites</span></span>  
<span data-ttu-id="eb5e5-119">メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-119">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="eb5e5-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-120">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>

 
## <a name="export-bindings"></a><span data-ttu-id="eb5e5-121">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-121">Export bindings</span></span>
<span data-ttu-id="eb5e5-122">このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-122">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="eb5e5-123">別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-123">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="eb5e5-124">バインドをインポートするには、アプリケーション内の同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-124">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="eb5e5-125">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-125">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="eb5e5-126">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-126">The bindings that you add do not take effect until you import the application.</span></span>  
  
1.  <span data-ttu-id="eb5e5-127">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-127">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="eb5e5-128">展開**BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-128">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="eb5e5-129">エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-129">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="eb5e5-130">**バインドのエクスポート**] ページの [**ファイルへのエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-130">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="eb5e5-131">たとえば、入力します。`C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="eb5e5-131">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5.  <span data-ttu-id="eb5e5-132">いることを確認**、現在のアプリケーションからのすべてのバインドをエクスポート**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-132">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6.  <span data-ttu-id="eb5e5-133">グループのすべてのパーティ情報をエクスポートするには、選択、**グローバル パーティ情報をエクスポート**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-133">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7.  <span data-ttu-id="eb5e5-134">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-134">Select **OK**.</span></span> <span data-ttu-id="eb5e5-135">バインディングは、指定した場所に XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-135">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="eb5e5-136">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="eb5e5-136">Import bindings</span></span>
<span data-ttu-id="eb5e5-137">BizTalk Server 管理コンソールを使用してバインドのインポート</span><span class="sxs-lookup"><span data-stu-id="eb5e5-137">Import bindings using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="eb5e5-138">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-138">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="eb5e5-139">展開**BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-139">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="eb5e5-140">バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-140">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="eb5e5-141">バインド ファイルを選択し、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-141">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="eb5e5-142">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-142">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="eb5e5-143">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-143">They display in appropriate folders of the application.</span></span> <span data-ttu-id="eb5e5-144">バインドの表示の一部として、送信ポートをインポートするなど、**送信ポート**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-144">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="eb5e5-145">パスワードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-145">Passwords are removed</span></span>  
<span data-ttu-id="eb5e5-146">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-146">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="eb5e5-147">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-147">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="eb5e5-148">[トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンソールの送信ポートまたは受信場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-148">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="eb5e5-149">ユーザー名とパスワードを指定する方法の詳細については、次を参照してください。 [Oracle データベースの資格情報 で、サインオンの構成](../../adapters-and-accelerators/adapter-oracle-database/configure-the-sign-in-credentials-for-the-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb5e5-149">For information about specifying user name and passwords, see [Configure the sign in credentials for the Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-sign-in-credentials-for-the-oracle-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5e5-150">参照</span><span class="sxs-lookup"><span data-stu-id="eb5e5-150">See Also</span></span>  
[<span data-ttu-id="eb5e5-151">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="eb5e5-151">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)