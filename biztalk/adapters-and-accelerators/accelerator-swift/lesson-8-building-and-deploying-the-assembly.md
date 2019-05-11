---
title: 'レッスン 8: ビルドと、アセンブリの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b78d78108b656eefd7861904f75b186891dd3e9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530562"
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a><span data-ttu-id="12638-102">レッスン 8: 構築およびアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="12638-102">Lesson 8: Building and Deploying the Assembly</span></span>
<span data-ttu-id="12638-103">このレッスンでは、ビルドし、前の手順で作成したパイプラインを含むアセンブリを生成するパイプライン プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="12638-103">In this lesson, you build and deploy the pipeline project to generate an assembly that contains the pipelines you created in the previous steps.</span></span> <span data-ttu-id="12638-104">このレッスンでは、これまでに作成した作業でコンパイル エラーがないをによりします。</span><span class="sxs-lookup"><span data-stu-id="12638-104">This lesson ensures there are no compilation errors in the work you have created so far.</span></span>  
  
 <span data-ttu-id="12638-105">保存して、プロジェクトをコンパイルしてアセンブリ (DLL) ファイル、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development フォルダー。</span><span class="sxs-lookup"><span data-stu-id="12638-105">You compile the project into an assembly (DLL) file and save it in the \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="12638-106">プロジェクトをビルドして展開するには</span><span class="sxs-lookup"><span data-stu-id="12638-106">To build and deploy the project</span></span>  
  
1. <span data-ttu-id="12638-107">ソリューション エクスプ ローラーで右クリックして**SWIFTPipelines**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="12638-107">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Build**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="12638-108">コンパイル プロセス中にいない、エラーが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12638-108">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="12638-109">場合は、エラーの原因を確認、修正およびプロジェクトを再ビルドします。</span><span class="sxs-lookup"><span data-stu-id="12638-109">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="12638-110">ただし、A4SWIFT パイプライン コンポーネントに関連する警告の番号が表示、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12638-110">You may, however, see a number of warnings related to the A4SWIFT pipeline components.</span></span> <span data-ttu-id="12638-111">設定して、これらの警告につながる条件を修正することができます、**ローカル コピー**パイプライン コンポーネントの参照のプロパティ**False**します。</span><span class="sxs-lookup"><span data-stu-id="12638-111">You can correct the condition leading to these warnings by setting the **Copy Local** properties of the pipeline component references to **False**.</span></span> <span data-ttu-id="12638-112">詳細についてを参照してください「で警告結果がパイプライン プロジェクトのビルド」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)します。</span><span class="sxs-lookup"><span data-stu-id="12638-112">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  
  
2. <span data-ttu-id="12638-113">SWIFTPipelines.dll の作成を検証するファイルを使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照\<*ドライブ*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development でファイルが存在することを確認してくださいこのフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="12638-113">To verify the creation of the SWIFTPipelines.dll file, using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to \<*drive*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development, and ensure that the file exists in this folder.</span></span>  
  
3. <span data-ttu-id="12638-114">ソリューション エクスプ ローラーで右クリックして**SWIFTPipelines**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="12638-114">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Deploy**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="12638-115">展開プロセス中にエラーまたは警告しない表示されます。</span><span class="sxs-lookup"><span data-stu-id="12638-115">During the deployment process, you should not see any failures or warnings.</span></span> <span data-ttu-id="12638-116">場合は、エラーの原因を確認、修正、およびプロジェクトを再デプロイします。</span><span class="sxs-lookup"><span data-stu-id="12638-116">If you do, check the source of the error, correct it, and then re-deploy the project.</span></span>  
  
4. <span data-ttu-id="12638-117">デプロイの成功に準拠するように、**ビュー**のメニュー [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**BizTalk エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="12638-117">To conform deployment success, in the **View** menu of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **BizTalk Explorer**.</span></span>  
  
5. <span data-ttu-id="12638-118">右クリック**BizTalk 構成データベース**、 をクリックし、**更新**します。</span><span class="sxs-lookup"><span data-stu-id="12638-118">Right-click **BizTalk Configuration Databases**, and then click **Refresh**.</span></span>  
  
6. <span data-ttu-id="12638-119">展開、**アセンブリ**ノード、アクセラレータが正常にデプロイされることを確認します。 **SWIFTPipelines (1.0.0.0)** します。</span><span class="sxs-lookup"><span data-stu-id="12638-119">Expand the **Assemblies** node and confirm that the accelerator successfully deployed **SWIFTPipelines (1.0.0.0)**.</span></span>  
  
   <span data-ttu-id="12638-120">続行する[モジュール 4。受信 XML を作成し、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="12638-120">Proceed to [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md).</span></span>