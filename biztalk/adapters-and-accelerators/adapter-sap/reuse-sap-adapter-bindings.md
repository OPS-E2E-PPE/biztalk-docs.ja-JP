---
title: SAP アダプターのバインドを再利用 |Microsoft Docs
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
ms.assetid: 5748c22f-20a2-4eb9-ad45-a1bef7290802
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32fa550d51067cae20451651674ad57144acce02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373014"
---
# <a name="reuse-sap-adapter-bindings"></a><span data-ttu-id="bb72a-102">SAP アダプターのバインドを再利用します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-102">Reuse SAP adapter bindings</span></span>
<span data-ttu-id="bb72a-103">バインド (オーケストレーション ポートやロール リンクの場合) 論理的エンドポイントとの物理的なエンドポイント間のマッピングを作成します (などの送信と受信ポート)。</span><span class="sxs-lookup"><span data-stu-id="bb72a-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="bb72a-104">これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb72a-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="bb72a-105">バインドを作成するには BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="bb72a-106">バインド ファイルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="bb72a-106">What is a Binding File?</span></span>  
 <span data-ttu-id="bb72a-107">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="bb72a-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="bb72a-108">バインド ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-108">The binding file describes:</span></span>  
  
- <span data-ttu-id="bb72a-109">各オーケストレーションがバインドされているホスト</span><span class="sxs-lookup"><span data-stu-id="bb72a-109">The host to which each orchestration is bound</span></span>
  
- <span data-ttu-id="bb72a-110">ホストの信頼レベル</span><span class="sxs-lookup"><span data-stu-id="bb72a-110">The trust level of the host</span></span>
  
- <span data-ttu-id="bb72a-111">各設定の送信ポート、受信ポート、受信場所、およびパーティが構成されています。</span><span class="sxs-lookup"><span data-stu-id="bb72a-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
  <span data-ttu-id="bb72a-112">バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれるバインドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-112">You can generate binding files and then apply the bindings they contain to an assembly, application, or group.</span></span> <span data-ttu-id="bb72a-113">これにより、異なるデプロイ環境のバインドを手動で構成することによって、アプリケーションの展開を高速化します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
<span data-ttu-id="bb72a-114">バインド ファイルは BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="bb72a-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="bb72a-115">ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="bb72a-116">アプリケーションまたはグループにバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-116">You can then import the binding file into an application or group.</span></span>  
  
<span data-ttu-id="bb72a-117">バインドおよびバインド ファイルについての詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="bb72a-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="bb72a-118">Prerequisites</span></span>  
<span data-ttu-id="bb72a-119">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="bb72a-119">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="bb72a-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-120">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>
 
## <a name="export-bindings"></a><span data-ttu-id="bb72a-121">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bb72a-121">Export bindings</span></span>
<span data-ttu-id="bb72a-122">このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-122">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="bb72a-123">別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-123">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="bb72a-124">バインドをインポートするには、アプリケーションで同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-124">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="bb72a-125">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-125">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="bb72a-126">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="bb72a-126">The bindings that you add do not take effect until you import the application.</span></span>  
  
1. <span data-ttu-id="bb72a-127">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="bb72a-127">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="bb72a-128">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-128">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="bb72a-129">エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-129">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="bb72a-130">**バインドのエクスポート**] ページの [**ファイルにエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-130">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="bb72a-131">たとえば、入力します `C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="bb72a-131">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5. <span data-ttu-id="bb72a-132">確認します **、現在のアプリケーションからすべてのバインドをエクスポート**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="bb72a-132">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6. <span data-ttu-id="bb72a-133">グループのすべてのパーティ情報をエクスポートするには、選択、 **グローバル パーティ情報**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="bb72a-133">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7. <span data-ttu-id="bb72a-134">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-134">Select **OK**.</span></span> <span data-ttu-id="bb72a-135">バインドは、指定した場所に XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-135">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="bb72a-136">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="bb72a-136">Import bindings</span></span>
<span data-ttu-id="bb72a-137">BizTalk Server 管理コンソールを使用してバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="bb72a-137">Import bindings using the BizTalk Server Administration console.</span></span>
  
1. <span data-ttu-id="bb72a-138">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="bb72a-138">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="bb72a-139">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-139">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="bb72a-140">バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-140">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="bb72a-141">バインド ファイルを選択し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-141">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="bb72a-142">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-142">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="bb72a-143">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-143">They display in appropriate folders of the application.</span></span> <span data-ttu-id="bb72a-144">たとえば、送信ポートが バインドの表示の一部としてインポート、**送信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bb72a-144">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="bb72a-145">パスワードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-145">Passwords are removed</span></span>  
<span data-ttu-id="bb72a-146">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="bb72a-146">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="bb72a-147">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb72a-147">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="bb72a-148">[トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールの送信ポートまたは受信場所。</span><span class="sxs-lookup"><span data-stu-id="bb72a-148">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="bb72a-149">ユーザー名とパスワードを指定する方法の詳細については、次を参照してください。 [SAP システムの資格情報で、サインオンの構成](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb72a-149">For information about specifying user name and passwords, see [Configure the sign in credentials for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bb72a-150">参照</span><span class="sxs-lookup"><span data-stu-id="bb72a-150">See also</span></span>
[<span data-ttu-id="bb72a-151">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="bb72a-151">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)