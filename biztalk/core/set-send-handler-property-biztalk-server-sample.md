---
title: "送信ハンドラ プロパティ (BizTalk Server サンプル) を設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- send handlers, properties
ms.assetid: eb6ae2f2-528f-44ec-bca4-f37006893ff2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0e14f58cbdd07a8c13dec6cd44fbc95584f2ecc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="set-send-handler-property-biztalk-server-sample"></a><span data-ttu-id="c757b-102">送信ハンドラー プロパティ (BizTalk Server サンプル) を設定します。</span><span class="sxs-lookup"><span data-stu-id="c757b-102">Set Send Handler Property (BizTalk Server Sample)</span></span>
<span data-ttu-id="c757b-103">送信ハンドラ プロパティの設定のサンプルでは、簡易メール送信プロトコル (SMTP) 送信ハンドラの XML 構成情報を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c757b-103">The Set Send Handler Property sample demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c757b-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c757b-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="c757b-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c757b-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="c757b-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="c757b-106">What This Sample Does</span></span>  
 <span data-ttu-id="c757b-107">このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c757b-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="c757b-108">送信ハンドラ名が指定されていることを前提として、クエリを実行し、一致する送信ハンドラの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c757b-108">Given a send handler name, query for a list of matching send handlers.</span></span>  
  
-   <span data-ttu-id="c757b-109">SMTP 送信ハンドラの XML 構成情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="c757b-109">Set the XML configuration information for an SMTP send handler.</span></span>  
  
-   <span data-ttu-id="c757b-110">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="c757b-110">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="c757b-111">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="c757b-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="c757b-112">このサンプル ファイルは、次の SDK の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="c757b-112">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="c757b-113">\<*パスのサンプル*> \Admin\WMI\Set 送信ハンドラー Property\\</span><span class="sxs-lookup"><span data-stu-id="c757b-113">\<*Samples Path*>\Admin\WMI\Set Send Handler Property\\</span></span>  
  
 <span data-ttu-id="c757b-114">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="c757b-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="c757b-115">ファイル</span><span class="sxs-lookup"><span data-stu-id="c757b-115">File(s)</span></span>|<span data-ttu-id="c757b-116">Description</span><span class="sxs-lookup"><span data-stu-id="c757b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c757b-117">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="c757b-117">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="c757b-118">ConfigureSMTP.vbs</span><span class="sxs-lookup"><span data-stu-id="c757b-118">ConfigureSMTP.vbs</span></span>|<span data-ttu-id="c757b-119">SMTP 送信ハンドラと差出人の電子メール アドレスを指定するパラメータを取る VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="c757b-119">VBScript file that takes parameters that specify an SMTP send handler and a From e-mail address.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="c757b-120">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="c757b-120">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="c757b-121">送信ハンドラ プロパティの設定のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c757b-121">The Set Send Handler Property sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="c757b-122">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="c757b-122">Running This Sample</span></span>  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a><span data-ttu-id="c757b-123">送信ハンドラ プロパティの設定のサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="c757b-123">To run the Set Send Handler Property sample</span></span>  
  
1.  <span data-ttu-id="c757b-124">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c757b-124">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="c757b-125">\<*パスのサンプル*> \Admin\WMI\Set 送信ハンドラー Property\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="c757b-125">\<*Samples Path*>\Admin\WMI\Set Send Handler Property\VBScript\\</span></span>  
  
2.  <span data-ttu-id="c757b-126">cscript プログラムを使用し、次のコマンド ライン引数を渡して、ファイル ConfigureSMTP.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="c757b-126">Run the file ConfigureSMTP.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
    -   **\<**   
         <span data-ttu-id="c757b-127">***SMTPServerName* >。**</span><span class="sxs-lookup"><span data-stu-id="c757b-127">***SMTPServerName* >.**</span></span> <span data-ttu-id="c757b-128">メールの送信に使用する SMTP サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c757b-128">The name of the SMTP server that will be used to send mail.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="c757b-129">***FromEmailAddress* >。**</span><span class="sxs-lookup"><span data-stu-id="c757b-129">***FromEmailAddress* >.**</span></span> <span data-ttu-id="c757b-130">差出人のアドレスに使用される電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="c757b-130">An e-mail address that will be used as the From address.</span></span>  
  
         <span data-ttu-id="c757b-131">例:</span><span class="sxs-lookup"><span data-stu-id="c757b-131">For example:</span></span>  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a><span data-ttu-id="c757b-132">コメント</span><span class="sxs-lookup"><span data-stu-id="c757b-132">Comments</span></span>  
 <span data-ttu-id="c757b-133">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。</span><span class="sxs-lookup"><span data-stu-id="c757b-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="c757b-134">スクリプト ファイル ConfigureSMTP.vbs には、実行する操作についての説明のある詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c757b-134">The script file ConfigureSMTP.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="c757b-135">詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。</span><span class="sxs-lookup"><span data-stu-id="c757b-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c757b-136">参照</span><span class="sxs-lookup"><span data-stu-id="c757b-136">See Also</span></span>  
 [<span data-ttu-id="c757b-137">管理 WMI (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="c757b-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)