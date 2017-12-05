---
title: "VisualStudioHostRestart (アプリケーションの展開サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d98a3a5e497a4476de897c8008f3a9976812209a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a><span data-ttu-id="b0c51-102">VisualStudioHostRestart (アプリケーションの展開サンプル)</span><span class="sxs-lookup"><span data-stu-id="b0c51-102">VisualStudioHostRestart (Application Deployment Sample)</span></span>
<span data-ttu-id="b0c51-103">このトピックでは、ローカル コンピュータの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で実行しているホスト インスタンスを再起動するための VisualStudioHostRestart サンプル スクリプトを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0c51-103">This topic explains how to use the VisualStudioHostRestart sample script to restart a host instance running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="b0c51-104">このスクリプトは、Visual Studio にアセンブリを再展開するときに使用できます。これにより、BizTalk Server ランタイムに変更内容がすぐに反映されます。</span><span class="sxs-lookup"><span data-stu-id="b0c51-104">You can use this script when redeploying assemblies in Visual Studio so that the BizTalk Server runtime immediately picks up the changes.</span></span> <span data-ttu-id="b0c51-105">また、プロジェクトの展開のプロパティで設定できるオプションを使用して、ホスト インスタンスを再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c51-105">Alternatively, you can use the option to restart host instances, which you can set in Deployment properties for the project.</span></span> <span data-ttu-id="b0c51-106">詳細については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0c51-106">For more information, see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b0c51-107">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="b0c51-107">What This Sample Does</span></span>  
 <span data-ttu-id="b0c51-108">このサンプル スクリプトは、次の処理を順番に実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c51-108">This sample script performs the following actions, in order:</span></span>  
  
1.  <span data-ttu-id="b0c51-109">ローカル コンピュータのすべてのインプロセス ホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="b0c51-109">Stops all in-process host instances on the local computer.</span></span>  
  
2.  <span data-ttu-id="b0c51-110">ローカル コンピュータのすべてのインプロセス ホスト インスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b0c51-110">Starts all in-process host instances on the local computer.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b0c51-111">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="b0c51-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="b0c51-112">サンプルにありますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のように、インストール フォルダー: *\<サンプル パス\>*\Application Deployment\VisualStudioHostRestart です。</span><span class="sxs-lookup"><span data-stu-id="b0c51-112">The sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder, as follows: *\<Samples path\>*\Application Deployment\VisualStudioHostRestart.</span></span>  
  
 <span data-ttu-id="b0c51-113">サンプルには、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0c51-113">The sample includes the following file:</span></span>  
  
-   <span data-ttu-id="b0c51-114">RestartBizTalkHostInstances.vbs</span><span class="sxs-lookup"><span data-stu-id="b0c51-114">RestartBizTalkHostInstances.vbs</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="b0c51-115">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="b0c51-115">How to Use This Sample</span></span>  
 <span data-ttu-id="b0c51-116">次の手順に従って、このサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c51-116">Use the following procedures to run this sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="b0c51-117">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="b0c51-117">To run the sample</span></span>  
  
-   <span data-ttu-id="b0c51-118">RestartBizTalkHostInstances.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c51-118">Run RestartBizTalkHostInstances.vbs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c51-119">参照</span><span class="sxs-lookup"><span data-stu-id="b0c51-119">See Also</span></span>  
 <span data-ttu-id="b0c51-120">[アプリケーションの展開 (BizTalk Server Samples フォルダ)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="b0c51-120">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 <span data-ttu-id="b0c51-121">[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="b0c51-121">[Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="b0c51-122">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="b0c51-122">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)