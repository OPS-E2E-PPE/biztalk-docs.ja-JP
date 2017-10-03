---
title: "Siebel アダプターのアダプターのバインドを再利用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding file, definition
- adapter bindings, reusing
ms.assetid: 1dc17b7a-5397-43f4-b19e-9c50fb0e97ff
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bff4d1f4566f758b7cc6d1d37efcb30f651d9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reuse-adapter-bindings-in-the-siebel-adapter"></a><span data-ttu-id="ff5b4-102">Siebel アダプターのアダプターのバインドを再利用します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-102">Reuse adapter bindings in the Siebel adapter</span></span>
<span data-ttu-id="ff5b4-103">バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、ポートまたはパーティを受信します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-103">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="ff5b4-104">これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="ff5b4-105">バインドを作成するには BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="ff5b4-106">バインド ファイルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-106">What is a binding file?</span></span>  
<span data-ttu-id="ff5b4-107">バインド ファイルとは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="ff5b4-108">バインド ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-108">The binding file describes:</span></span>  
  
-   <span data-ttu-id="ff5b4-109">各オーケストレーションがバインドされているホスト</span><span class="sxs-lookup"><span data-stu-id="ff5b4-109">The host to which each orchestration is bound</span></span>
  
-   <span data-ttu-id="ff5b4-110">ホストの信頼レベル</span><span class="sxs-lookup"><span data-stu-id="ff5b4-110">The trust level of the host</span></span>
  
-   <span data-ttu-id="ff5b4-111">送信ポート、受信ポート、受信場所、およびパーティが構成されているそれぞれの設定</span><span class="sxs-lookup"><span data-stu-id="ff5b4-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
 <span data-ttu-id="ff5b4-112">バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれているバインドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="ff5b4-113">これにより、さまざまな展開環境のバインドを手動で構成することによってし、アプリケーションの展開を高速化します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
 <span data-ttu-id="ff5b4-114">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="ff5b4-115">ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="ff5b4-116">バインド ファイルをインポートして、アプリケーションまたはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-116">You can then import the binding file into an application or group.</span></span>  
  
 <span data-ttu-id="ff5b4-117">バインドおよびバインド ファイルについての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>
 
 > [!NOTE]
 >  <span data-ttu-id="ff5b4-118">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-118">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="ff5b4-119">バインドをエクスポートすることによって、バインド ファイルを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-119">But you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="ff5b4-120">バインド ファイルをインポートして、アプリケーションまたはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-120">You can then import the binding file into an application or group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff5b4-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="ff5b4-121">Prerequisites</span></span>  
<span data-ttu-id="ff5b4-122">I 番目のメンバーであるアカウントのサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-122">Sign in ith an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="ff5b4-123">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-123">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>

 
## <a name="export-bindings"></a><span data-ttu-id="ff5b4-124">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-124">Export bindings</span></span>
<span data-ttu-id="ff5b4-125">このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-125">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="ff5b4-126">別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-126">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="ff5b4-127">バインドをインポートするには、アプリケーション内の同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-127">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="ff5b4-128">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-128">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="ff5b4-129">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-129">The bindings that you add do not take effect until you import the application.</span></span>  
  
1.  <span data-ttu-id="ff5b4-130">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-130">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ff5b4-131">展開**BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-131">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ff5b4-132">エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-132">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="ff5b4-133">**バインドのエクスポート**] ページの [**ファイルへのエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-133">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="ff5b4-134">たとえば、入力します。`C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="ff5b4-134">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5.  <span data-ttu-id="ff5b4-135">いることを確認**、現在のアプリケーションからのすべてのバインドをエクスポート**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-135">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6.  <span data-ttu-id="ff5b4-136">グループのすべてのパーティ情報をエクスポートするには、選択、**グローバル パーティ情報をエクスポート**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-136">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7.  <span data-ttu-id="ff5b4-137">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-137">Select **OK**.</span></span> <span data-ttu-id="ff5b4-138">バインディングは、指定した場所に XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-138">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="ff5b4-139">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="ff5b4-139">Import bindings</span></span>
<span data-ttu-id="ff5b4-140">BizTalk Server 管理コンソールを使用してバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-140">Import bindings using the BizTalk Server Administration console.</span></span>
  
1.  <span data-ttu-id="ff5b4-141">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-141">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ff5b4-142">展開**BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-142">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ff5b4-143">バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-143">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="ff5b4-144">バインド ファイルを選択し、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-144">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="ff5b4-145">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-145">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="ff5b4-146">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-146">They display in appropriate folders of the application.</span></span> <span data-ttu-id="ff5b4-147">バインドの表示の一部として、送信ポートをインポートするなど、**送信ポート**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-147">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="ff5b4-148">パスワードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-148">Passwords are removed</span></span>  
<span data-ttu-id="ff5b4-149">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-149">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="ff5b4-150">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-150">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="ff5b4-151">[トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンソールの送信ポートまたは受信場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-151">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="ff5b4-152">ユーザー名とパスワードを指定する方法の詳細については、次を参照してください。 [、Siebel の資格情報 で、サインオンの構成](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="ff5b4-152">For information about specifying user name and passwords, see [Configure the sign in credentials for the Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff5b4-153">参照</span><span class="sxs-lookup"><span data-stu-id="ff5b4-153">See also</span></span>
[<span data-ttu-id="ff5b4-154">Siebel アダプターと BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="ff5b4-154">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)