---
title: アダプターを操作しますか? | Microsoft Docs
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
ms.openlocfilehash: 25877b95a440faef802d3d2ba7861687d7e4b108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224754"
---
# <a name="what-is-the-interact-adapter"></a>アダプターを操作しますか?
対話 SWIFTNet のアダプタでは、メッセージの転送を BizTalk Server と SWIFT セキュリティで保護された IP ネットワーク (SIPN) 間の接続を提供します。 SIPN は、金融機関、金融業界インフラストラクチャ、および顧客の相互接続をセキュリティで保護されたプライベート ネットワーク経由でメッセージとファイルを転送します。 InterAct アダプターは、SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) s、SIPN への接続に使用します。  
  
 SWIFTNet 対話安全性と信頼性の高いメッセージ交換の各構造化された財務を提供します。 SWIFT の顧客のメッセージングの要件は、お客様がメッセージも異なります。  
  
 次の機能がサポートされています。  
  
-   PKI のセキュリティ  
  
-   メッセージの検証  
  
-   構成可能なサーバーの全体のルーティング  
  
-   メッセージの優先順位  
  
-   ストアおよび転送メッセージの配信通知  
  
-   否認不可の出力と受信確認のです。  
  
 アダプターを使用する対話 SWIFTNet の外部から提供されるアプリケーションとの対話機能を活用します。 このアダプターには、転送、および監査したりしません exchange プリミティブを除き、メッセージの内容を確認するメッセージの内容に関する情報がありません。  
  
## <a name="interact-message-exchange"></a>InterAct メッセージ交換  
 SWIFTNet 対話安全性と信頼性の高いメッセージ交換の各構造化された財務を提供します。 SWIFT の顧客のメッセージングの要件は、お客様がメッセージも異なります。 SWIFTNet 対話は、多様な通信モードがあります。  
  
-   **ストア アンド フォワードのメッセージング** ストア アンド フォワードの SWIFTNet 対話の機能は、多数のユーザーの多くできない可能性がありますオンライン転送時に、見宛てのメッセージに適しています。 不確実性とするかどうか、ユーザーはオンライン時のメッセージを送信する心配不便さを削除します。 メッセージは受信者がメッセージを受信する準備がすぐに配信されます。 その結果、多数のうち一部異なるタイム ゾーンでは、相手に個々 の命令、確認、およびレポートを送信するための望ましい方法を提供します。  
  
-   **リアルタイムのメッセージングです。** リアルタイムのメッセージング、格納および転送時にオンラインになっている見宛てのメッセージの転送に低コストの代替手段が用意されています。 その結果、いくつかの大きな見または市場のインフラストラクチャへのメッセージの個別の命令、確認、およびレポートを送信するために最適です。  
  
 (メッセージのメッセージごと) に省略可能な SWIFTNet 対話機能は次のとおりです。  
  
-   **メッセージの優先度。** メッセージは、メッセージで、適切な相手の処理を許可する「緊急」としてフラグを設定することができます。  
  
-   **配信通知 (ストア アンド フォワード モード)。** 相手がメッセージを受信することの確認は、します。  
  
-   **否認不可の出力と受信します。** に関して問題が発生した場合、メッセージ交換が行われるように要求を確認する SWIFT を使用できます。  
  
 標準の SWIFTNet 対話機能には、SWIFTNet PKI のセキュリティが含まれます。 SWIFTNet FileAct は SWIFTNet PKI を使用して保護し、メッセージの認証と整合性の制御を提供します。  
  
 すべてのメッセージと SWIFTNet で交換されるファイルには、一般的な一連のあるユーザーをバイパスできませんセキュリティ、検証、およびプラットフォームのルーティング規則を確認するチェックが行われます。 これらのチェックは、SWIFTAlliance ゲートウェイ (SAG) アプリケーションによって実行されます。  
  
## <a name="see-also"></a>参照  
 [入門、FileAct および InterAct アダプター](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [SWIFTNet とは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [FileAct アダプターとは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)