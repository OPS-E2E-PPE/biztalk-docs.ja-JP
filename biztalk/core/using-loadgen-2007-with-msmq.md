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
# <a name="using-loadgen-2007-with-msmq"></a>MSMQ での LoadGen 2007 の使用
負荷生成ツール Loadgen を使用すると、BizTalk Server システム上の大きな負荷をシミュレートできます。  
  
> [!NOTE]
>  LoadGen 2007 ツールはダウンロード[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)です。  
  
 MSMQ での LoadGen の使用はサポートしていますが、MSMQ ランタイム サービスがコンピューターにインストールされていないことがあるため、インストール処理で MSMQ COM コンポーネントを自動的に登録することはしません。  
  
 MSMQ および LoadGen を使用するには、Bin ディレクトリに配置されている MSMQTransmitter.dll ファイルと ComMsmqMonitor.dll ファイルを手動で登録します。  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 MSMQ COM コンポーネントを登録しないと、次のようなランタイム エラーが表示されます。  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md)