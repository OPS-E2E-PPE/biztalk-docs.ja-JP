---
title: WCF アダプターに関する FAQ:サービス アーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8bad0063-ccff-41f4-b4e0-a02b49403c2d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cf46334fe3c40b222552c97115bc7758134c7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393591"
---
# <a name="wcf-adapter-faq-service-architecture"></a>WCF アダプターに関する FAQ:サービスのアーキテクチャ
## <a name="what-is-the-difference-between-a-wcf-custom-behavior-and-a-biztalk-pipeline-component"></a>WCF カスタム動作と BizTalk パイプライン コンポーネントの違いは何ですか。  
 初期の検査時に WCF カスタム動作は従来の BizTalk パイプラインとほぼ同じです。 両方は、その宛先にメッセージの流れを中断、カスタム メッセージの処理を実行するメッセージのインターセプトの基本的な概念を活用して、その宛先に転送します。 (送信ポートにバインド) した後、BizTalk Server でメッセージの処理がまたはこのインターセプションの (受信場所にバインド) する前にいずれかで発生することができます。 インターセプションの時点からも実装でだけでなく、2 つのメソッド内でこのインターセプションがどのように行われるかは異なります。 違いの一部を次に示します。  
  
-   パイプラインは、オーケストレーションで使用できます。 WCF の動作は、BizTalk Server 内から WCF アダプターによって呼び出されるに制限されます。  
  
-   パイプラインは、BizTalk Server に固有の古い技術です。 BizTalk Server で、またはその他の純粋な WCF シナリオでは、WCF の動作を使用できます。  
  
-   パイプライン (デコード、検証など) のセットのパイプライン ステージ以内に居住します。WCF の動作は、(後ほど説明)、4 つのインターセプション エントリ ポイントのいずれかでメッセージ フローに接続することができます。  
  
-   パイプラインは、純粋な実行時の機能です。 WCF 動作も同様です中は、リレーショナルできますも強制または BizTalk Server 管理コンソール内から構成中に、値のデータの制約を設定します。  
  
-   パイプラインは、WCF の動作が WCF メッセージに対し、BizTalk メッセージを操作できます。 つまり、パイプラインは、WCF の動作が WCF メッセージ プロパティにアクセスできますが、BizTalk コンテキスト プロパティの昇格などの操作を実行できます。  
  
-   WCF または WCF アダプタでのマルチパート メッセージのモデルはありません。 ただし、パイプライン コンポーネントは、する必要がある任意の方法で BizTalk メッセージを操作できる、ために、必要に応じてマルチパート メッセージを処理ができます。  
  
## <a name="for-the-receive-locations-or-send-ports-using-the-wcf-basichttp-and-wcf-wshttp-adapters-what-type-of-encoding-should-i-select"></a>受信場所または送信ポートを Wcf-basichttp と Wcf-wshttp アダプターを使用してでは、エンコードの種類に選択します。  
 各アダプターには HTTP ベースのメッセージ、テキスト エンコードです。 メッセージのエンコードには、MTOM (Message Transmission Organization Mechanism) またはテキストのいずれかであると、メッセージに使用される SOAP エンコーダーを指定します。 テキストが選択されている場合、テキスト エンコードを選択してください。 この選択肢は、unicodeFFF (ビッグ エンディアン)、utf-16 (16 ビット エンコード)、および utf-8 (8 ビット エンコード) です。  
  
 MTOM は、バイナリ データの最も効率的な転送を推奨されるメカニズムです。 ただし、サービスは MTOM データを処理できることと、これにより、このオプションは、テキスト形式に比べ移植性は劣りますが必要です。 標準的な非バイナリのデータを転送する場合、MTOM はテキスト オプションを使用するより非効率実際にはことができます。 テキストは、一般的に受け付けられるし、により、複数のプラットフォーム間相互運用性が転送されるデータには、テキスト以外のコンテンツが含まれている場合、2 つの非効率の選択肢となります。 これは、WCF サービス コントラクトを使用する場合にバインディング エンコード選択肢を選択する際に重要な要素です。 WCF 操作で転送するデータとプロセスを理解するには、メッセージ エンコーディングの正しい選択に影響します。