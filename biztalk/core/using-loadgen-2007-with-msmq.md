---
title: MSMQ での LoadGen 2007 の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8f23a86-0e6d-478a-87a3-5b02338c9afb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec8f56e431a54599711f59a25542213813f9c698
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396846"
---
# <a name="using-loadgen-2007-with-msmq"></a><span data-ttu-id="bfa1c-102">MSMQ での LoadGen 2007 の使用</span><span class="sxs-lookup"><span data-stu-id="bfa1c-102">Using LoadGen 2007 with MSMQ</span></span>
<span data-ttu-id="bfa1c-103">負荷生成ツール Loadgen をでは、BizTalk Server システム上の負荷をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfa1c-103">The Load Generation tool, Loadgen, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfa1c-104">LoadGen 2007 ツールがダウンロードできる[ http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)します。</span><span class="sxs-lookup"><span data-stu-id="bfa1c-104">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span>  
  
 <span data-ttu-id="bfa1c-105">MSMQ での LoadGen の使用がサポートされていますが、私たちは自動登録 MSMQ COM コンポーネントのインストール時に、MSMQ ランタイム サービスがコンピューターにインストールされていない可能性がありますので。</span><span class="sxs-lookup"><span data-stu-id="bfa1c-105">Using LoadGen with MSMQ is supported, but we do not auto-register the MSMQ COM components during installation since the MSMQ runtime service may not be installed on your computer.</span></span>  
  
 <span data-ttu-id="bfa1c-106">MSMQ および LoadGen を使用するには、ビンのディレクトリにある MSMQTransmitter.dll と ComMsmqMonitor.dll ファイルを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="bfa1c-106">To use MSMQ and LoadGen, manually register the MSMQTransmitter.dll and ComMsmqMonitor.dll files located in the bins directory:</span></span>  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 <span data-ttu-id="bfa1c-107">MSMQ COM コンポーネントを登録していない場合は、次の実行時エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bfa1c-107">If you do not register the MSMQ COM components, you will receive the following runtime errors:</span></span>  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfa1c-108">参照</span><span class="sxs-lookup"><span data-stu-id="bfa1c-108">See Also</span></span>  
 [<span data-ttu-id="bfa1c-109">エンジンの MST を測定するためのテスト シナリオ</span><span class="sxs-lookup"><span data-stu-id="bfa1c-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)