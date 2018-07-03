---
title: FileAct アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6fe9b28e4ea2b5eee087b61866827a766c3e3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971491"
---
# <a name="what-is-the-fileact-adapter"></a>FileAct アダプターとは何ですか。
SWIFTNet 用に FileAct アダプターは、ファイルの転送で、世界銀行間金融電気通信 (SWIFT) Secure IP Network (SIPN) を BizTalk Server と、Society 間の接続を提供します。 SIPN は、金融機関、金融業界インフラストラクチャ、顧客との接続をセキュリティで保護されたプライベート ネットワーク経由でメッセージやファイルを転送します。 FileAct アダプターは SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) s を SIPN への接続を使用します。  
  
 FileAct アダプターでは、安全に SWIFT の参加者のメカニズムを備えていて、ファイルとそれらのファイルに関連する情報を確実に交換します。 次の機能がサポートされています。  
  
-   SWIFTNet ユーザーにファイルを送信します。  
  
-   SWIFTNet ユーザーからファイルを取得します。  
  
-   配信通知の受信側でのファイルの受信を確認します。  
  
-   進行中の転送を中止します。  
  
-   ファイル転送状態の監視  
  
-   同時実行のファイル転送  
  
-   データの信頼性と整合性の保証  
  
-   転送中のファイル データの機密性  
  
-   ファイル転送の否認不可  
  
-   タイムスタンプ  
  
## <a name="the-fileact-service"></a>FileAct サービス  
 SWIFTNet 用に FileAct アダプターでは、構造化された金融メッセージまたはサイズの大きなレポートのバッチなどのファイルの転送を安全かつ高い信頼性を提供します。 一般的なアプリケーションには、反復的なクレジット転送年金または給与支払、証券の付加価値のある情報とレポート、および規制レポートなどが含まれます。 SWIFTNet FileAct には、さまざまなメッセージングのモードが提供しています。  
  
- **ストア アンド フォワード ファイル転送します。** 不確実性とかどうか、本物でオンラインになって、ファイルを送信する時間について心配することの不便の SWIFTNet FileAct ストア アンド フォワードの機能を削除します。 ファイルは、受信者がメッセージを受信する準備がすぐに配信されます。 その結果、多数の異なるタイム ゾーンのうちいくつかあります本物のファイルを送信するための望ましい方法を提供します。  
  
- **リアルタイムのファイル転送。** リアルタイム メッセージングは、格納および転送時にオンラインになっている本物を宛先とするファイルを転送する低コストの選択肢を提供します。 その結果、いくつかの大きな本物またはインフラストラクチャの市場にファイルを送信するために最適です。  
  
- **リアルタイムのファイルを取得します。** これは、通常のワークステーション ベースのシステム コンテキストで、多くの場合、SWIFTNet 参照と組み合わせてのファイルを取得するために使用する対話型のサービスです。 このモードがサポートします。  
  
  (ファイル単位) では、オプションの SWIFTNet FileAct 機能は次のとおりです。  
  
- **メッセージの優先度。** ファイル転送は、処理、本物を適切なために、メッセージで「緊急」としてフラグことができます。  
  
- **配信通知 (リアルタイムおよびストア アンド フォワード モード)。** 相手が、ファイルを受信することの確認を提供します。  
  
- **出力と受信の非否認します。** に関して問題が発生した場合は、ファイル転送が行われるように要求を確認する SWIFT を使用できます。  
  
  SWIFTNet FileAct の標準機能には、SWIFTNet PKI のセキュリティが含まれます。<strong>します。</strong> SWIFTNet FileAct は SWIFTNet PKI を使用して保護し、メッセージの認証と整合性の制御を提供します。  
  
  すべてのメッセージと SWIFTNet で交換されるファイルは、ユーザーをバイパスできませんセキュリティ、検証、およびプラットフォームのルーティング規則のことを確認する一連の一般的に行われます。 これらのチェックは、SWIFTAlliance ゲートウェイ (SAG) アプリケーションによって実行されます。  
  
## <a name="see-also"></a>参照  
 [概要 FileAct および InterAct アダプター](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [SWIFTNet とは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [InterAct アダプターとは](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)