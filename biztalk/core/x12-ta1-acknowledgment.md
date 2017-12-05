---
title: "X12 TA1 受信確認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6a3de45744b40335999c1471165ff851ec60664
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="x12-ta1-acknowledgment"></a>X12 TA1 確認
X12 TA1 技術確認では、アドレス受信者によるインターチェンジ ヘッダーおよびトレーラの処理状態が報告されます。 X12 でエンコードされたメッセージの ISA および IEA が有効な場合は、他のコンテンツの状態に関係なく、肯定 TA1 確認が送信されます。 ISA および IEA が無効な場合は、TA1 確認がエラー コードと共に送信されます。  
  
 X12 TA1 受信確認は、x12 _ に準拠している\<バージョン番号\>>_ta1.xsd スキーマです。 TA1 確認は、ISA/IEA エンベロープ内で送信されます。 ISA および IEA は、他のインターチェンジと違いはありません。  
  
 TA1 確認のインターチェンジ内のセグメントを次の表に示します。  
  
|TA1 のフィールド|フィールドの名前|マップされる受信インターチェンジ|値|  
|------------------|-------------------|------------------------------------|-----------|  
|TA101|インターチェンジ制御番号|ISA13 - インターチェンジ制御番号|-|  
|TA102|インターチェンジ日付|ISA09 - インターチェンジ日付|-|  
|TA103|インターチェンジ時刻|ISA10 - インターチェンジ時刻|-|  
|TA104|インターチェンジ確認コード*|なし|エンジンの動作: A、E、または R<br /><br /> A = 受理<br /><br /> E = インターチェンジを受理 (ただしエラーが発生)<br /><br /> R = インターチェンジを拒否/中断|  
|TA105|インターチェンジ通知コード|なし|処理結果のエラー コード **注:**でテーブルを参照してください[X12 TA1 受信確認エラー コード](../core/x12-ta1-acknowledgment-error-codes.md)です。|  
  
 \*データ要素の検証はエンジンの動作に基づいてセキュリティおよび認証情報を除くこれは基づきます構成情報で文字列を比較します。