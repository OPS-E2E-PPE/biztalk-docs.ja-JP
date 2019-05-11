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
# <a name="using-loadgen-2007-with-msmq"></a>MSMQ での LoadGen 2007 の使用
負荷生成ツール Loadgen をでは、BizTalk Server システム上の負荷をシミュレートすることができます。  
  
> [!NOTE]
>  LoadGen 2007 ツールがダウンロードできる[ http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)します。  
  
 MSMQ での LoadGen の使用がサポートされていますが、私たちは自動登録 MSMQ COM コンポーネントのインストール時に、MSMQ ランタイム サービスがコンピューターにインストールされていない可能性がありますので。  
  
 MSMQ および LoadGen を使用するには、ビンのディレクトリにある MSMQTransmitter.dll と ComMsmqMonitor.dll ファイルを手動で登録します。  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 MSMQ COM コンポーネントを登録していない場合は、次の実行時エラーを受け取ります。  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)