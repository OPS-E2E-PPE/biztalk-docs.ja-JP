---
title: X12 TA1 受信確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a168a4112e861ea6b33b232883d320be2aa1ba82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394752"
---
# <a name="x12-ta1-acknowledgment"></a>X12 TA1 確認
X12 TA1 技術確認のインターチェンジ ヘッダーとトレーラー、アドレス受信者による処理の状態を報告します。 ISA および IEA が X12 でエンコードされたメッセージの有効な場合、肯定 TA1 確認が送信されますが、任意の他のコンテンツのステータスです。 それ以外の場合は、エラー コードで TA1 確認が送信されます。  
  
 X12 TA1 受信確認は、x12 _ に準拠している\<バージョン番号\>>_ta1.xsd スキーマ。 TA1 確認は、ISA/IEA エンベロープ内で送信されます。 ISA および IEA は、他のインターチェンジと違いはありません。  
  
 TA1 確認のインターチェンジ内のセグメントは、次の表に表示されます。  
  
|TA1 のフィールド|フィールドの名前|受信したインターチェンジにマップされています。|値|  
|------------------|-------------------|------------------------------------|-----------|  
|TA101|インターチェンジ制御番号|ISA13 - インターチェンジ制御番号|-|  
|TA102|インターチェンジ日付|Isa09-インターチェンジ日付|-|  
|TA103|インターチェンジ時刻|ISA10 – Interchange Time|-|  
|TA104|インターチェンジ確認コード *|なし|エンジンの動作:A、E、または R<br /><br /> A = 受理します。<br /><br /> E = インターチェンジはエラーありで受理<br /><br /> R = インターチェンジを拒否/中断|  
|TA105|インターチェンジ通知コード|なし|結果のエラー コードを処理します。 **注:** 内のテーブルを参照してください。 [X12 TA1 受信確認エラー コード](../core/x12-ta1-acknowledgment-error-codes.md)します。|  
  
 \* データ要素の検証に基づくエンジンの動作セキュリティおよび認証情報を除くは、これは構成情報の文字列比較に基づきます。