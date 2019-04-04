---
title: Siebel アダプターのアダプターのバインドを再利用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding file, definition
- adapter bindings, reusing
ms.assetid: 1dc17b7a-5397-43f4-b19e-9c50fb0e97ff
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a85346b44a88b5776e9f586ddc56675f8ef9ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007043"
---
# <a name="reuse-adapter-bindings-in-the-siebel-adapter"></a><span data-ttu-id="cacc5-102">Siebel アダプターのアダプターのバインドを再利用します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-102">Reuse adapter bindings in the Siebel adapter</span></span>
<span data-ttu-id="cacc5-103">バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、受信ポートまたはパーティします。</span><span class="sxs-lookup"><span data-stu-id="cacc5-103">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="cacc5-104">これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cacc5-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="cacc5-105">バインドを作成するには BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="cacc5-106">バインド ファイルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="cacc5-106">What is a binding file?</span></span>  
<span data-ttu-id="cacc5-107">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="cacc5-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="cacc5-108">バインド ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-108">The binding file describes:</span></span>  
  
- <span data-ttu-id="cacc5-109">各オーケストレーションがバインドされているホスト</span><span class="sxs-lookup"><span data-stu-id="cacc5-109">The host to which each orchestration is bound</span></span>
  
- <span data-ttu-id="cacc5-110">ホストの信頼レベル</span><span class="sxs-lookup"><span data-stu-id="cacc5-110">The trust level of the host</span></span>
  
- <span data-ttu-id="cacc5-111">各設定の送信ポート、受信ポート、受信場所、およびパーティが構成されています。</span><span class="sxs-lookup"><span data-stu-id="cacc5-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
  <span data-ttu-id="cacc5-112">バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれているバインドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="cacc5-113">これにより、異なるデプロイ環境のバインドを手動で構成することによって、アプリケーションの展開を高速化します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
  <span data-ttu-id="cacc5-114">バインド ファイルは BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="cacc5-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="cacc5-115">ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="cacc5-116">アプリケーションまたはグループにバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-116">You can then import the binding file into an application or group.</span></span>  
  
  <span data-ttu-id="cacc5-117">バインドおよびバインド ファイルについての詳細については、[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cacc5-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>
 
  > [!NOTE]
  >  <span data-ttu-id="cacc5-118">バインド ファイルは BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="cacc5-118">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="cacc5-119">バインドをエクスポートすることによって、バインド ファイルを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-119">But you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="cacc5-120">アプリケーションまたはグループにバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-120">You can then import the binding file into an application or group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cacc5-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="cacc5-121">Prerequisites</span></span>  
<span data-ttu-id="cacc5-122">I 番目のメンバーであるアカウントでのサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="cacc5-122">Sign in ith an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="cacc5-123">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-123">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>

 
## <a name="export-bindings"></a><span data-ttu-id="cacc5-124">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cacc5-124">Export bindings</span></span>
<span data-ttu-id="cacc5-125">このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-125">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="cacc5-126">別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-126">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="cacc5-127">バインドをインポートするには、アプリケーションで同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-127">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="cacc5-128">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-128">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="cacc5-129">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="cacc5-129">The bindings that you add do not take effect until you import the application.</span></span>  
  
1. <span data-ttu-id="cacc5-130">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="cacc5-130">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="cacc5-131">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-131">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="cacc5-132">エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-132">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="cacc5-133">**バインドのエクスポート**] ページの [**ファイルにエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-133">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="cacc5-134">たとえば、入力します `C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="cacc5-134">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5. <span data-ttu-id="cacc5-135">確認します **、現在のアプリケーションからすべてのバインドをエクスポート**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="cacc5-135">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6. <span data-ttu-id="cacc5-136">グループのすべてのパーティ情報をエクスポートするには、選択、 **グローバル パーティ情報**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="cacc5-136">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7. <span data-ttu-id="cacc5-137">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-137">Select **OK**.</span></span> <span data-ttu-id="cacc5-138">バインドは、指定した場所に XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-138">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="cacc5-139">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="cacc5-139">Import bindings</span></span>
<span data-ttu-id="cacc5-140">BizTalk Server 管理コンソールを使用してバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="cacc5-140">Import bindings using the BizTalk Server Administration console.</span></span>
  
1. <span data-ttu-id="cacc5-141">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="cacc5-141">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="cacc5-142">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-142">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="cacc5-143">バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-143">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="cacc5-144">バインド ファイルを選択し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="cacc5-144">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="cacc5-145">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-145">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="cacc5-146">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-146">They display in appropriate folders of the application.</span></span> <span data-ttu-id="cacc5-147">たとえば、送信ポートが バインドの表示の一部としてインポート、**送信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="cacc5-147">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="cacc5-148">パスワードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-148">Passwords are removed</span></span>  
<span data-ttu-id="cacc5-149">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="cacc5-149">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="cacc5-150">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cacc5-150">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="cacc5-151">[トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールの送信ポートまたは受信場所。</span><span class="sxs-lookup"><span data-stu-id="cacc5-151">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="cacc5-152">ユーザー名とパスワードを指定する方法の詳細については、[、Siebel の資格情報で、サインオンの構成](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cacc5-152">For information about specifying user name and passwords, see [Configure the sign in credentials for the Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cacc5-153">参照</span><span class="sxs-lookup"><span data-stu-id="cacc5-153">See also</span></span>
[<span data-ttu-id="cacc5-154">Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="cacc5-154">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)