---
title: "厳密な名前のアセンブリ キー ファイルを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5778a8ec-f5f7-4ae1-a57e-99f6503f044c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec807cf6b596f7e89f607ebeb56700c59134c211
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="68ff9-102">厳密な名前のアセンブリ キー ファイルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="68ff9-102">How to Configure a Strong Name Assembly Key File</span></span>
<span data-ttu-id="68ff9-103">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] では、BizTalk ソリューションを展開するプロセスで、まずアセンブリのビルドが行われます。</span><span class="sxs-lookup"><span data-stu-id="68ff9-103">In the process of deploying a BizTalk solution, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] first builds the assemblies.</span></span> <span data-ttu-id="68ff9-104">このとき各アセンブリは、厳密に署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="68ff9-104">The deployment process requires that each assembly is strongly signed.</span></span> <span data-ttu-id="68ff9-105">厳密な名前のアセンブリ キー ファイルとプロジェクトを関連付けることによって、アセンブリを厳密署名できます。</span><span class="sxs-lookup"><span data-stu-id="68ff9-105">You can strongly sign your assemblies by associating the project with a strong name assembly key file.</span></span> <span data-ttu-id="68ff9-106">まだ行っていない場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からソリューションを展開する前に、次の手順に従って、厳密な名前のアセンブリ キー ファイルを生成し、ソリューション内の各プロジェクトに割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="68ff9-106">If you haven't already done so, before deploying a solution from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], use the following procedure to generate a strong name assembly key file and assign it to each project in the solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="68ff9-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="68ff9-107">Prerequisites</span></span>  
 <span data-ttu-id="68ff9-108">このトピックの手順を実行する必要がありますログインする必要がのメンバーであるアカウントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者のグループです。</span><span class="sxs-lookup"><span data-stu-id="68ff9-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrator's group.</span></span> <span data-ttu-id="68ff9-109">また、使用するアカウントには、グローバル アセンブリ キャッシュ (GAC) に対する書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="68ff9-109">In addition, your account must have Write permissions on the global assembly cache (GAC).</span></span> <span data-ttu-id="68ff9-110">ローカル コンピューターの管理者アカウントには、このアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="68ff9-110">The Administrators account on the local computer has this permission.</span></span>  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="68ff9-111">厳密な名前のアセンブリ キー ファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="68ff9-111">To configure a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="68ff9-112">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="68ff9-112">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="68ff9-113">コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="68ff9-113">At the command prompt, from the folder where you want to store the key file, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="68ff9-114">**sn/k***file_name* **.snk** </span><span class="sxs-lookup"><span data-stu-id="68ff9-114">**sn /k**  *file_name* **.snk**</span></span>  
  
     <span data-ttu-id="68ff9-115">例: **sn/k ErrorHandling.snk**</span><span class="sxs-lookup"><span data-stu-id="68ff9-115">Example: **sn /k ErrorHandling.snk**</span></span>  
  
     <span data-ttu-id="68ff9-116">確認メッセージを**キーのペアに書き込まれる** \< *file_name*\>**.snk** `,`コマンド ラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="68ff9-116">A confirmation message, **Key pair written to** \<*file_name*\>**.snk**`,` displays on the command line.</span></span>  
  
3.  <span data-ttu-id="68ff9-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、プロジェクトを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="68ff9-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the project and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="68ff9-118">をクリックして、**署名**タブを選び**参照**で、**厳密な名前キー ファイルを選択して**ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="68ff9-118">Click the **Signing** tab and choose **Browse** in the **Choose a strong name key file** drop down box.</span></span>  
  
5.  <span data-ttu-id="68ff9-119">キー ファイルを参照してクリックします。</span><span class="sxs-lookup"><span data-stu-id="68ff9-119">Browse to the key file and click it.</span></span> <span data-ttu-id="68ff9-120">をクリックして**開く**、プロジェクトのプロパティを閉じます。</span><span class="sxs-lookup"><span data-stu-id="68ff9-120">Click **Open**, and then close the project properties.</span></span>  
  
6.  <span data-ttu-id="68ff9-121">この厳密な名前のアセンブリ キー ファイルを使用して展開するソリューション内のプロジェクトごとに、手順 3. ～ 6. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="68ff9-121">Repeat steps 3 through 6 for each project in the solution that you want to deploy using this strong name assembly key file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ff9-122">参照</span><span class="sxs-lookup"><span data-stu-id="68ff9-122">See Also</span></span>  
 [<span data-ttu-id="68ff9-123">Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="68ff9-123">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)