---
title: Idoc を受信するためのメッセージ コンテキスト プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5468a1944ecfb4e2ae3da2ded5d941d19ac37712
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373258"
---
# <a name="message-context-properties-for-receiving-idocs"></a>Idoc を受信するためのメッセージ コンテキスト プロパティ
Microsoft を使用して IDOC を受信するため[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のメッセージ コンテキスト プロパティがサポートされます。  
  
 **IDOC 制御レコードのプロパティです。**  
  
- **TABNAM** -テーブルの構造体の名前  
  
- **MANDT** -クライアント  
  
- **DOCNUM** -IDOC 番号  
  
- **DOCREL** -IDOC を SAP リリース  
  
- **ステータス**の IDOC の状態  
  
- **直接**-の方向  
  
- **OUTMOD** -出力モード  
  
- **表現**- 受信処理にオーバーライドします。  
  
- **テスト**-フラグをテストします。  
  
- **IDOCTYP** -基本的な型の名前  
  
- **CIMTYP** -拡張機能 (顧客によって定義される)  
  
- **MESTYP** -メッセージの種類  
  
- **MESCOD** -メッセージ コード  
  
- **MESFCT** -メッセージの関数  
  
- **STD** -EDI 標準、フラグ  
  
- **STDVRS** -EDI、標準のバージョンとリリース  
  
- **STDMES** -EDI メッセージの種類  
  
- **SNDPOR** -送信者のポート (SAP システムの外部のサブシステム)  
  
- **SNDPRT** -パートナーの送信者の種類  
  
- **SNDPFC** -パートナーの送信元の関数  
  
- **SNDPRN** -パートナーの送信側の数  
  
- **SNDSAD** -センダのアドレス (SADR)  
  
- **SNDLAD** -送信者の論理アドレス  
  
- **RCVPOR** -受信ポート  
  
- **RCVPRT** -受信者のパートナーの種類  
  
- **RCVPFC** -パートナーの受信者の関数  
  
- **RCVPRN** -パートナーの受信者の数  
  
- **RCVSAD** -受信者のアドレス (SADR)  
  
- **RCVLAD** -受信者の論理アドレス  
  
- **CREDAT** - の作成  
  
- **CRETIM** -作成された時刻  
  
- **REFINT** -転送のファイル (EDI インターチェンジ)  
  
- **REFGRP** -メッセージのグループ (EDI メッセージのグループ)  
  
- **REFMES** -メッセージ (EDI メッセージ)  
  
- **ARCKEY** - 外部メッセージのアーカイブのキー  
  
- **シリアル**-シリアル化  
  
- **DOCTYP**の IDOC の種類 (この EDI_DC で使用できるだけです。 コンテキスト プロパティに存在する必要がありますが、2 の Idoc のバージョンののみ昇格する必要があります)  
  
  **TID** – 受信 TRFC 呼び出しの SAP システムから送信された TID を表します。  
  
  **GUID** : GUID を表します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は内部的に使用します。 これは、SAP システムから受け取った TID で一対一のマッピングがあります。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)