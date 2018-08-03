---
title: LOBWebApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, LOBWebApplication
- ASPX pages, LOBWebApplication utility
- virtual servers
- ASPX pages, submitting actions
- LOBWebApplication
- ASPX pages, response messages
- LOBWebApplication utility
ms.assetid: 2d578efd-72a9-4621-9274-30792bf94b6c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9120d9078303092740fdbfc27b6932b7849cc6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002107"
---
# <a name="lobwebapplication"></a><span data-ttu-id="23f8f-102">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="23f8f-102">LOBWebApplication</span></span>
<span data-ttu-id="23f8f-103">LOBWebApplication ユーティリティは、実際の基幹業務 (LOB) Web アプリケーションをシミュレートして、ASPX ページから取引先にアクションまたは応答メッセージを送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-103">You use the LOBWebApplication utility to submit an action or response message from an ASPX page to a trading partner, simulating an actual line-of-business Web application.</span></span>  
  
 <span data-ttu-id="23f8f-104">ASPX ページをセットアップした後、ページを起動してメッセージのパラメーター (ホーム組織と取引先組織、PIP コード、PIP バージョン、PIP インスタンス ID、およびメッセージ カテゴリ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-104">After you have set up the ASPX page, you start the page, and enter the parameters for a message: the home and partner organizations; the PIP code, version, and instance ID; and the message category.</span></span> <span data-ttu-id="23f8f-105">その後、サービス コンテンツを変更してメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="23f8f-105">You can then modify the service content, and submit the message.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="23f8f-106">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="23f8f-106">Location in SDK</span></span>  
 <span data-ttu-id="23f8f-107">\<*ドライブ*\>\Program Files (86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication</span><span class="sxs-lookup"><span data-stu-id="23f8f-107">\<*drive*\>\Program Files (86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication</span></span>  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a><span data-ttu-id="23f8f-108">LOBWebApplication 用の仮想サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="23f8f-108">Adding a Virtual Server for LOBWebApplication</span></span>  
  
#### <a name="to-add-a-virtual-server"></a><span data-ttu-id="23f8f-109">仮想サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="23f8f-109">To add a virtual server</span></span>  
  
1.  <span data-ttu-id="23f8f-110">クリックして**開始**、 をポイント**シリアルキー**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="23f8f-110">Click **Start**, point to **AllPrograms**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="23f8f-111">インフォメーション サービス マネージャーで、展開**\<コンピューター名\>(ローカル コンピューター)**、展開**Web サイト**、右クリックし、**既定の Web サイト**.</span><span class="sxs-lookup"><span data-stu-id="23f8f-111">In Information Services Manager, expand **\<Computer name\> (local computer)**, expand **Web Sites**, and then right-click **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="23f8f-112">をポイント**新規**、 をクリックし、**仮想ディレクトリ**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-112">Point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="23f8f-113">**仮想ディレクトリの作成ウィザード**] ページで [**次**など、サイトのエイリアスを入力し、 **LOBWebApplication**。</span><span class="sxs-lookup"><span data-stu-id="23f8f-113">On the **Virtual Directory Creation Wizard** page, click **Next**, and then type an alias for the site, such as **LOBWebApplication**.</span></span>  
  
5.  <span data-ttu-id="23f8f-114">**Web サイトのコンテンツ ディレクトリ** ページで **参照**に移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk \<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication、 をクリックして**OK**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-114">On the **Web Site Content Directory** page, click **Browse**, move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication, click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="23f8f-115">**仮想ディレクトリのアクセス許可**] ページで、[**読み取り**と**スクリプトを実行する**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="23f8f-115">On the **Virtual Directory Access Permissions** page, select **Read** and **Run scripts**, and then click **Next**.</span></span> <span data-ttu-id="23f8f-116">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23f8f-116">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="23f8f-117">BTARN を構成するために使用するサービス アカウント ユーザー (hostsvc など) を STS_WPG に追加します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-117">Add the service account user that was used to configure BTARN, for example, hostsvc, to the STS_WPG.</span></span>  
  
8.  <span data-ttu-id="23f8f-118">C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files にあるファイルをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-118">Delete all files from C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files.</span></span> <span data-ttu-id="23f8f-119">ファイルを削除する前に、iisreset プログラムを実行してファイルのロックを解除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="23f8f-119">You may have to run the iisreset program to unlock the files before you can delete them.</span></span>  
  
9. <span data-ttu-id="23f8f-120">IIS マネージャーで、アプリケーション プール BTARNHTTPReceivePool の下で実行するように LOBWebApplication を設定します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-120">In IIS Manager, set the LOBWebApplication to run under the Application Pool BTARNHTTPReceivePool.</span></span>  
  
10. <span data-ttu-id="23f8f-121">IIS マネージャーを使用して、LOBWebApplication ユーティリティの [Directory Security Properties] セクションで、仮想ディレクトリを匿名で実行するオプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="23f8f-121">In IIS Manager, in the Directory Security Properties section for the LOBWebApplication utility, disable the option for the virtual directory to run as anonymous.</span></span>  
  
## <a name="building-lobwebapplication"></a><span data-ttu-id="23f8f-122">LOBWebApplication の構築</span><span class="sxs-lookup"><span data-stu-id="23f8f-122">Building LOBWebApplication</span></span>  
  
#### <a name="to-build-lobwebapplication"></a><span data-ttu-id="23f8f-123">LOBWebApplication を構築するには</span><span class="sxs-lookup"><span data-stu-id="23f8f-123">To build LOBWebApplication</span></span>  
  
1. <span data-ttu-id="23f8f-124">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-124">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="23f8f-125">**ファイル**、 をポイント**オープン**、 をクリックし、**ソリューションを開く**。</span><span class="sxs-lookup"><span data-stu-id="23f8f-125">On the **File**, point to **Open**, and then click **Open Solution**.</span></span>  
  
3. <span data-ttu-id="23f8f-126">移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication には、選択**LOBWebApplication.sln**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-126">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication, select **LOBWebApplication.sln**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="23f8f-127">LOBWebApplication 用の仮想サーバーを追加していない場合、ソリューションは [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で正常に開きません。</span><span class="sxs-lookup"><span data-stu-id="23f8f-127">If you have not added a virtual server for LOBWebApplication, the solution will not open correctly in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
4. <span data-ttu-id="23f8f-128">右クリック**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-128">Right-click **References**, and then click **Add Reference**.</span></span>  
  
5. <span data-ttu-id="23f8f-129">**参照の追加**ダイアログ ボックスで、をクリックして**参照**に移動\<*ドライブ*\>: \Program Files (x86) \Microsoft BizTalk \<バージョン\>Accelerator for rosettanet \bin が、Microsoft.Solutions.BTARN.ConfigurationManager.dll および Microsoft.Solutions.BTARN.Shared.dll ファイルを選択し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-129">In the **Add Reference** dialog box, click **Browse**, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin, select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll files, and then click **Open**.</span></span>  
  
6. <span data-ttu-id="23f8f-130">右クリック**LOBWebApplication**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-130">Right-click **LOBWebApplication**, and then click **Build**.</span></span>  
  
## <a name="running-lobwebapplication"></a><span data-ttu-id="23f8f-131">LOBWebApplication の実行</span><span class="sxs-lookup"><span data-stu-id="23f8f-131">Running LOBWebApplication</span></span>  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a><span data-ttu-id="23f8f-132">LOBWebApplication を実行してメッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="23f8f-132">To run LOBWebApplication and submit a message</span></span>  
  
1.  <span data-ttu-id="23f8f-133">クリックして**開始**、 をポイント**すべてのプログラム**、順にクリックします**Internet Explorer**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-133">Click **Start**, point to **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="23f8f-134">Internet Explorer で、**アドレス**ボックスに「 http://localhost/LOBWebApplication、 をクリックし、**移動**します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-134">In Internet Explorer, in the **Address** box, type http://localhost/LOBWebApplication, and then click **Go**.</span></span>  
  
3.  <span data-ttu-id="23f8f-135">**Submit Message**  ダイアログ ボックスに、ホーム組織、取引先組織、PIP コード、PIP バージョン、PIP インスタンス ID、およびメッセージ カテゴリを入力します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-135">In the **Submit Message** dialog box, type the home organization, the partner organization, the PIP code, the PIP version, the PIP Instance ID, and the message category.</span></span>  
  
4.  <span data-ttu-id="23f8f-136">必要に応じてサービス コンテンツを変更します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-136">Modify the service content as needed.</span></span>  
  
5.  <span data-ttu-id="23f8f-137">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23f8f-137">Click **Submit**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23f8f-138">コメント</span><span class="sxs-lookup"><span data-stu-id="23f8f-138">Remarks</span></span>  
 <span data-ttu-id="23f8f-139">LOBWebApplication ユーティリティは、指定した PIP からメッセージのインスタンスを生成し、ASPX ページに生成されたメッセージのインスタンスからサービスのコンテンツを入力します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-139">The LOBWebApplication utility generates an instance of the message from the specified PIP, and enters service content from the generated message instance into the ASPX page.</span></span> <span data-ttu-id="23f8f-140">この処理を実行する際、LOBWebApplication ユーティリティは、書式設定されたメッセージ インスタンスを PIP から直接生成するのと同じ技法を使用します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-140">To do this, the utility uses the same technique that it uses to generate a well-formed message instance directly from a PIP.</span></span> <span data-ttu-id="23f8f-141">詳細については、次を参照してください。 [PIP からの整形式メッセージ インスタンスを作成する](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md)します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-141">For more information, see [Creating a Well-Formed Message Instance from a PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md).</span></span> <span data-ttu-id="23f8f-142">ASPX ページのサービス コンテンツのフィールドに実際のデータを入力すると、実際のメッセージ インスタンスを生成できます。</span><span class="sxs-lookup"><span data-stu-id="23f8f-142">You can populate any field of the service content in the ASPX page with actual data to generate an actual message instance.</span></span>  
  
 <span data-ttu-id="23f8f-143">LOBWebApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) Web アプリケーションをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-143">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span> <span data-ttu-id="23f8f-144">LOBApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) デスクトップ アプリケーションをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="23f8f-144">You use the LOBApplication utility to simulate a line-of-business desktop application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f8f-145">参照</span><span class="sxs-lookup"><span data-stu-id="23f8f-145">See Also</span></span>  
 <span data-ttu-id="23f8f-146">[ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="23f8f-146">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="23f8f-147">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="23f8f-147">LOBApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)
