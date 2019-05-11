---
title: 新機能、InterAct アダプターでしょうか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ab3ebf74205af290924535a01fce73ff59d15e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364066"
---
# <a name="what-is-the-interact-adapter"></a>新機能、InterAct アダプターでしょうか。
SWIFTNet 用のアダプターを操作では、メッセージの転送を BizTalk Server と SWIFT Secure IP Network (SIPN) 間の接続を提供します。 SIPN は、金融機関、金融業界インフラストラクチャ、顧客との相互接続をセキュリティで保護されたプライベート ネットワーク経由でメッセージやファイルを転送します。 InterAct アダプターは SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) s を SIPN への接続を使用します。  
  
 SWIFTNet 対話構造化された個々 の財務メッセージの交換を安全かつ高い信頼性を提供します。 SWIFT の顧客のメッセージングの要件は、お客様が、メッセージも異なります。  
  
 次の機能がサポートされています。  
  
- PKI のセキュリティ  
  
- メッセージの検証  
  
- 構成可能な集中ルーティング  
  
- メッセージの優先順位  
  
- ストア アンド フォワード メッセージの配信通知  
  
- 否認不可の出力の確認メッセージ。  
  
  アダプターを使用する対話 SWIFTNet の外部で指定されたアプリケーションとの対話機能を利用します。 このアダプターには、転送、および監査したりしません exchange プリミティブを除く、メッセージの内容を検証するメッセージの内容に関する情報がありません。  
  
## <a name="interact-message-exchange"></a>InterAct メッセージ交換  
 SWIFTNet 対話構造化された個々 の財務メッセージの交換を安全かつ高い信頼性を提供します。 SWIFT の顧客のメッセージングの要件は、お客様が、メッセージも異なります。 SWIFTNet 操作と、さまざまな通信モードを提供します。  
  
- **ストア アンド フォワード メッセージです。** ストア アンド フォワードの SWIFTNet 操作の機能は、オペレーターの多くできない可能性がありますオンライン転送時に本物の数が多い宛てのメッセージに適しています。 不確実性と、本物でメッセージを送信する時点でオンラインあるかどうかに関する心配することの不便さを削除します。 メッセージは、受信者がメッセージを受信する準備がすぐに配信されます。 その結果、多数の異なるタイム ゾーンのうちいくつかあります本物を個々 の命令、確認、およびレポートを送信するための望ましい方法を提供します。  
  
- **リアルタイム メッセージング。** リアルタイム メッセージングは、格納および転送時にオンラインになっている本物宛てのメッセージを転送する低コストの選択肢を提供します。 その結果、いくつかの大規模な相手に、またはインフラストラクチャを市場に投入するメッセージに対して、個々 の命令、確認、およびレポートを送信するために最適です。  
  
  (メッセージのメッセージごと) に省略可能な SWIFTNet 対話機能は次のとおりです。  
  
- **メッセージの優先度。** メッセージは、本物の処理を適切なために、メッセージの「緊急」としてフラグを設定することができます。  
  
- **配信通知 (ストア アンド フォワード モード)。** 相手がメッセージを受信することの確認を提供します。  
  
- **出力と受信の非否認します。** に関して問題が発生した場合は、メッセージ交換が行われるように要求を確認する SWIFT を使用できます。  
  
  標準の SWIFTNet 対話機能には、SWIFTNet PKI のセキュリティが含まれます。 SWIFTNet FileAct は SWIFTNet PKI を使用して保護し、メッセージの認証と整合性の制御を提供します。  
  
  すべてのメッセージと SWIFTNet で交換されるファイルは、ユーザーをバイパスできませんセキュリティ、検証、およびプラットフォームのルーティング規則のことを確認する一連の一般的に行われます。 これらのチェックは、SWIFTAlliance ゲートウェイ (SAG) アプリケーションによって実行されます。  
  
## <a name="see-also"></a>参照  
 [概要 FileAct および InterAct アダプター](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [SWIFTNet とは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [FileAct アダプターとは](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)