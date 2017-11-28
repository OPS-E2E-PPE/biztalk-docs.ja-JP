---
title: "レッスン 8: のビルドと、アセンブリの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6f043764dba966d662274d47643e01bec3735a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a><span data-ttu-id="81bb5-102">レッスン 8: のビルドと、アセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="81bb5-102">Lesson 8: Building and Deploying the Assembly</span></span>
<span data-ttu-id="81bb5-103">このレッスンでは、ビルドし、前の手順で作成したパイプラインを含むアセンブリを生成するパイプライン プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="81bb5-103">In this lesson, you build and deploy the pipeline project to generate an assembly that contains the pipelines you created in the previous steps.</span></span> <span data-ttu-id="81bb5-104">このレッスンは、これまでに作成した作業ではコンパイル エラーがないようにします。</span><span class="sxs-lookup"><span data-stu-id="81bb5-104">This lesson ensures there are no compilation errors in the work you have created so far.</span></span>  
  
 <span data-ttu-id="81bb5-105">保存して、プロジェクトをコンパイルしてアセンブリ (DLL) ファイル、 \<*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="81bb5-105">You compile the project into an assembly (DLL) file and save it in the \<*drive*>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="81bb5-106">プロジェクトをビルドして展開するには</span><span class="sxs-lookup"><span data-stu-id="81bb5-106">To build and deploy the project</span></span>  
  
1.  <span data-ttu-id="81bb5-107">ソリューション エクスプ ローラーで右クリック**SWIFTPipelines**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-107">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81bb5-108">コンパイル プロセス中に表示しないようにすべてのエラーです。</span><span class="sxs-lookup"><span data-stu-id="81bb5-108">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="81bb5-109">場合は、エラーの原因を確認して修正して、プロジェクトを再構築します。</span><span class="sxs-lookup"><span data-stu-id="81bb5-109">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="81bb5-110">A4SWIFT のパイプライン コンポーネントに関連する警告の数を参照してください、ただし、します。</span><span class="sxs-lookup"><span data-stu-id="81bb5-110">You may, however, see a number of warnings related to the A4SWIFT pipeline components.</span></span> <span data-ttu-id="81bb5-111">これらの警告を設定して、引き起こす状況を修正することができます、**ローカル コピー** 、パイプライン コンポーネントへの参照のプロパティ**False**です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-111">You can correct the condition leading to these warnings by setting the **Copy Local** properties of the pipeline component references to **False**.</span></span> <span data-ttu-id="81bb5-112">詳細についてを参照してください「パイプライン プロジェクトをビルドすることがありますで警告を表示」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-112">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  
  
2.  <span data-ttu-id="81bb5-113">SWIFTPipelines.dll の作成を検証するファイルを使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、[参照] \<*ドライブ*: > \labs\SWIFTProject\SWIFTPipelines\bin\Development、このフォルダーにファイルが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="81bb5-113">To verify the creation of the SWIFTPipelines.dll file, using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to \<*drive*:>\labs\SWIFTProject\SWIFTPipelines\bin\Development, and ensure that the file exists in this folder.</span></span>  
  
3.  <span data-ttu-id="81bb5-114">ソリューション エクスプ ローラーで右クリック**SWIFTPipelines**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-114">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81bb5-115">展開プロセス中に表示しないようにエラーまたは警告があります。</span><span class="sxs-lookup"><span data-stu-id="81bb5-115">During the deployment process, you should not see any failures or warnings.</span></span> <span data-ttu-id="81bb5-116">作成する場合は、エラーの原因を確認して、して修正し、プロジェクトを再展開します。</span><span class="sxs-lookup"><span data-stu-id="81bb5-116">If you do, check the source of the error, correct it, and then re-deploy the project.</span></span>  
  
4.  <span data-ttu-id="81bb5-117">展開の成功を準拠するように、**ビュー**のメニュー[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**BizTalk エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-117">To conform deployment success, in the **View** menu of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **BizTalk Explorer**.</span></span>  
  
5.  <span data-ttu-id="81bb5-118">右クリック**BizTalk 構成データベース**、クリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-118">Right-click **BizTalk Configuration Databases**, and then click **Refresh**.</span></span>  
  
6.  <span data-ttu-id="81bb5-119">展開、**アセンブリ**ノード アクセラレータが正常に展開されたことを確認および**SWIFTPipelines (1.0.0.0)**です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-119">Expand the **Assemblies** node and confirm that the accelerator successfully deployed **SWIFTPipelines (1.0.0.0)**.</span></span>  
  
 <span data-ttu-id="81bb5-120">進みます[第 4 章: 受信 XML を作成して、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="81bb5-120">Proceed to [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md).</span></span>