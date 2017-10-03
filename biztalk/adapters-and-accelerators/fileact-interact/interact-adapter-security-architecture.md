---
title: "アダプターのセキュリティ アーキテクチャを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4924b8c-1fda-4a0c-b9be-8f2ccba38013
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de0eee57daec102507a9e502e3146e1cfcdec723
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-security-architecture"></a>アダプターのセキュリティ アーキテクチャを対話します。
メッセージの送信および受信確認のセキュリティは、SWIFTNet リンク (SNL) と SWIFTAlliance ゲートウェイ (SAG) に固有の証明書と暗号化の機能を使用して実装されます。 SWIFT では、サービスが、「エンド ツー エンド」署名の適用に対話するために設計されていることをお勧め、つまり、メッセージの要求と応答の両方に署名します。  
  
 暗号化操作は、SWIFTNet リンクのセキュリティ モジュールによって実装されます。 このモジュールは、署名および PKI のキーを使用して暗号化を許可します。 暗号操作の範囲と性質は、Api に渡される要求と応答のコントロールのデータ構造の一部として指定されます。  
  
 SWIFTNet は、署名/暗号化 RequestPayload または ResponsePayload のサポートされています。 また RequestHeader または ResponseHeader を署名することができます。  
  
## <a name="signingencrypting-requests-and-responses"></a>署名と暗号化の要求と応答  
 要素の SWIFTNet 対話要求で暗号化操作を適用するための規則は次のとおりです。  
  
-   RequestControl: この宛て SWIFTNet のみです。 SWIFTNet は、応答側 (および、要求元に対してもいくつかの要素) を RequestDescriptor を提供します。 そのため、クライアント プロセス サーバー プロセスの暗号化操作を実行できますないにします。  
  
-   RequestE2EControl: この要素には、エンド ツー エンドの信頼性の高いメッセージングを確実に情報が含まれています。 暗号化操作ができません。  
  
-   RequestHeader: SWIFTNet によって使用される、伝達する応答側に変更します。 そのため、こののみ署名できます。  
  
-   RequestPayload: このした暗号化操作を実行できます。  
  
-   暗号要素: この要求で以前にアクティブ化された暗号化操作に関連してこれらです。 これらの暗号化操作ができません。  
  
 SWIFTNet 対話の応答の暗号化関数を適用するための規則は次のとおりです。  
  
-   ResponseControl: この宛て SWIFTNet のみです。 SWIFTNet は、要求元に、ResponseDescriptor を提供します。 そのため、クライアント プロセスの暗号操作では、サーバー プロセスできますありません自体に対して実行します。  
  
-   ResponseE2EControl: この要素には、エンド ツー エンドの信頼性の高いメッセージングを確実に情報が含まれています。 暗号化操作ができません。  
  
-   ResponseHeader: この要素は署名することができます (に転送される変更されず、要求元)。  
  
-   ResponsePayload: を暗号化および署名されたことができます。  
  
-   暗号要素: この要求で以前にアクティブ化された暗号化操作に関連してこれらです。 これらの暗号化操作ができません。  
  
## <a name="receiving-requests-with-cryptography"></a>暗号化と要求を受信  
 サーバー プロセスが暗号化操作対象となる、要求元によって要求が受信可能性があります。 受信要求には、逆方向の暗号化操作を有効にするすべての関連情報が含まれています。 CryptoInternal 情報では、暗号化の解除および検証の関数は効果的に動作ようになりました。  
  
 サーバー プロセスを実行する復号化ニーズの DN のセキュリティ コンテキストをアクティブ化する必要があります。  
  
 暗号操作を反転して、要求を修正し、されます (確認、暗号化を解除) ように、元の要求を作成する使用可能な変更を加えず server プロセスにクライアントを暗号化する処理で最初に配信された、操作です。 応答に類似した処理が行わします。 署名の検証は確認されないことのみが署名された新機能を実現する変更されていない、ですが、署名者が本物かどうかのどちらを認証することが重要です。 これは、SignDN が有効な証明書を使用する必要があります。 有効な証明書が証明書がされていません (SWIFTNet 内に一元的に維持され、証明書失効リスト内の参照) を失効します。  
  
## <a name="activation"></a>アクティブ化  
 SWIFTNet リンクは、検証とすべての着信要求および着信自動モードで復号化を操作できる応答します。 つまり、SWIFTNet リンクが自動的に処理する (ことを確認および解除) 要求 (サーバー側) または着信応答 (クライアント側) のすべての着信をブロックする最後の暗号です。 前提条件 (復号化は要求された場合)、復号化に必要なセキュリティ コンテキストが開かれていると (この設定を自動モードを行うに Sw:InitRequest または Sw:HandleInitResponse で自動モードで SWIFTNet リンクが初期化されています。「自動」に CryptoMode を設定またはまだ"Advanced"対話するためのより強力なです。 (は常に"Advanced"を使用対話アダプターは、これにより、クライアントまたはサーバー アプリケーションはフォームを回復すると、リモート側で、または期限切れの証明書から予期しない暗号化します。  
  
 SWIFTNet リンクでは、署名と 1 つの送信要求 (または 1 つの送信応答) に自動的に暗号化を"TRUE"(応答) の要求の RequestControl (ResponseControl) で RequestCrypto (ResponseCrypto) フィールドが初期化される場合に動作します。  
  
 その場合は SWIFTNet リンクは、最後の暗号ブロックを処理します。 前提条件は、(必要な署名の署名を要求すると)、セキュリティ コンテキストが開かれている、暗号ブロックが存在することと、署名と暗号化のために必要な上で要求 RequestCrypto (ResponseCrypto)フラグは、RequestControl (ResponseControl) に"TRUE"に設定されます。 これは、常に、クライアントまたはサーバーの初期化に使用される CryptoMode に関係なく、します。  
  
## <a name="see-also"></a>参照  
 [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [アダプター否認不可を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)