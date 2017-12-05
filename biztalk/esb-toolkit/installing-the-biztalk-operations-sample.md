---
title: "BizTalk Operations サンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8fb289e5bb7950f9ad8bca3dac98035bada176
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="installing-the-biztalk-operations-sample"></a><span data-ttu-id="3f01c-102">BizTalk Operations サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3f01c-102">Installing the BizTalk Operations Sample</span></span>
<span data-ttu-id="3f01c-103">Microsoft BizTalk Operations サンプルには、ESB BizTalk 操作のサービスのインストールし、構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="3f01c-103">The Microsoft BizTalk Operations sample requires the ESB BizTalk Operations service installed and configured.</span></span> <span data-ttu-id="3f01c-104">ESB BizTalk Operations サービスをインストールして、ESB 構成ツールを使用して構成するコア Web サービスの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3f01c-104">ESB BizTalk Operations service is one of the core Web services that can be installed and configured using the ESB Configuration Tool.</span></span> <span data-ttu-id="3f01c-105">ESB 構成ツールの使用に関する詳細については、次を参照してください[http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).。</span><span class="sxs-lookup"><span data-stu-id="3f01c-105">For more information about using the ESB Configuration Tool, see [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span></span> <span data-ttu-id="3f01c-106">BizTalk Operations Web サービスの既定の場所は http://localhost/ESB.BizTalkOperationsService/Operations.asmx;ただし、変更できますこのアプリケーション構成ファイル内の別の場所またはリモート サーバーでサービスを展開する場合。</span><span class="sxs-lookup"><span data-stu-id="3f01c-106">The default location of the BizTalk Operations Web service is http://localhost/ESB.BizTalkOperationsService/Operations.asmx; however, you can change this in the application configuration file if you deploy the service in a different location or a remote server.</span></span>  
  
 <span data-ttu-id="3f01c-107">ソリューションのプロジェクトからの BizTalk 操作サンプルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f01c-107">You must install BizTalk Operations sample from the solution project.</span></span>  
  
 <span data-ttu-id="3f01c-108">**BizTalk 操作サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="3f01c-108">**To install the BizTalk Operations sample**</span></span>  
  
1.  <span data-ttu-id="3f01c-109">インストールした \Source\Samples\BizTalkOperations フォルダーから ESB.BizTalkOperations.Test.Client.csproj をという名前のソリューションを開き、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Visual studio のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="3f01c-109">Open the solution named ESB.BizTalkOperations.Test.Client.csproj from the \Source\Samples\BizTalkOperations folder where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples into Visual Studio.</span></span>  
  
2.  <span data-ttu-id="3f01c-110">コマンドを使用、**ビルド**ソリューションをコンパイルするにはメニュー。</span><span class="sxs-lookup"><span data-stu-id="3f01c-110">Use the commands on the **Build** menu to compile the solution.</span></span>