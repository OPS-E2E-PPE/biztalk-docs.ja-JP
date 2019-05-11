---
title: 手順 17:WSClient アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WSClient application
- message enrichment tutorial, WSClient application
- creating, WSClient application
ms.assetid: 2849cd4c-30d0-47ab-8161-fab379d5a548
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9238e94168060c8e8853bbd8108ae62a57397d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288846"
---
# <a name="step-17-create-the-wsclient-application"></a><span data-ttu-id="f9adb-102">手順 17:WSClient アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-102">Step 17: Create the WSClient Application</span></span>
<span data-ttu-id="f9adb-103">WSClient.exe (Web サービス クライアント) で記述されたコンソール アプリケーションは、[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]は、前の手順で Web サービスとして公開するオーケストレーションにデータを送信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9adb-103">WSClient.exe (Web service client) is a console application written in [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] that illustrates how to send data to the orchestration that you published as a Web service in the previous steps.</span></span> <span data-ttu-id="f9adb-104">WSClient アプリケーションは、4 つの入力の順序でパラメーターを受け取る: 患者名、ミドル ネーム、名、および社会保障番号の末尾をそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="f9adb-104">The WSClient application accepts four input parameters in order: patient first name, middle name, last name, and social security number, respectively.</span></span> <span data-ttu-id="f9adb-105">患者の情報を Web サービスを送信するには、次のコマンドライン構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-105">To send patient information to your Web service, use the following command line syntax:</span></span>  
  
```  
wsclient john henry smith 123456789  
```  
  
### <a name="to-create-the-wsclient-application"></a><span data-ttu-id="f9adb-106">WSClient アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="f9adb-106">To create the WSClient application</span></span>  
  
1. <span data-ttu-id="f9adb-107">ソリューション エクスプ ローラーで右クリックして**ソリューション 'BTAHL7V22Common'**、 をクリックして**追加**、 をクリックし、**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-107">In Solution Explorer, right-click **Solution 'BTAHL7V22Common'**, click **Add**, and then click **New Project**.</span></span>  
  
2. <span data-ttu-id="f9adb-108">**新しいプロジェクトの追加** ダイアログ ボックスで、**プロジェクトの種類**ウィンドウで、をクリックして**Visual c#** し、**テンプレート**ウィンドウで、をクリックします **。コンソール アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-108">In the **Add New Project** dialog box, in the **Project Types** pane, click **Visual C#** and in the **Templates** pane, click **Console Application**.</span></span>  
  
3. <span data-ttu-id="f9adb-109">**名前**フィールドに「 **WSClient**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-109">In the **Name** field, type **WSClient**.</span></span> <span data-ttu-id="f9adb-110">**場所**フィールドを参照 **\<*ドライブ*\>: \Tutorial**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-110">In the **Location** field, browse to **\<*drive*\>:\Tutorial**, and then click **OK**.</span></span> <span data-ttu-id="f9adb-111">ソリューション エクスプ ローラーがツリーに WSClient を追加し、Program.cs ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9adb-111">Solution Explorer adds WSClient to the tree, and the Program.cs file appears.</span></span>  
  
4. <span data-ttu-id="f9adb-112">ソリューション エクスプ ローラーで右クリックして**WSClient**、 をクリックし、 **Web 参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-112">In Solution Explorer, right-click **WSClient**, and then click **Add Web Reference**.</span></span>  
  
5. <span data-ttu-id="f9adb-113">[Web 参照の追加] ダイアログ ボックスで、**の Web サービス、ローカル マシン**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-113">In the Add Web Reference dialog box, click **Web services on the local machine**.</span></span> <span data-ttu-id="f9adb-114">ローカル コンピューターでは、利用可能な Web サービスを検索し、一覧で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9adb-114">The local computer searches for available Web services, and then displays them in a list.</span></span>  
  
6. <span data-ttu-id="f9adb-115">ローカル コンピューター上の Web サービスの一覧でクリックして**BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、 をクリックして**Operation_1**、順にクリックします**参照の追加**.</span><span class="sxs-lookup"><span data-stu-id="f9adb-115">In the list of Web Services on the Local Machine, click **BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, click **Operation_1**, and then click **Add Reference**.</span></span>  
  
7. <span data-ttu-id="f9adb-116">Program.cs をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9adb-116">Double-click Program.cs.</span></span>  
  
8. <span data-ttu-id="f9adb-117">次のコードをコピーし、[Program.cs] ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f9adb-117">Copy the following code and then paste it into the Program.cs window:</span></span>  
  
   ```  
   using System;  
  
   namespace WSClient  
   {  
      class Class1  
      {  
         [STAThread]  
         static void Main(string[] args)  
         {  
            try   
            {  
               localhost.DoorbellRoot req=new WSClient.localhost.DoorbellRoot();  
               req.FirstName=args[0];  
               req.MiddleName=args[1];  
               req.LastName=args[2];  
               req.SSN=args[3];  
               localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort sp=new WSClient.localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort();  
               sp.Operation_1(req);  
            }  
            catch (Exception ex)  
            {  
               Console.WriteLine(ex.Message);  
            }  
         }  
      }  
   }  
   ```  
  
9. <span data-ttu-id="f9adb-118">ソリューション エクスプ ローラーで右クリックして**WSClient**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-118">In Solution Explorer, right-click **WSClient**, and then click **Build**.</span></span> <span data-ttu-id="f9adb-119">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-119">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="f9adb-120">成功メッセージが表示されない場合のトラブルシューティングを行う**WSClient**します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-120">If no success message appears, troubleshoot **WSClient**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="f9adb-121">WSClient.exe、実行可能ファイルのコピーを配置、 \<*ドライブ*\>: \Tutorial\WSClient\bin\Debug フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f9adb-121">places a copy of the executable, WSClient.exe, into the \<*drive*\>:\Tutorial\WSClient\bin\Debug folder.</span></span>  
  
   <span data-ttu-id="f9adb-122">続行する[手順 18。新しいメッセージ強化ソリューションのテスト](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="f9adb-122">Proceed to [Step 18: Test Your New Message Enrichment Solution](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9adb-123">参照</span><span class="sxs-lookup"><span data-stu-id="f9adb-123">See Also</span></span>  
 [<span data-ttu-id="f9adb-124">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="f9adb-124">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)