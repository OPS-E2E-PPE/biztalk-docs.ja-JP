---
title: SQL アダプターのバインドを再利用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8bc8140f-1d40-492c-bce1-b85e992b3567
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6995f62b6dc94734b6e5dac01fad4284e6fcf7fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009987"
---
# <a name="reuse-sql-adapter-bindings"></a><span data-ttu-id="ac759-102">SQL アダプターのバインドを再利用します。</span><span class="sxs-lookup"><span data-stu-id="ac759-102">Reuse SQL adapter bindings</span></span>
<span data-ttu-id="ac759-103">バインド (オーケストレーション ポートやロール リンクの場合) 論理的エンドポイントとの物理的なエンドポイント間のマッピングを作成します (などの送信と受信ポート)。</span><span class="sxs-lookup"><span data-stu-id="ac759-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="ac759-104">これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac759-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="ac759-105">バインドを作成するを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ac759-105">You can create bindings by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="ac759-106">バインド ファイルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="ac759-106">What is a Binding File?</span></span>  
 <span data-ttu-id="ac759-107">バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="ac759-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="ac759-108">バインド ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ac759-108">The binding file describes:</span></span>  
  
- <span data-ttu-id="ac759-109">各オーケストレーションがバインドされているホスト。</span><span class="sxs-lookup"><span data-stu-id="ac759-109">The host to which each orchestration is bound.</span></span>  
  
- <span data-ttu-id="ac759-110">ホストの信頼レベル。</span><span class="sxs-lookup"><span data-stu-id="ac759-110">The trust level of the host.</span></span>  
  
- <span data-ttu-id="ac759-111">各設定は、送信ポート、受信ポート、受信場所、およびパーティが構成されています。</span><span class="sxs-lookup"><span data-stu-id="ac759-111">The settings for each send port, receive port, receive location, and party that has been configured.</span></span>  
  
  <span data-ttu-id="ac759-112">バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれているバインドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ac759-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="ac759-113">これにより、異なるデプロイ環境のバインドを手動で構成することによって、アプリケーションの展開を高速化します。</span><span class="sxs-lookup"><span data-stu-id="ac759-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
  <span data-ttu-id="ac759-114">バインド ファイルは BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。</span><span class="sxs-lookup"><span data-stu-id="ac759-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="ac759-115">ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ac759-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="ac759-116">同様をアプリケーションまたはグループにし、バインド ファイルをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac759-116">Similarly, you can then import the binding file into an application or group.</span></span> <span data-ttu-id="ac759-117">このセクションでは、インポートしてバインドをエクスポートする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ac759-117">This section provides instructions on how to import and export bindings.</span></span>  
  
  <span data-ttu-id="ac759-118">バインドおよびバインド ファイルについての詳細については、[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac759-118">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ac759-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="ac759-119">Prerequisites</span></span>  
<span data-ttu-id="ac759-120">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="ac759-120">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="ac759-121">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="ac759-121">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
 
## <a name="export-bindings"></a><span data-ttu-id="ac759-122">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ac759-122">Export bindings</span></span>
<span data-ttu-id="ac759-123">このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac759-123">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="ac759-124">別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ac759-124">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="ac759-125">バインドをインポートするには、アプリケーションで同じ名前の既存のバインドが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ac759-125">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="ac759-126">バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ac759-126">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="ac759-127">アプリケーションをインポートしない限り、追加したバインドは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="ac759-127">The bindings that you add do not take effect until you import the application.</span></span>  
  
1. <span data-ttu-id="ac759-128">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ac759-128">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="ac759-129">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="ac759-129">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="ac759-130">エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="ac759-130">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="ac759-131">**バインドのエクスポート**] ページの [**ファイルにエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ac759-131">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="ac759-132">たとえば、入力します `C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="ac759-132">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5. <span data-ttu-id="ac759-133">確認します **、現在のアプリケーションからすべてのバインドをエクスポート**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ac759-133">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6. <span data-ttu-id="ac759-134">グループのすべてのパーティ情報をエクスポートするには、選択、 **グローバル パーティ情報**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ac759-134">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7. <span data-ttu-id="ac759-135">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac759-135">Select **OK**.</span></span> <span data-ttu-id="ac759-136">バインドは、指定した場所に XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ac759-136">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="ac759-137">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="ac759-137">Import bindings</span></span>
<span data-ttu-id="ac759-138">BizTalk Server 管理コンソールを使用してバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ac759-138">Import bindings using the BizTalk Server Administration console.</span></span>
  
1. <span data-ttu-id="ac759-139">開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ac759-139">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="ac759-140">展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="ac759-140">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="ac759-141">バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="ac759-141">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="ac759-142">バインド ファイルを選択し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="ac759-142">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="ac759-143">バインド ファイルのアイテムがアプリケーションに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ac759-143">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="ac759-144">これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac759-144">They display in appropriate folders of the application.</span></span> <span data-ttu-id="ac759-145">たとえば、送信ポートが バインドの表示の一部としてインポート、**送信ポート**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ac759-145">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="ac759-146">パスワードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="ac759-146">Passwords are removed</span></span>  
<span data-ttu-id="ac759-147">セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ac759-147">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="ac759-148">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac759-148">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="ac759-149">[トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールの送信ポートまたは受信場所。</span><span class="sxs-lookup"><span data-stu-id="ac759-149">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="ac759-150">ユーザー名とパスワードを指定する方法の詳細については、[for SQL Server 資格情報で、サインオンの構成](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac759-150">For information about specifying user name and passwords, see [Configure the sign in credentials for the SQL Server](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac759-151">参照</span><span class="sxs-lookup"><span data-stu-id="ac759-151">See Also</span></span>  
[<span data-ttu-id="ac759-152">SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="ac759-152">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)