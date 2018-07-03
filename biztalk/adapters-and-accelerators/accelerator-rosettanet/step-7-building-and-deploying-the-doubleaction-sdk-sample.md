---
title: '手順 7: ビルドと DoubleAction SDK サンプルの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- deploying, solutions
- building solutions
- double action tutorial, deploying solutions
ms.assetid: f67f8aee-1004-48ee-a6fd-881097382888
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c4664210cf4911f180b44b470db01aa2948531f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998675"
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a><span data-ttu-id="77398-102">手順 7: ビルドと DoubleAction SDK サンプルの展開</span><span class="sxs-lookup"><span data-stu-id="77398-102">Step 7: Building and Deploying the DoubleAction SDK Sample</span></span>
<span data-ttu-id="77398-103">DoubleAction.odx サンプルでは、オーケストレーションを実装し、ダブル アクションの PIP (Partner Interface Process) である 0C2、0C4、3A2、および 3A40 に対する応答を自動的に生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="77398-103">The DoubleAction.odx sample shows how to implement an orchestration to generate responses automatically for the double-action Partner Interface Processes (PIPs) 0C2, 0C4, 3A2, and 3A4.</span></span> <span data-ttu-id="77398-104">このサンプル プロジェクトを拡張し、さらに多くのダブルアクション PIP をサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="77398-104">You can extend this sample project to support additional double-action PIPs.</span></span>  
  
 <span data-ttu-id="77398-105">このサンプルを使用すると、Fabrikam が 4 つの PIP のいずれかを使用して要求を行ったときに、自動的に Fabrikam に応答が送信されます。</span><span class="sxs-lookup"><span data-stu-id="77398-105">You use this sample to send a response automatically to Fabrikam whenever Fabrikam makes a request using any one of the four PIPs.</span></span>  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a><span data-ttu-id="77398-106">DoubleAction サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="77398-106">To build and initialize the DoubleAction sample</span></span>  
  
1. <span data-ttu-id="77398-107">Contoso コンピューターのコマンド プロンプト ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="77398-107">On the Contoso computer, in a command prompt window, move to the following folder:</span></span>   
   <span data-ttu-id="77398-108">*\<ドライブ\>*: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\doubleaction\\します。</span><span class="sxs-lookup"><span data-stu-id="77398-108">*\<drive\>*:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="77398-109">セットアップ プログラムを実行する前に、メモ帳で DoubleAction.sql ファイル (上のフォルダーに置かれています) を開きます。</span><span class="sxs-lookup"><span data-stu-id="77398-109">Before running the Setup program, open the DoubleAction.sql file (in the above folder) in Notepad.</span></span> <span data-ttu-id="77398-110">**ファイル** メニューのをクリックして**付けて**します。</span><span class="sxs-lookup"><span data-stu-id="77398-110">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="77398-111">**エンコード**ボックスで、 **ANSI**クリックしてドロップダウン リストから**保存**します。</span><span class="sxs-lookup"><span data-stu-id="77398-111">In the **Encoding** box, select **ANSI** from the drop-down list, and then click **Save**.</span></span> <span data-ttu-id="77398-112">をクリックして**はい**既存のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="77398-112">Click **Yes** to overwrite the existing file.</span></span>  
  
2. <span data-ttu-id="77398-113">BizTalk Server のインストールが SQL Server 2008 R2 または 2008 SP1 を実行している場合は、同じフォルダーに setupx64.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="77398-113">If your BizTalk Server installation is running on SQL Server 2008 R2/2008 SP1, run setupx64.bat in the same folder.</span></span> <span data-ttu-id="77398-114">バッチ ファイルによって、次の処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="77398-114">The batch file will perform the following actions:</span></span>  
  
   - <span data-ttu-id="77398-115">BTARNDATA データベースに、MessagesToLOB テーブルからアクション メッセージを取得する SQL ストアド プロシージャ (`PipAutomationGetAction`) を作成します。</span><span class="sxs-lookup"><span data-stu-id="77398-115">Creates a SQL stored procedure (`PipAutomationGetAction`) in the BTARNDATA database to retrieve the action message from the MessagesToLOB table.</span></span>  
  
   - <span data-ttu-id="77398-116">HeaderHelper .NET プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="77398-116">Compiles the HeaderHelper .NET project and registers the assembly in the global assembly cache.</span></span>  
  
   - <span data-ttu-id="77398-117">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL 受信ポート (MessagesToLOB_Receive_Port) を作成し、バインドします。</span><span class="sxs-lookup"><span data-stu-id="77398-117">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL receive port (MessagesToLOB_Receive_Port).</span></span>  
  
   - <span data-ttu-id="77398-118">受信場所 (MessagesToLOB_Receive_Location) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="77398-118">Enables the receive location (MessagesToLOB_Receive_Location).</span></span>  
  
   - <span data-ttu-id="77398-119">コンパイルし、ダブル アクション PIPAutomation オーケストレーション (DoubleAction.odx) を展開します。</span><span class="sxs-lookup"><span data-stu-id="77398-119">Compiles and deploys the double-action PIPAutomation orchestration (DoubleAction.odx).</span></span>  
  
   - <span data-ttu-id="77398-120">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをバインドして、開始します。</span><span class="sxs-lookup"><span data-stu-id="77398-120">Binds and starts the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="77398-121">コンパイル中に警告がいくつか表示されます。</span><span class="sxs-lookup"><span data-stu-id="77398-121">The sample displays some warnings while compiling.</span></span> <span data-ttu-id="77398-122">これらの警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="77398-122">You can ignore these warnings.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="77398-123">DoubleAction.odx にバインドされていることを確認**MessagesToLOB_Receive_Port**オーケストレーションが開始されているとします。</span><span class="sxs-lookup"><span data-stu-id="77398-123">Verify that DoubleAction.odx has been bound to **MessagesToLOB_Receive_Port**, and that the orchestration has been started.</span></span>  
  
3. <span data-ttu-id="77398-124">BizTalk Server 管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1**ノード。</span><span class="sxs-lookup"><span data-stu-id="77398-124">In BizTalk Server Administration Console, expand the **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span> <span data-ttu-id="77398-125">をクリックして、**オーケストレーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="77398-125">Click the **Orchestrations** node.</span></span> <span data-ttu-id="77398-126">右クリックし、 **DoubleAction**オーケストレーション、およびクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="77398-126">Right-click the **DoubleAction** orchestration, and then click **Properties**.</span></span> <span data-ttu-id="77398-127">[プロパティ] ダイアログ ボックスで、**バインド**ノード、および設定して、**ホスト**に **[biztalkserverapplication]** 設定と、**受信ポート**に **[messagetolob_receiveport]** します。</span><span class="sxs-lookup"><span data-stu-id="77398-127">In the Properties dialog box, click the **Bindings** node, and then set the **Host** to **BizTalkServerApplication** and set the **Receive Port** to **MessageToLOB_ReceivePort**.</span></span> <span data-ttu-id="77398-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77398-128">Click **OK**.</span></span> <span data-ttu-id="77398-129">右クリックし、 **DoubleAction**オーケストレーション、およびクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="77398-129">Right-click the **DoubleAction** orchestration, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77398-130">参照</span><span class="sxs-lookup"><span data-stu-id="77398-130">See Also</span></span>  
 [<span data-ttu-id="77398-131">Fabrikam ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="77398-131">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)