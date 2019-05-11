---
title: BizTalk 操作サンプルをインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23ecf4795c6e495d2606f0411256bd806ee1e6f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295140"
---
# <a name="installing-the-biztalk-operations-sample"></a><span data-ttu-id="56c6f-102">BizTalk 操作サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="56c6f-102">Installing the BizTalk Operations Sample</span></span>
<span data-ttu-id="56c6f-103">Microsoft BizTalk 操作サンプルには、ESB BizTalk 操作のサービスをインストールして構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="56c6f-103">The Microsoft BizTalk Operations sample requires the ESB BizTalk Operations service installed and configured.</span></span> <span data-ttu-id="56c6f-104">ESB BizTalk Operations サービスでは、インストールして、ESB 構成ツールを使用して構成するコア Web サービスの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="56c6f-104">ESB BizTalk Operations service is one of the core Web services that can be installed and configured using the ESB Configuration Tool.</span></span> <span data-ttu-id="56c6f-105">詳細については、ESB 構成ツールを使用して、次を参照してください。 [ http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-105">For more information about using the ESB Configuration Tool, see [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span></span> <span data-ttu-id="56c6f-106">BizTalk 操作 Web サービスの既定の場所は<http://localhost/ESB.BizTalkOperationsService/Operations.asmx>。 ただし、別の場所またはリモート サーバーでサービスをデプロイする場合、アプリケーション構成ファイルで変更することができます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-106">The default location of the BizTalk Operations Web service is <http://localhost/ESB.BizTalkOperationsService/Operations.asmx>; however, you can change this in the application configuration file if you deploy the service in a different location or a remote server.</span></span>  

 <span data-ttu-id="56c6f-107">ソリューションのプロジェクトからの BizTalk 操作サンプルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-107">You must install BizTalk Operations sample from the solution project.</span></span>  

 <span data-ttu-id="56c6f-108">**BizTalk 操作サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="56c6f-108">**To install the BizTalk Operations sample**</span></span>  

1. <span data-ttu-id="56c6f-109">インストールした \Source\Samples\BizTalkOperations フォルダーから ESB.BizTalkOperations.Test.Client.csproj という名前のソリューションを開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]に Visual Studio のサンプル。</span><span class="sxs-lookup"><span data-stu-id="56c6f-109">Open the solution named ESB.BizTalkOperations.Test.Client.csproj from the \Source\Samples\BizTalkOperations folder where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples into Visual Studio.</span></span>  

2. <span data-ttu-id="56c6f-110">使用して、**ビルド**] メニューの [ソリューションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="56c6f-110">Use the commands on the **Build** menu to compile the solution.</span></span>
