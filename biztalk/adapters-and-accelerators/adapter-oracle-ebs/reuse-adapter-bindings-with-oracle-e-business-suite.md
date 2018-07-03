---
title: Oracle E-business suite アダプターのバインドを再利用 |Microsoft Docs
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
ms.openlocfilehash: 3b4e906d9a0d7bf0c936f826bffb053e66e93bfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976171"
---
# <a name="reuse-adapter-bindings-with-oracle-e-business-suite"></a><span data-ttu-id="6f2e9-102">Oracle E-business suite アダプターのバインドを再利用します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-102">Reuse adapter bindings with Oracle E-Business Suite</span></span>
<span data-ttu-id="6f2e9-103">バインド (オーケストレーション ポートやロール リンクの場合) 論理的エンドポイントとの物理的なエンドポイント間のマッピングを作成します (などの送信と受信ポート)。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="6f2e9-104">これにより、さまざまなコンポーネントの間の通信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ビジネス ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-104">This enables communication between different components of a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] business solution.</span></span> <span data-ttu-id="6f2e9-105">バインドを作成するを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-105">You can create bindings by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="6f2e9-106">バインド ファイルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-106">What is a Binding File?</span></span>  
 <span data-ttu-id="6f2e9-107">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="6f2e9-108">バインド ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-108">The binding file describes:</span></span>  
  
- <span data-ttu-id="6f2e9-109">各オーケストレーションがバインドされているホスト。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-109">The host to which each orchestration is bound.</span></span>  
  
- <span data-ttu-id="6f2e9-110">ホストの信頼レベル。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-110">The trust level of the host.</span></span>  
  
- <span data-ttu-id="6f2e9-111">各設定は、送信ポート、受信ポート、受信場所、およびパーティが構成されています。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-111">The settings for each send port, receive port, receive location, and party that has been configured.</span></span>  
  
  <span data-ttu-id="6f2e9-112">バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれているバインドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="6f2e9-113">これにより、異なるデプロイ環境のバインドを手動で構成することによって、アプリケーションの展開を高速化します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
  <span data-ttu-id="6f2e9-114">バインド ファイルは BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="6f2e9-115">ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="6f2e9-116">同様をアプリケーションまたはグループにし、バインド ファイルをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-116">Similarly, you can then import the binding file into an application or group.</span></span> <span data-ttu-id="6f2e9-117">このセクションでは、インポートしてバインドをエクスポートする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-117">This section provides instructions on how to import and export bindings.</span></span>  
  
  <span data-ttu-id="6f2e9-118">バインドおよびバインド ファイルについての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-118">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>

  > [!NOTE]
  >  <span data-ttu-id="6f2e9-119">バインド ファイルは BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-119">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="6f2e9-120">バインドをエクスポートすることによって、バインド ファイルを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-120">But you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="6f2e9-121">アプリケーションまたはグループにバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-121">You can then import the binding file into an application or group.</span></span>  
 
## <a name="prerequisites"></a><span data-ttu-id="6f2e9-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="6f2e9-122">Prerequisites</span></span>    
<span data-ttu-id="6f2e9-123">I 番目のメンバーであるアカウントでのサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-123">Sign in ith an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="6f2e9-124">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-124">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>

## <a name="export-bindings"></a><span data-ttu-id="6f2e9-125">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-125">Export bindings</span></span>

<span data-ttu-id="6f2e9-126">このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-126">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="6f2e9-127">別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-127">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="6f2e9-128">バインドをインポートするには、アプリケーションで同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-128">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="6f2e9-129">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-129">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="6f2e9-130">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-130">The bindings that you add do not take effect until you import the application.</span></span>  

1. <span data-ttu-id="6f2e9-131">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-131">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="6f2e9-132">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-132">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="6f2e9-133">エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-133">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="6f2e9-134">**バインドのエクスポート**] ページの [**ファイルにエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-134">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="6f2e9-135">たとえば、入力します `C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="6f2e9-135">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5. <span data-ttu-id="6f2e9-136">確認します **、現在のアプリケーションからすべてのバインドをエクスポート**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-136">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6. <span data-ttu-id="6f2e9-137">グループのすべてのパーティ情報をエクスポートするには、選択、 **グローバル パーティ情報**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-137">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7. <span data-ttu-id="6f2e9-138">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-138">Select **OK**.</span></span> <span data-ttu-id="6f2e9-139">バインドは、指定した場所に XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-139">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="6f2e9-140">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="6f2e9-140">Import bindings</span></span>

<span data-ttu-id="6f2e9-141">BizTalk Server 管理コンソールを使用してバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-141">Import bindings using the BizTalk Server Administration console.</span></span>
  
1. <span data-ttu-id="6f2e9-142">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-142">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="6f2e9-143">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-143">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="6f2e9-144">バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-144">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="6f2e9-145">バインド ファイルを選択し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-145">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="6f2e9-146">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-146">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="6f2e9-147">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-147">They display in appropriate folders of the application.</span></span> <span data-ttu-id="6f2e9-148">たとえば、送信ポートが バインドの表示の一部としてインポート、**送信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-148">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  
  
## <a name="passwords-are-removed"></a><span data-ttu-id="6f2e9-149">パスワードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-149">Passwords are removed</span></span>  
<span data-ttu-id="6f2e9-150">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-150">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="6f2e9-151">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-151">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="6f2e9-152">[トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールの送信ポートまたは受信場所。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-152">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="6f2e9-153">ユーザー名とパスワードを指定する方法の詳細については、次を参照してください。 [、Oracle E-business Suite のサインイン資格情報を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f2e9-153">For information about specifying user name and passwords, see [Configure the sign-in credentials for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f2e9-154">参照</span><span class="sxs-lookup"><span data-stu-id="6f2e9-154">See Also</span></span>  
[<span data-ttu-id="6f2e9-155">Oracle E-business Suite のアプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="6f2e9-155">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)