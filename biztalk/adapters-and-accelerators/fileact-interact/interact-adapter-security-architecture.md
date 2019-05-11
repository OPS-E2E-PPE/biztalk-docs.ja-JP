---
title: InterAct アダプターのセキュリティ アーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4924b8c-1fda-4a0c-b9be-8f2ccba38013
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 445f62df17c45b80d7be83b9e9283f091e797fb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366654"
---
# <a name="interact-adapter-security-architecture"></a>InterAct アダプターのセキュリティ アーキテクチャ
SWIFTNet リンク (SNL) と SWIFTAlliance ゲートウェイ (SAG) に固有の証明書と暗号化機能を使用して、メッセージの送信と受信確認のセキュリティが実装されます。 SWIFT では、サービスが、「エンド ツー エンド」署名の適用に対話するために設計されていることをお勧め-は、メッセージの要求と応答の両方に署名します。  
  
 暗号化操作は、SWIFTNet リンクのセキュリティ モジュールによって実装されます。 このモジュールは、署名および PKI のキーを使用して暗号化できます。 性質と程度の暗号操作は、Api に渡される要求と応答のコントロールのデータ構造の一部として指定されます。  
  
 SWIFTNet、署名と暗号化の RequestPayload または ResponsePayload をサポートします。 また、RequestHeader または ResponseHeader を署名することができます。  
  
## <a name="signingencrypting-requests-and-responses"></a>署名と暗号化の要求と応答  
 SWIFTNet 操作要求の要素の暗号化操作を適用するための規則は次のとおりです。  
  
- RequestControl: これは宛て SWIFTNet のみです。 SWIFTNet は、応答側 (および、申請者にもいくつかの要素) を RequestDescriptor を配信します。 そのため、サーバー プロセスの暗号化操作にクライアント プロセスでく実行がありません。  
  
- RequestE2EControl: この要素には、エンド ツー エンドの信頼性の高いメッセージングを確実に情報が含まれています。 暗号化操作を実行できないことができます。  
  
- RequestHeader: SWIFTNet で使用される、伝達する応答側に変更します。 そのため、これは署名のみ。  
  
- RequestPayload: この暗号化操作を実行できます。  
  
- 個の要素を暗号化します。 この要求にアクティブだったの暗号化操作に関連これら。 これらの暗号化の操作を実行しないことができます。  
  
  SWIFTNet 操作の応答の暗号化関数を適用するための規則は次のとおりです。  
  
- ResponseControl: これは宛て SWIFTNet のみです。 SWIFTNet は、要求元に、ResponseDescriptor を提供します。 そのため、クライアント プロセスの暗号化操作にサーバー プロセスでく実行がありません。  
  
- ResponseE2EControl: この要素には、エンド ツー エンドの信頼性の高いメッセージングを確実に情報が含まれています。 暗号化操作を実行できないことができます。  
  
- ResponseHeader: この要素は署名することができます (に転送される変更要求元)。  
  
- ResponsePayload: は暗号化および署名できます。  
  
- 個の要素を暗号化します。 この要求にアクティブだったの暗号化操作に関連これら。 これらの暗号化の操作を実行しないことができます。  
  
## <a name="receiving-requests-with-cryptography"></a>暗号化方式による要求の受信  
 サーバー プロセスは、要求元が対象の暗号化操作になっている要求を受信可能性があります。 受信要求には、逆方向の暗号化操作を有効にするすべての関連情報が含まれています。 CryptoInternal 情報では、復号化と検証の関数は効果的に動作ようになりました。  
  
 サーバー プロセスは復号化を行う必要があります。 の DN のセキュリティ コンテキストをアクティブ化する必要があります。  
  
 要求は逆方向の暗号化操作によって変更する (確認、暗号化を解除) このような方法で元の要求が使用できることをそのまま、サーバー プロセス、暗号化にクライアント プロセスで最初に配信された、操作です。 応答には、類似した処理が行わします。 署名の検証は検証ないことのみ署名された内容を理解するに変更されていないが、署名者が正規品であるかどうかのどちらを認証することが重要です。 これは、SignDN が有効な証明書を使用する必要があります。 有効な証明書が証明書が失効 (SWIFTNet 内に一元的に保持される、証明書失効リスト内の参照)。  
  
## <a name="activation"></a>アクティブ化  
 検証と自動モードですべての受信要求と受信用の暗号化解除を行える SWIFTNet リンク応答します。 つまり、SWIFTNet リンクが自動的に処理される (ことを確認し、復号化) 最後の暗号化を要求 (サーバー側) または着信応答 (クライアント側) のすべての着信ブロックします。 前提条件は暗号化解除 (復号化が要求される) 場合に必要なセキュリティ コンテキストが開かれていると (この設定を自動モードは Sw:InitRequest または Sw:HandleInitResponse、自動モードで SWIFTNet リンクが初期化されています。「自動」に CryptoMode の設定や、まだ「の高度な」対話の向上します。 (常に"Advanced"を使用対話アダプターは、これにより、クライアントまたはサーバー アプリケーションはフォームを回復すると、リモート側によって、または期限切れの証明書から予期しない暗号化します。  
  
 SWIFTNet リンクでは、署名と 1 つの送信要求 (または 1 つの送信応答) に自動的に暗号化を要求 (応答) の RequestControl (ResponseControl) では"TRUE"RequestCrypto (ResponseCrypto) フィールドが初期化されている場合に動作します。  
  
 その場合は SWIFTNet リンクは、最後の暗号ブロックを処理します。 前提条件は次の署名 (署名が要求する) 場合に必要なセキュリティ コンテキストが開かれている、暗号化ブロックがの署名と暗号化のために必要な上で要求に存在する RequestCrypto (ResponseCrypto)フラグは、RequestControl (ResponseControl) で"TRUE"に設定されます。 これは、常に、クライアントまたはサーバーの初期化に使用される CryptoMode に関係なく。  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)