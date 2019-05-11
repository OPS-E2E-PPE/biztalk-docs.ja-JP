---
title: 手順 7:DoubleAction SDK サンプルのビルドと |Microsoft Docs
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
ms.openlocfilehash: 6ef2bee03470c6cf3792310467802e05628dd4b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280674"
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a><span data-ttu-id="c42bc-102">手順 7:DoubleAction SDK サンプルのビルドと</span><span class="sxs-lookup"><span data-stu-id="c42bc-102">Step 7: Building and Deploying the DoubleAction SDK Sample</span></span>
<span data-ttu-id="c42bc-103">DoubleAction.odx サンプルは、ダブル アクションの Partner Interface Process (Pip) の応答を自動的に生成するオーケストレーションを実装する方法を示しています。 0c2、0 C 4、3 a 2、3A4 とします。</span><span class="sxs-lookup"><span data-stu-id="c42bc-103">The DoubleAction.odx sample shows how to implement an orchestration to generate responses automatically for the double-action Partner Interface Processes (PIPs) 0C2, 0C4, 3A2, and 3A4.</span></span> <span data-ttu-id="c42bc-104">追加のダブル アクション Pip をサポートするには、このサンプル プロジェクトを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="c42bc-104">You can extend this sample project to support additional double-action PIPs.</span></span>  
  
 <span data-ttu-id="c42bc-105">Fabrikam が 4 つの Pip のいずれかを使用して、要求されるたびに、Fabrikam に自動的に応答を送信するのにには、このサンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-105">You use this sample to send a response automatically to Fabrikam whenever Fabrikam makes a request using any one of the four PIPs.</span></span>  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a><span data-ttu-id="c42bc-106">ビルドして初期化 DoubleAction サンプル</span><span class="sxs-lookup"><span data-stu-id="c42bc-106">To build and initialize the DoubleAction sample</span></span>  
  
1. <span data-ttu-id="c42bc-107">コマンド プロンプト ウィンドウで、Contoso のコンピューターには、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-107">On the Contoso computer, in a command prompt window, move to the following folder:</span></span>   
   <span data-ttu-id="c42bc-108">*\<ドライブ\>*: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\doubleaction\\します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-108">*\<drive\>*:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c42bc-109">セットアップ プログラムを実行する前に、メモ帳で DoubleAction.sql ファイル (上記のフォルダー) でを開きます。</span><span class="sxs-lookup"><span data-stu-id="c42bc-109">Before running the Setup program, open the DoubleAction.sql file (in the above folder) in Notepad.</span></span> <span data-ttu-id="c42bc-110">**ファイル** メニューのをクリックして**付けて**します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-110">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="c42bc-111">**エンコード**ボックスで、 **ANSI**クリックしてドロップダウン リストから**保存**します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-111">In the **Encoding** box, select **ANSI** from the drop-down list, and then click **Save**.</span></span> <span data-ttu-id="c42bc-112">をクリックして**はい**既存のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c42bc-112">Click **Yes** to overwrite the existing file.</span></span>  
  
2. <span data-ttu-id="c42bc-113">BizTalk Server のインストールが SQL Server 2008 R2 または 2008 SP1 を実行している場合は、同じフォルダーに setupx64.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-113">If your BizTalk Server installation is running on SQL Server 2008 R2/2008 SP1, run setupx64.bat in the same folder.</span></span> <span data-ttu-id="c42bc-114">バッチ ファイルでは、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c42bc-114">The batch file will perform the following actions:</span></span>  
  
   - <span data-ttu-id="c42bc-115">SQL ストアド プロシージャを作成します (`PipAutomationGetAction`)、アクション メッセージを MessagesToLOB テーブルから取得する、BTARNDATA データベースです。</span><span class="sxs-lookup"><span data-stu-id="c42bc-115">Creates a SQL stored procedure (`PipAutomationGetAction`) in the BTARNDATA database to retrieve the action message from the MessagesToLOB table.</span></span>  
  
   - <span data-ttu-id="c42bc-116">HeaderHelper .NET プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-116">Compiles the HeaderHelper .NET project and registers the assembly in the global assembly cache.</span></span>  
  
   - <span data-ttu-id="c42bc-117">作成し、バインド、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL 受信ポート (MessagesToLOB_Receive_Port)。</span><span class="sxs-lookup"><span data-stu-id="c42bc-117">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL receive port (MessagesToLOB_Receive_Port).</span></span>  
  
   - <span data-ttu-id="c42bc-118">受信場所 (MessagesToLOB_Receive_Location) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c42bc-118">Enables the receive location (MessagesToLOB_Receive_Location).</span></span>  
  
   - <span data-ttu-id="c42bc-119">コンパイルし、ダブル アクション PIPAutomation オーケストレーション (DoubleAction.odx) を展開します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-119">Compiles and deploys the double-action PIPAutomation orchestration (DoubleAction.odx).</span></span>  
  
   - <span data-ttu-id="c42bc-120">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをバインドして、開始します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-120">Binds and starts the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="c42bc-121">サンプルでは、コンパイル中にいくつかの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c42bc-121">The sample displays some warnings while compiling.</span></span> <span data-ttu-id="c42bc-122">これらの警告を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="c42bc-122">You can ignore these warnings.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="c42bc-123">DoubleAction.odx にバインドされていることを確認**MessagesToLOB_Receive_Port**オーケストレーションが開始されているとします。</span><span class="sxs-lookup"><span data-stu-id="c42bc-123">Verify that DoubleAction.odx has been bound to **MessagesToLOB_Receive_Port**, and that the orchestration has been started.</span></span>  
  
3. <span data-ttu-id="c42bc-124">BizTalk Server 管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1**ノード。</span><span class="sxs-lookup"><span data-stu-id="c42bc-124">In BizTalk Server Administration Console, expand the **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span> <span data-ttu-id="c42bc-125">をクリックして、**オーケストレーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="c42bc-125">Click the **Orchestrations** node.</span></span> <span data-ttu-id="c42bc-126">右クリックし、 **DoubleAction**オーケストレーション、およびクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-126">Right-click the **DoubleAction** orchestration, and then click **Properties**.</span></span> <span data-ttu-id="c42bc-127">[プロパティ] ダイアログ ボックスで、**バインド**ノード、および設定して、**ホスト**に **[biztalkserverapplication]** 設定と、**受信ポート**に **[messagetolob_receiveport]** します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-127">In the Properties dialog box, click the **Bindings** node, and then set the **Host** to **BizTalkServerApplication** and set the **Receive Port** to **MessageToLOB_ReceivePort**.</span></span> <span data-ttu-id="c42bc-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c42bc-128">Click **OK**.</span></span> <span data-ttu-id="c42bc-129">右クリックし、 **DoubleAction**オーケストレーション、およびクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="c42bc-129">Right-click the **DoubleAction** orchestration, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42bc-130">参照</span><span class="sxs-lookup"><span data-stu-id="c42bc-130">See Also</span></span>  
 [<span data-ttu-id="c42bc-131">Fabrikam ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="c42bc-131">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)