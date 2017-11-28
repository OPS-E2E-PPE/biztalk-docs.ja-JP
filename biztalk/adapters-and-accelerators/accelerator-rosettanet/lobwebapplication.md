---
title: "LOBWebApplication |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b00e29b51eac2c58ac7843cca75994efceb4085
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lobwebapplication"></a><span data-ttu-id="fc905-102">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="fc905-102">LOBWebApplication</span></span>
<span data-ttu-id="fc905-103">LOBWebApplication ユーティリティは、実際の基幹業務 (LOB) Web アプリケーションをシミュレートして、ASPX ページから取引先にアクションまたは応答メッセージを送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="fc905-103">You use the LOBWebApplication utility to submit an action or response message from an ASPX page to a trading partner, simulating an actual line-of-business Web application.</span></span>  
  
 <span data-ttu-id="fc905-104">ASPX ページをセットアップした後、ページを起動してメッセージのパラメーター (ホーム組織と取引先組織、PIP コード、PIP バージョン、PIP インスタンス ID、およびメッセージ カテゴリ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc905-104">After you have set up the ASPX page, you start the page, and enter the parameters for a message: the home and partner organizations; the PIP code, version, and instance ID; and the message category.</span></span> <span data-ttu-id="fc905-105">その後、サービス コンテンツを変更してメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="fc905-105">You can then modify the service content, and submit the message.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="fc905-106">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="fc905-106">Location in SDK</span></span>  
 <span data-ttu-id="fc905-107">\<*ドライブ*> \Program Files\Microsoft BizTalk 2013 Accelerator for rosettanet \sdk\lobwebapplication</span><span class="sxs-lookup"><span data-stu-id="fc905-107">\<*drive*>\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication</span></span>  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a><span data-ttu-id="fc905-108">LOBWebApplication 用の仮想サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="fc905-108">Adding a Virtual Server for LOBWebApplication</span></span>  
  
#### <a name="to-add-a-virtual-server"></a><span data-ttu-id="fc905-109">仮想サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="fc905-109">To add a virtual server</span></span>  
  
1.  <span data-ttu-id="fc905-110">をクリックして**開始**、 をポイント**シリアルキー**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="fc905-110">Click **Start**, point to **AllPrograms**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="fc905-111">インフォメーション サービス マネージャで、展開**\<コンピューター名 > (ローカル コンピューター)**、展開**Web サイト**、し、右クリックし、**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-111">In Information Services Manager, expand **\<Computer name> (local computer)**, expand **Web Sites**, and then right-click **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="fc905-112">をポイント**新規**、クリックして**仮想ディレクトリ**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-112">Point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="fc905-113">**仮想ディレクトリの作成ウィザード** ページで、をクリックして**次**など、サイトのエイリアスを入力し、 **LOBWebApplication**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-113">On the **Virtual Directory Creation Wizard** page, click **Next**, and then type an alias for the site, such as **LOBWebApplication**.</span></span>  
  
5.  <span data-ttu-id="fc905-114">**Web サイトのコンテンツのディレクトリ** ページで **参照**に移動\<*ドライブ*> \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication、 をクリックして**OK**、クリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-114">On the **Web Site Content Directory** page, click **Browse**, move to \<*drive*>\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication, click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="fc905-115">**仮想ディレクトリのアクセス許可**] ページで、[**読み取り**と**スクリプトを実行する**、順にクリック**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-115">On the **Virtual Directory Access Permissions** page, select **Read** and **Run scripts**, and then click **Next**.</span></span> <span data-ttu-id="fc905-116">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc905-116">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="fc905-117">BTARN を構成するために使用するサービス アカウント ユーザー (hostsvc など) を STS_WPG に追加します。</span><span class="sxs-lookup"><span data-stu-id="fc905-117">Add the service account user that was used to configure BTARN, for example, hostsvc, to the STS_WPG.</span></span>  
  
8.  <span data-ttu-id="fc905-118">C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files にあるファイルをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="fc905-118">Delete all files from C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files.</span></span> <span data-ttu-id="fc905-119">ファイルを削除する前に、iisreset プログラムを実行してファイルのロックを解除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc905-119">You may have to run the iisreset program to unlock the files before you can delete them.</span></span>  
  
9. <span data-ttu-id="fc905-120">IIS マネージャーで、アプリケーション プール BTARNHTTPReceivePool の下で実行するように LOBWebApplication を設定します。</span><span class="sxs-lookup"><span data-stu-id="fc905-120">In IIS Manager, set the LOBWebApplication to run under the Application Pool BTARNHTTPReceivePool.</span></span>  
  
10. <span data-ttu-id="fc905-121">IIS マネージャーを使用して、LOBWebApplication ユーティリティの [Directory Security Properties] セクションで、仮想ディレクトリを匿名で実行するオプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="fc905-121">In IIS Manager, in the Directory Security Properties section for the LOBWebApplication utility, disable the option for the virtual directory to run as anonymous.</span></span>  
  
## <a name="building-lobwebapplication"></a><span data-ttu-id="fc905-122">LOBWebApplication の構築</span><span class="sxs-lookup"><span data-stu-id="fc905-122">Building LOBWebApplication</span></span>  
  
#### <a name="to-build-lobwebapplication"></a><span data-ttu-id="fc905-123">LOBWebApplication を構築するには</span><span class="sxs-lookup"><span data-stu-id="fc905-123">To build LOBWebApplication</span></span>  
  
1.  <span data-ttu-id="fc905-124">[!INCLUDE[vs2012](../../includes/vs2012-md.md)]を起動します。</span><span class="sxs-lookup"><span data-stu-id="fc905-124">Start [!INCLUDE[vs2012](../../includes/vs2012-md.md)].</span></span>  
  
2.  <span data-ttu-id="fc905-125">**ファイル**、 をポイント**開く**、順にクリック**ソリューションを開く**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-125">On the **File**, point to **Open**, and then click **Open Solution**.</span></span>  
  
3.  <span data-ttu-id="fc905-126">移動\<*ドライブ*> \Program Files\Microsoft BizTalk 2013 Accelerator for rosettanet \sdk\lobwebapplication、選択**LOBWebApplication.sln**、クリックして**開いている**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-126">Move to \<*drive*>\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication, select **LOBWebApplication.sln**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fc905-127">LOBWebApplication 用の仮想サーバーを追加していない場合、ソリューションは [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で正常に開きません。</span><span class="sxs-lookup"><span data-stu-id="fc905-127">If you have not added a virtual server for LOBWebApplication, the solution will not open correctly in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="fc905-128">右クリック**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-128">Right-click **References**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="fc905-129">**参照の追加**ダイアログ ボックスで、をクリックして**参照**に移動\<*ドライブ*>: \Program Files\Microsoft BizTalk 2013 Accelerator for rosettanet \binMicrosoft.Solutions.BTARN.ConfigurationManager.dll および Microsoft.Solutions.BTARN.Shared.dll ファイルを選択し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-129">In the **Add Reference** dialog box, click **Browse**, move to \<*drive*>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\Bin, select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll files, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="fc905-130">右クリック**LOBWebApplication**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-130">Right-click **LOBWebApplication**, and then click **Build**.</span></span>  
  
## <a name="running-lobwebapplication"></a><span data-ttu-id="fc905-131">LOBWebApplication の実行</span><span class="sxs-lookup"><span data-stu-id="fc905-131">Running LOBWebApplication</span></span>  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a><span data-ttu-id="fc905-132">LOBWebApplication を実行してメッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="fc905-132">To run LOBWebApplication and submit a message</span></span>  
  
1.  <span data-ttu-id="fc905-133">をクリックして**開始**、 をポイント**すべてのプログラム**、順にクリック**Internet Explorer**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-133">Click **Start**, point to **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="fc905-134">Internet Explorer での**アドレス**ボックスに、http://localhost/LOBWebApplication を入力し、をクリックして**移動**です。</span><span class="sxs-lookup"><span data-stu-id="fc905-134">In Internet Explorer, in the **Address** box, type http://localhost/LOBWebApplication, and then click **Go**.</span></span>  
  
3.  <span data-ttu-id="fc905-135">**Submit Message**  ダイアログ ボックスで、ホーム組織、取引先組織、PIP コード、PIP バージョン、PIP インスタンス ID、およびメッセージ カテゴリを入力します。</span><span class="sxs-lookup"><span data-stu-id="fc905-135">In the **Submit Message** dialog box, type the home organization, the partner organization, the PIP code, the PIP version, the PIP Instance ID, and the message category.</span></span>  
  
4.  <span data-ttu-id="fc905-136">必要に応じてサービス コンテンツを変更します。</span><span class="sxs-lookup"><span data-stu-id="fc905-136">Modify the service content as needed.</span></span>  
  
5.  <span data-ttu-id="fc905-137">**[送信]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc905-137">Click **Submit**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc905-138">解説</span><span class="sxs-lookup"><span data-stu-id="fc905-138">Remarks</span></span>  
 <span data-ttu-id="fc905-139">LOBWebApplication ユーティリティは、指定した PIP からメッセージのインスタンスを生成し、ASPX ページに生成されたメッセージのインスタンスからサービスのコンテンツを入力します。</span><span class="sxs-lookup"><span data-stu-id="fc905-139">The LOBWebApplication utility generates an instance of the message from the specified PIP, and enters service content from the generated message instance into the ASPX page.</span></span> <span data-ttu-id="fc905-140">この処理を実行する際、LOBWebApplication ユーティリティは、書式設定されたメッセージ インスタンスを PIP から直接生成するのと同じ技法を使用します。</span><span class="sxs-lookup"><span data-stu-id="fc905-140">To do this, the utility uses the same technique that it uses to generate a well-formed message instance directly from a PIP.</span></span> <span data-ttu-id="fc905-141">詳細については、次を参照してください。 [PIP からの整形式メッセージ インスタンスを作成する](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md)です。</span><span class="sxs-lookup"><span data-stu-id="fc905-141">For more information, see [Creating a Well-Formed Message Instance from a PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md).</span></span> <span data-ttu-id="fc905-142">ASPX ページのサービス コンテンツのフィールドに実際のデータを入力すると、実際のメッセージ インスタンスを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fc905-142">You can populate any field of the service content in the ASPX page with actual data to generate an actual message instance.</span></span>  
  
 <span data-ttu-id="fc905-143">LOBWebApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) Web アプリケーションをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="fc905-143">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span> <span data-ttu-id="fc905-144">LOBApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) デスクトップ アプリケーションをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="fc905-144">You use the LOBApplication utility to simulate a line-of-business desktop application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc905-145">参照</span><span class="sxs-lookup"><span data-stu-id="fc905-145">See Also</span></span>  
 <span data-ttu-id="fc905-146">[ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="fc905-146">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="fc905-147">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="fc905-147">LOBApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)