---
title: 生成して、SharePoint サイトで MT MX フォームの発行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb32891ef9a8d78f032eececfab7644c6d5ae56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377651"
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a><span data-ttu-id="3f2a7-102">生成して、SharePoint サイトで MT/MX フォームの発行</span><span class="sxs-lookup"><span data-stu-id="3f2a7-102">Generating and Publishing MT/MX Forms on the SharePoint Site</span></span>
<span data-ttu-id="3f2a7-103">**生成し、SharePoint サイトで MT/MX フォームを公開します。**</span><span class="sxs-lookup"><span data-stu-id="3f2a7-103">**To generate and publish MT/MX forms on a SharePoint site:**</span></span>  

1. <span data-ttu-id="3f2a7-104">フォーム ジェネレーター ユーティリティをダウンロードし、ローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-104">Download the Form Generator Utility and save it locally on the computer.</span></span>  

2. <span data-ttu-id="3f2a7-105">開く、 **FormGenerator.sln**上記でダウンロードしたフォルダーから、ソリューションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-105">Open the **FormGenerator.sln** from the folder downloaded above and compile the solution.</span></span>  

3. <span data-ttu-id="3f2a7-106">コマンド プロンプトでコンパイルされた実行可能ファイル (FormGenerator.exe) のフォルダーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-106">At a command prompt, access the folder of compiled executable (FormGenerator.exe).</span></span> <span data-ttu-id="3f2a7-107">たとえば、デバッグ モードでユーティリティをビルドした場合にアクセス、 **.\bin\debug**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-107">For example, if you have built the utility in debug mode, access the **..\bin\debug** folder.</span></span>  

