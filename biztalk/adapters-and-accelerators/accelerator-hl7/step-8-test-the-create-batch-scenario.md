---
title: "手順 8: 作成バッチ シナリオのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc7fac40-fd3e-413b-82cc-7ad08226094c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 865717858e27509a9f9e4af611b39ba10be212a5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-8-test-the-create-batch-scenario"></a>手順 8: 作成するバッチのシナリオをテストします。
このステップでは、ソース Tutorial_BTAHL7Pickup フォルダーにバッチ処理するメッセージのテスト インスタンスを削除することにより、バッチの作成シナリオをテストします。 送信ポートを設定するには、ソース フォルダーからメッセージを取得し、送信;受信ポートを受信します。受信パイプラインはそれを処理し、Tutorial_BTAHL7Drop コピー先のフォルダーにドロップします。  
  
### <a name="to-test-the-create-batch-scenario"></a>バッチの作成シナリオをテストするには  
  
1.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、   **\<*ドライブ*\>: \Batching Tutorial\Instances** フォルダーです。  
  
2.  選択**CreateBatchMessage1.txt**、および**CreateBatchMessage2.txt**、それらを右クリックし、クリックして**コピー**です。  
  
3.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、   **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\ のアクセラレータSDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7Pickup * * フォルダーです。  
  
4.  フォルダーを右クリックし、をクリックして**貼り付け**です。  
  
### <a name="to-verify-the-results-of-the-create-batch-scenario"></a>バッチの作成シナリオの結果を確認するには  
  
1.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、   **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\ のアクセラレータSDK\End エンドツー エンド Tutorial\Tutorial_BatchACKDrop * * フォルダーです。 短時間の後に、フォルダーに表示される受信確認のバッチの処理のインスタンスが表示されます。 表示されない場合は、確認、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エラー メッセージは、イベント ビューアー。 ファイルは、名前を付ける必要があります\< *Guid*\>.txt です。 このバッチは、最初に送信された 2 つのメッセージを受信したときに生成された 2 つの受信確認を含める必要があります。 このバッチは、次のフィールドが必要です。  
  
    |FHS.5|BHS.5|BTS.1|FTS.1|  
    |-----------|-----------|-----------|-----------|  
    |Tutorial_BatchSource|Tutorial_BatchSource|2|1|  
  
     バッチ内で受信確認は、次のフィールドが必要です。  
  
    |MSH.9|MSA.2|MSA.1|MSH.3|MSH.5|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK ^ A03 ^ ACK|Msg01|AA|Tutorial_BatchDest|Tutorial_BatchSource|  
    |ACK ^ A03 ^ ACK|Msg02|AA|Tutorial_BatchDest|Tutorial_BatchSource|  
  
2.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、   **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\ のアクセラレータSDK\End エンドツー エンド Tutorial\Tutorial_BatchMsgDrop * * フォルダーです。 1 時間後に、フォルダーに表示されるメッセージ バッチの処理済みインスタンスが表示されます。 表示されない場合は、確認、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エラー メッセージは、イベント ビューアー。 ファイルは、名前を付ける必要があります\< *Guid*\>.txt です。 このバッチは、最初に送信された 2 つのメッセージを含める必要があります。 このバッチは、次のフィールドが必要です。  
  
    |FHS.5|BHS.5|BTS.1|FTS.1|  
    |-----------|-----------|-----------|-----------|  
    |Tutorial_BatchDest|Tutorial_BatchDest|2|1|  
  
     バッチ内のメッセージは、次のフィールドが必要です。  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|Msg01|Tutorial_BatchSource|Tutorial_BatchDest|  
    |ADT ^ A03|Msg02|Tutorial_BatchSource|Tutorial_BatchDest|  
  
     バッチは、ヘッダーとトレーラーのバッチに特定の 2 つのセットでラップされます。  
  
    -   複数のバッチを含めることができるファイルを囲むために使用されるファイルのヘッダーおよびトレーラー (FHS および FT)。 ファイル受信アプリケーションに注意してください (**Tutorial_BatchDest**) FHS5 フィールドであり、ファイルの作成の日付/時刻 FHS7 にします。 FTS2 でファイルのバッチ数 (ファイル内のバッチの数) に注意してください (1)。  
  
    -   各バッチを囲むために使用されるバッチ ヘッダーおよびトレーラー (BHS および BTS)。 受信 BTS2 でアプリケーションおよびバッチの作成日付/時刻、FHS、およびバッチ メッセージの数 (2) のように、ファイルに注意してください。  
  
## <a name="see-also"></a>参照  
 [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [パート 3: バッチの作成シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)