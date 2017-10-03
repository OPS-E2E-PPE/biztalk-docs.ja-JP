---
title: "Idoc を受信するためのメッセージ コンテキスト プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca289e37cac15972e75c69d7ad20928b72911963
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-context-properties-for-receiving-idocs"></a>Idoc を受信するためのメッセージ コンテキスト プロパティ
Microsoft を使用して、IDOC を受信するため[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のメッセージ コンテキスト プロパティをサポートしています。  
  
 **IDOC 制御レコードのプロパティです。**  
  
-   **TABNAM** -テーブルの構造体の名前  
  
-   **MANDT** -クライアント  
  
-   **DOCNUM** -IDOC 番号  
  
-   **DOCREL** -IDOC に対する SAP リリース  
  
-   **ステータス**の IDOC の状態  
  
-   **直接**-の方向  
  
-   **OUTMOD** -出力モード  
  
-   **表現**受信処理にオーバーライドする -  
  
-   **テスト**-フラグのテスト  
  
-   **IDOCTYP** -基本型の名前  
  
-   **CIMTYP** -拡張機能 (顧客により定義)  
  
-   **MESTYP** -メッセージの種類  
  
-   **MESCOD** -メッセージ コード  
  
-   **MESFCT** -メッセージ関数  
  
-   **STD** -EDI 標準、フラグ  
  
-   **STDVRS** -EDI のバージョンとリリースに標準的な  
  
-   **STDMES** -EDI メッセージの種類  
  
-   **SNDPOR** -送信者のポート (SAP システム、サブシステムの外部)  
  
-   **SNDPRT** -パートナーの送信者の種類  
  
-   **SNDPFC** -パートナーの送信元の関数  
  
-   **SNDPRN** -パートナーの送信者の数  
  
-   **SNDSAD** -センダのアドレス (SADR)  
  
-   **SNDLAD** -送信者の論理アドレス  
  
-   **RCVPOR** -受信ポート  
  
-   **RCVPRT** -受信者のパートナーの種類  
  
-   **RCVPFC** -パートナーの受信者の関数  
  
-   **RCVPRN** -パートナーの受信者の数  
  
-   **RCVSAD** -受信者のアドレス (SADR)  
  
-   **RCVLAD** -受信者の論理アドレス  
  
-   **CREDAT**上に作成された -  
  
-   **CRETIM** -作成された時刻  
  
-   **REFINT** -転送のファイル (EDI インターチェンジ)  
  
-   **REFGRP** -メッセージのグループ (EDI メッセージのグループ)  
  
-   **REFMES** -メッセージ (EDI メッセージ)  
  
-   **ARCKEY** - 外部メッセージのアーカイブのキー  
  
-   **シリアル**のシリアル化  
  
-   **DOCTYP** -IDOC タイプ (この EDI_DC で使用できるだけです。 コンテキスト プロパティ内に存在する必要がありますが、2 の Idoc のバージョンののみ昇格させる必要があります)  
  
 **TID** – 着信 TRFC の呼び出しの SAP システムによって送信された TID を表します。  
  
 **GUID** : GUID を表します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]内部的に使用します。 これは、SAP システムから受け取った TID と一対一のマッピングです。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)