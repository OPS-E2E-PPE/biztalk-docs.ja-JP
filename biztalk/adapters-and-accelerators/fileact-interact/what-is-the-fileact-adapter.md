---
title: "FileAct アダプターとは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62b83fc723bbebce857eb442384b14179c1072ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-fileact-adapter"></a>FileAct アダプターとは何ですか。
SWIFTNet の FileAct アダプターは、ファイルを転送するための世界銀行間財務通信 (SWIFT) セキュリティで保護された IP ネットワーク (SIPN) の BizTalk Server と、Society 間の接続に提供します。 SIPN は、金融機関、金融業界インフラストラクチャ、および顧客を接続するセキュリティで保護されたプライベート ネットワーク経由でメッセージとファイルを転送します。 FileAct アダプターは、SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) s、SIPN への接続に使用します。  
  
 FileAct アダプターは、安全に SWIFT の参加者のメカニズムを提供し、ファイルとそれらのファイルに関連する情報を確実に交換します。 次の機能がサポートされています。  
  
-   SWIFTNet ユーザーにファイルを送信します。  
  
-   SWIFTNet ユーザーからファイルを取得します。  
  
-   配信通知の受信側でのファイルの受信を確認します。  
  
-   進行中の転送を中止します。  
  
-   ファイルの転送の状態の監視  
  
-   同時実行のファイル転送  
  
-   データの完全性と整合性の保証  
  
-   転送中にファイル データの機密性  
  
-   ファイル転送の否認不可  
  
-   タイムスタンプ  
  
## <a name="the-fileact-service"></a>FileAct サービス  
 SWIFTNet の FileAct アダプターは、構造化された財務メッセージまたはサイズの大きなレポートのバッチなどのファイルの安全性と信頼性の高い転送を提供します。 一般的なアプリケーションには、反復的なクレジット転送年金または給与支払、証券付加価値のある情報とレポート、および規制 reporting などが含まれます。 SWIFTNet FileAct には、さまざまなメッセージング モードが提供しています。  
  
-   **ストア アンド フォワード ファイル転送します。** SWIFTNet FileAct ストア アンド フォワードの機能は、不確実性とするかどうか、ユーザーはオンライン時のファイルを送信する心配不便さを削除します。 ファイルは、受信者がメッセージを受信する準備がすぐに配信されます。 その結果、多数のうち一部異なるタイム ゾーンでは、ユーザーにファイルを送信するための望ましい方法を提供します。  
  
-   **リアルタイムのファイル転送します。** リアルタイムのメッセージング、格納および転送時にオンラインになっている相手の送信先となるファイルの転送に低コストの選択肢が用意されています。 その結果、いくつかの大きな見または市場インフラストラクチャにファイルを送信するために最適です。  
  
-   **リアルタイムのファイルを取得します。** これは、通常ワークステーション ベースのシステムのコンテキストでは、多くの場合、SWIFTNet 参照と共にのファイルを取得するために使用する対話型サービスです。 このモードがサポートされます。  
  
 (ファイルをファイルごと) に省略可能な SWIFTNet FileAct 機能は次のとおりです。  
  
-   **メッセージの優先度。** ファイル転送フラグを設定できます「緊急」としてメッセージで、適切な相手の処理を許可します。  
  
-   **配信通知 (リアルタイムおよびストア アンド フォワード モード)。** 相手には、ファイルが受信されたことの確認を提供します。  
  
-   **否認不可の出力と受信します。** に関して問題が発生した場合に、ファイル転送が行われるように要求を確認する SWIFT を使用できます。  
  
 標準の SWIFTNet FileAct 機能に SWIFTNet PKI のセキュリティは、**です。** SWIFTNet FileAct は SWIFTNet PKI を使用して保護し、メッセージの認証と整合性の制御を提供します。  
  
 すべてのメッセージと SWIFTNet で交換されるファイルには、一般的な一連のあるユーザーをバイパスできませんセキュリティ、検証、およびプラットフォームのルーティング規則を確認するチェックが行われます。 これらのチェックは、SWIFTAlliance ゲートウェイ (SAG) アプリケーションによって実行されます。  
  
## <a name="see-also"></a>参照  
 [入門、FileAct および InterAct アダプター](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [SWIFTNet とは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [アダプターを操作しますか?](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)