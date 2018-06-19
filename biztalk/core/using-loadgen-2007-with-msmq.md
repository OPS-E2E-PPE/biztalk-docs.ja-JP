---
title: MSMQ での LoadGen 2007 を使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 55d67628b7863df3f2396cd9b45b55f42a488b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287130"
---
# <a name="using-loadgen-2007-with-msmq"></a><span data-ttu-id="77b11-102">MSMQ での LoadGen 2007 の使用</span><span class="sxs-lookup"><span data-stu-id="77b11-102">Using LoadGen 2007 with MSMQ</span></span>
<span data-ttu-id="77b11-103">負荷生成ツール Loadgen を使用すると、BizTalk Server システム上の大きな負荷をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="77b11-103">The Load Generation tool, Loadgen, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77b11-104">LoadGen 2007 ツールはダウンロード[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)です。</span><span class="sxs-lookup"><span data-stu-id="77b11-104">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span>  
  
 <span data-ttu-id="77b11-105">MSMQ での LoadGen の使用はサポートしていますが、MSMQ ランタイム サービスがコンピューターにインストールされていないことがあるため、インストール処理で MSMQ COM コンポーネントを自動的に登録することはしません。</span><span class="sxs-lookup"><span data-stu-id="77b11-105">Using LoadGen with MSMQ is supported, but we do not auto-register the MSMQ COM components during installation since the MSMQ runtime service may not be installed on your computer.</span></span>  
  
 <span data-ttu-id="77b11-106">MSMQ および LoadGen を使用するには、Bin ディレクトリに配置されている MSMQTransmitter.dll ファイルと ComMsmqMonitor.dll ファイルを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="77b11-106">To use MSMQ and LoadGen, manually register the MSMQTransmitter.dll and ComMsmqMonitor.dll files located in the bins directory:</span></span>  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 <span data-ttu-id="77b11-107">MSMQ COM コンポーネントを登録しないと、次のようなランタイム エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77b11-107">If you do not register the MSMQ COM components, you will receive the following runtime errors:</span></span>  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a><span data-ttu-id="77b11-108">参照</span><span class="sxs-lookup"><span data-stu-id="77b11-108">See Also</span></span>  
 [<span data-ttu-id="77b11-109">エンジンの MST を測定するためのシナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="77b11-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)