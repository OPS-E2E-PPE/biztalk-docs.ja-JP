---
title: '手順 8: バッチの作成シナリオのテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc7fac40-fd3e-413b-82cc-7ad08226094c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d880d1f9d586878a28803ef5060cfb770bf67a7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007811"
---
# <a name="step-8-test-the-create-batch-scenario"></a>手順 8: バッチの作成シナリオをテストします。
この手順では、ソース Tutorial_BTAHL7Pickup フォルダーにバッチ処理するメッセージのテスト インスタンスを削除することにより、バッチの作成シナリオをテストします。 送信ポートを設定することがソース フォルダーからメッセージを取得し、それを送信します受信ポートを受信します。受信パイプラインは処理され、Tutorial_BTAHL7Drop コピー先のフォルダーに格納します。  

### <a name="to-test-the-create-batch-scenario"></a>バッチの作成シナリオをテストするには  

1. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Batching Tutorial\Instances**フォルダー。  

2. 選択**CreateBatchMessage1.txt**、および**CreateBatchMessage2.txt**を右クリックし、クリックして**コピー**します。  

3. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BTAHL7Pickup**フォルダー。  

4. フォルダーを右クリックし、**貼り付け**します。  

### <a name="to-verify-the-results-of-the-create-batch-scenario"></a>バッチの作成シナリオの結果を確認するには  

1. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BatchACKDrop**フォルダー。 短い期間の後に、フォルダーに表示される受信確認のバッチの処理のインスタンスが表示されます。 表示されない場合は、確認、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーのエラー メッセージ。 名前を指定する必要がありますファイル\< *Guid*\>.txt します。 このバッチは、最初に送信された 2 つのメッセージを受信すると生成された 2 つの受信確認を含める必要があります。 このバッチは、次のフィールドが必要です。  

   |FHS.5|BHS.5|BTS.1|FTS.1|  
   |-----------|-----------|-----------|-----------|  
   |Tutorial_BatchSource|Tutorial_BatchSource|2|1|  

    バッチ内で受信確認は、次のフィールドが必要です。  


   |    MSH.9    | MSA.2 | MSA.1 |       MSH.3        |        MSH.5         |
   |-------------|-------|-------|--------------------|----------------------|
   | ACK ^ A03 ^ ACK | Msg01 |  AA   | Tutorial_BatchDest | Tutorial_BatchSource |
   | ACK ^ A03 ^ ACK | Msg02 |  AA   | Tutorial_BatchDest | Tutorial_BatchSource |


2. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BatchMsgDrop**フォルダー。 1 時間後に、フォルダーに表示されるメッセージ バッチの処理のインスタンスが表示されます。 表示されない場合は、確認、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーのエラー メッセージ。 名前を指定する必要がありますファイル\< *Guid*\>.txt します。 このバッチは、最初に送信された 2 つのメッセージを含める必要があります。 このバッチは、次のフィールドが必要です。  

   |FHS.5|BHS.5|BTS.1|FTS.1|  
   |-----------|-----------|-----------|-----------|  
   |Tutorial_BatchDest|Tutorial_BatchDest|2|1|  

    バッチ内のメッセージは、次のフィールドが必要です。  

   |MSH.9|MSH.10|MSH.3|MSH.5|  
   |-----------|------------|-----------|-----------|  
   |ADT ^ A03|Msg01|Tutorial_BatchSource|Tutorial_BatchDest|  
   |ADT ^ A03|Msg02|Tutorial_BatchSource|Tutorial_BatchDest|  

    バッチは、ヘッダーとトレーラーのバッチに固有の 2 つのセットにラップされています。  

   -   複数のバッチを含めることができるファイルを囲むために使用されるファイルのヘッダーおよびトレーラー (FHS と FTS)。 ファイル受信アプリケーションに注意してください (**Tutorial_BatchDest**) FHS5 フィールドと、ファイルの作成の日付/時刻 FHS7 でします。 FTS2 でファイルのバッチ数 (ファイル内のバッチの数) に注意してください (1)。  

   -   各バッチを囲むために使用されるバッチ ヘッダーおよびトレーラー (BHS および BTS)。 BTS2 で受信アプリケーションおよびバッチの作成日付/時刻、FHS、およびバッチのメッセージ数 (2) のように、ファイルに注意してください。  

## <a name="see-also"></a>参照  
 [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [パート 3: バッチの作成シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)