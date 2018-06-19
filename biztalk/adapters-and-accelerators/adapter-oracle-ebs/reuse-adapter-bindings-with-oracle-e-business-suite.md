---
title: Oracle E-business Suite でアダプターのバインドを再利用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb4dd90d-7958-4d62-bc7b-d6be16288dbc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25aec8346a4252902e37a778384ae603852a11be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215770"
---
# <a name="reuse-adapter-bindings-with-oracle-e-business-suite"></a><span data-ttu-id="50516-102">Oracle E-business Suite でアダプターのバインドを再利用します。</span><span class="sxs-lookup"><span data-stu-id="50516-102">Reuse adapter bindings with Oracle E-Business Suite</span></span>
<span data-ttu-id="50516-103">バインド (オーケストレーション ポート、ロール リンクなど) の論理エンドポイントとの物理的なエンドポイント間のマッピングを作成する (など、送信と受信ポート)。</span><span class="sxs-lookup"><span data-stu-id="50516-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="50516-104">これにより、さまざまなコンポーネントの間の通信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ビジネス ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="50516-104">This enables communication between different components of a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] business solution.</span></span> <span data-ttu-id="50516-105">バインドを作成するを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="50516-105">You can create bindings by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="50516-106">バインド ファイルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="50516-106">What is a Binding File?</span></span>  
 <span data-ttu-id="50516-107">バインド ファイルとは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="50516-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="50516-108">バインド ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="50516-108">The binding file describes:</span></span>  
  
-   <span data-ttu-id="50516-109">各オーケストレーションがバインドされているホスト。</span><span class="sxs-lookup"><span data-stu-id="50516-109">The host to which each orchestration is bound.</span></span>  
  
-   <span data-ttu-id="50516-110">ホストの信頼レベル。</span><span class="sxs-lookup"><span data-stu-id="50516-110">The trust level of the host.</span></span>  
  
-   <span data-ttu-id="50516-111">各設定は、送信ポート、受信ポート、受信場所、およびパーティが構成されています。</span><span class="sxs-lookup"><span data-stu-id="50516-111">The settings for each send port, receive port, receive location, and party that has been configured.</span></span>  
  
 <span data-ttu-id="50516-112">バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれているバインドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="50516-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="50516-113">これにより、さまざまな展開環境のバインドを手動で構成することによってし、アプリケーションの展開を高速化します。</span><span class="sxs-lookup"><span data-stu-id="50516-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
 <span data-ttu-id="50516-114">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="50516-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="50516-115">ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="50516-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="50516-116">同様に、アプリケーションまたはグループにし、バインド ファイルをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="50516-116">Similarly, you can then import the binding file into an application or group.</span></span> <span data-ttu-id="50516-117">このセクションでは、インポートしてバインドをエクスポートする方法の指示を提供します。</span><span class="sxs-lookup"><span data-stu-id="50516-117">This section provides instructions on how to import and export bindings.</span></span>  
  
 <span data-ttu-id="50516-118">バインドおよびバインド ファイルについての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="50516-118">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>

 > [!NOTE]
 >  <span data-ttu-id="50516-119">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="50516-119">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="50516-120">バインドをエクスポートすることによって、バインド ファイルを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="50516-120">But you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="50516-121">バインド ファイルをインポートして、アプリケーションまたはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="50516-121">You can then import the binding file into an application or group.</span></span>  
 
## <a name="prerequisites"></a><span data-ttu-id="50516-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="50516-122">Prerequisites</span></span>    
<span data-ttu-id="50516-123">I 番目のメンバーであるアカウントのサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="50516-123">Sign in ith an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="50516-124">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="50516-124">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>

## <a name="export-bindings"></a><span data-ttu-id="50516-125">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="50516-125">Export bindings</span></span>

<span data-ttu-id="50516-126">このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50516-126">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="50516-127">別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="50516-127">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="50516-128">バインドをインポートするには、アプリケーション内の同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="50516-128">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="50516-129">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="50516-129">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="50516-130">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="50516-130">The bindings that you add do not take effect until you import the application.</span></span>  

1.  <span data-ttu-id="50516-131">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="50516-131">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="50516-132">展開**BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="50516-132">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="50516-133">エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="50516-133">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="50516-134">**バインドのエクスポート**] ページの [**ファイルへのエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="50516-134">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="50516-135">たとえば、入力します。`C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="50516-135">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5.  <span data-ttu-id="50516-136">いることを確認 **、現在のアプリケーションからのすべてのバインドをエクスポート**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="50516-136">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6.  <span data-ttu-id="50516-137">グループのすべてのパーティ情報をエクスポートするには、選択、**グローバル パーティ情報をエクスポート**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="50516-137">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7.  <span data-ttu-id="50516-138">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50516-138">Select **OK**.</span></span> <span data-ttu-id="50516-139">バインディングは、指定した場所に XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="50516-139">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="50516-140">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="50516-140">Import bindings</span></span>

<span data-ttu-id="50516-141">BizTalk Server 管理コンソールを使用してバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="50516-141">Import bindings using the BizTalk Server Administration console.</span></span>
  
1.  <span data-ttu-id="50516-142">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="50516-142">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="50516-143">展開**BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="50516-143">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="50516-144">バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="50516-144">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="50516-145">バインド ファイルを選択し、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="50516-145">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="50516-146">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="50516-146">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="50516-147">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="50516-147">They display in appropriate folders of the application.</span></span> <span data-ttu-id="50516-148">バインドの表示の一部として、送信ポートをインポートするなど、**送信ポート**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="50516-148">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  
  
## <a name="passwords-are-removed"></a><span data-ttu-id="50516-149">パスワードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="50516-149">Passwords are removed</span></span>  
<span data-ttu-id="50516-150">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="50516-150">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="50516-151">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50516-151">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="50516-152">[トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンソールの送信ポートまたは受信場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="50516-152">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="50516-153">ユーザー名とパスワードを指定する方法の詳細については、次を参照してください。 [for Oracle E-business Suite サインイン資格情報を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="50516-153">For information about specifying user name and passwords, see [Configure the sign-in credentials for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50516-154">参照</span><span class="sxs-lookup"><span data-stu-id="50516-154">See Also</span></span>  
[<span data-ttu-id="50516-155">Oracle E-business Suite アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="50516-155">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)