4. <span data-ttu-id="3f2a7-108">入力 FormGenerator.exe [-b] [-\<いいえ。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-108">Type FormGenerator.exe [-b] [-\<No.</span></span> <span data-ttu-id="3f2a7-109">テンプレート フォルダーのパスの\>]</span><span class="sxs-lookup"><span data-stu-id="3f2a7-109">of Template folder paths\>]</span></span>  

    <span data-ttu-id="3f2a7-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`.</span></span> <span data-ttu-id="3f2a7-111">パラメーターを新しく作成したフォルダーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-111">Replace the parameters with the newly-created folder names.</span></span>  

5. <span data-ttu-id="3f2a7-112">上記のコマンドでは、MX メッセージの修復に必要なエンベロープ スキーマも生成されます。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-112">The above command will also generate the Envelope schema needed for MX message repair.</span></span>  

6. <span data-ttu-id="3f2a7-113">出力フォルダーに移動して\<DestinationFolderPath\>します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-113">Go to output folder \<DestinationFolderPath\>.</span></span> <span data-ttu-id="3f2a7-114">\<DestinationFolderPath\>フォームを生成する InfoPath フォーム テンプレートのフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-114">In \<DestinationFolderPath\>, open the folder of the InfoPath form template for which you want to generate the form.</span></span> <span data-ttu-id="3f2a7-115">たとえば、MT103 InfoPath フォームを生成する場合は、DestinationFolderPath MT103 フォルダーを開くし、TemplateDS.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-115">For example, if you want to generate the MT103 InfoPath form, then open the MT103 folder at the DestinationFolderPath and open the TemplateDS.sln.</span></span>  

7. <span data-ttu-id="3f2a7-116">ソリューション エクスプ ローラーで、ダブルクリック、 **manifest.xsf**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-116">In the Solution Explorer, double click the **manifest.xsf**.</span></span> <span data-ttu-id="3f2a7-117">取得に開かれる時間のかかるが InfoPath フォームのデザインのファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-117">It will open the design file of the InfoPath form which will take some time to get opened.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3f2a7-118">MX メッセージの manifest.xsf は開く取得 2 ~ 5 分かかります。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-118">The MX messages manifest.xsf might take 2-5 minutes to get opened.</span></span>  

8. <span data-ttu-id="3f2a7-119">Manifest.xsf に移動**ツール、オプション フォーム - > セキュリティと信頼**メニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-119">In the manifest.xsf, go to **Tools ->Form Options-> Security and Trust** menu option.</span></span> <span data-ttu-id="3f2a7-120">チェック、**完全信頼**アクセス許可のオプションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-120">Check the **Full Trust** option must be enabled for the permission.</span></span>  

9. <span data-ttu-id="3f2a7-121">選択、**このフォーム テンプレートの署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-121">Select the **Sign this form Template** checkbox.</span></span> <span data-ttu-id="3f2a7-122">クリックして**証明書の選択**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-122">Click **Select certificate**.</span></span> <span data-ttu-id="3f2a7-123">これには、フォームに署名する証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-123">In this, select the certificate with which you want to sign the form.</span></span> <span data-ttu-id="3f2a7-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-124">Click **OK**.</span></span>  

10. <span data-ttu-id="3f2a7-125">保存**manifest.xsf**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-125">Save **manifest.xsf**.</span></span>  

11. <span data-ttu-id="3f2a7-126">移動して**ビューのデザイン タスクを ->** します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-126">Go to **View -> Design Tasks**.</span></span> <span data-ttu-id="3f2a7-127">デザイン タスク ウィンドウで、次のようにクリックします。**フォーム テンプレートの発行**オプション。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-127">On the Design Tasks pane, click **Publish Form Template** option.</span></span>  

12. <span data-ttu-id="3f2a7-128">発行ウィザード ウィンドウで、次のように選択します。**ネットワークの場所に** をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-128">In the publishing wizard window, select **To a network location** and click **Next**.</span></span>  

13. <span data-ttu-id="3f2a7-129">フォーム テンプレートのパスとファイル名 ボックスに、次のように入力します<strong>http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn</strong>と種類**\<MessageType\>** フォーム テンプレートの名前をテキスト ボックスと [] をクリック **[次へ]**。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-129">In the Form template path and file name textbox, type <strong>http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn</strong> and type **\<MessageType\>** in the Form Template name textbox and click **Next**.</span></span>  

14. <span data-ttu-id="3f2a7-130">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-130">Click **Next**.</span></span>  

15. <span data-ttu-id="3f2a7-131">クリックして**パブリッシュと閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-131">Click **Publish and close**.</span></span>  

16. <span data-ttu-id="3f2a7-132">Internet Explorer で SharePoint サイトを開いて **http://localhost/sites/bassite/templates**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-132">In the Internet Explorer, open your SharePoint site **http://localhost/sites/bassite/templates**.</span></span>  

17. <span data-ttu-id="3f2a7-133">をポイント **\<MessageType\>**、その横にある下矢印をクリックし、順にクリックして、**プロパティの編集**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-133">Point to **\<MessageType\>**, click the down arrow next to it, and then click **Edit Properties**.</span></span>  

18. <span data-ttu-id="3f2a7-134">テンプレート。\<MessageType\>ウィンドウで、[Namespace] ボックスで。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-134">In the Templates:\< MessageType\> window, in the Namespace box:</span></span>  

    - <span data-ttu-id="3f2a7-135">MT の InfoPath フォームを生成している場合に入力します。 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span><span class="sxs-lookup"><span data-stu-id="3f2a7-135">If you are generating MT InfoPath forms, type: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span></span>  

    - <span data-ttu-id="3f2a7-136">MX InfoPath フォームを生成している場合に入力します。 <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\></strong></span><span class="sxs-lookup"><span data-stu-id="3f2a7-136">If you are generating MX InfoPath forms, type: <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\></strong></span></span>  

       <span data-ttu-id="3f2a7-137">これは、対応するテンプレートを使用してメッセージ インスタンスを特定するに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-137">This will help in identifying the message instance with the corresponding template.</span></span>  

19. <span data-ttu-id="3f2a7-138">クリックして**を保存して閉じます**します。</span><span class="sxs-lookup"><span data-stu-id="3f2a7-138">Click **Save and Close**.</span></span>
