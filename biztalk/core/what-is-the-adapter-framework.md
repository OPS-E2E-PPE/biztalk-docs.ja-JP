---
title: アダプター フレームワークとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd96ab8287a3c8d02bb612d4595c9f418e566eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243217"
---
# <a name="what-is-the-adapter-framework"></a>アダプター フレームワークとは何ですか。
BizTalk アダプター フレームワークは、実装またはからの作業にアクセスするすべてのアダプターを開き、安定したメカニズムを提供しています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージング エンジン。 説明されている、インターフェイス、 **Microsoft.BizTalk.Adapter.Framework**名前空間の構成プロパティ ページを変更する手段を提供するアダプターを有効にします。 サービスとスキーマを BizTalk プロジェクトにインポートするための手段にもなります。  
  
 次の図は、アダプターとアダプター フレームワークがどのように連携して、アプリケーションを接続する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 ![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
 次の手順では、この図に示す手順の順序について説明します。  
  
1. データは、指定されたアドレスで特定のプロトコルでメッセージをリッスンする受信場所から受信されます。 受信場所は、アダプターと受信パイプラインに関連付けられます。 アダプターとパイプライン コンポーネントがあらかじめ決められたプロトコルのメッセージに対して特定のロジックを実行するを構成することができます。  
  
2. 受信場所でメッセージを受信すると、メッセージは、新しい BizTalk メッセージを作成、データ ストリームをアタッチします (通常のメッセージのボディ部) のメッセージに、どのエンドポイントに関するメタデータを追加すると、アダプターに送信されデータは、受信したし、メッセージング エンジンにそのメッセージを送信します。  
  
3. メッセージング エンジンは、場所データが XML に変換、メッセージの送信者の認証、メッセージを復号化、および XML の検証、受信パイプラインにメッセージを送信します。  
  
4. メッセージング エンジンは、メッセージ ボックス データベースにメッセージを発行します。 メッセージ ボックスは、Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]処理されるメッセージを含むテーブル。 両方のオーケストレーションおよび送信ポートは、メッセージ ボックス データベースにサブスクライブできます。  
  
5. メッセージング エンジンは、オーケストレーションまたは送信ポートのサブスクライバー、サブスクライバーのフィルターで一連の仕様に一致するメッセージ コンテキスト プロパティに基づいて、メッセージを送信します。  
  
6. オーケストレーションがサブスクライバーの場合は、メッセージを処理して、送信ポートを通じて送信されます。 場合は、サブスクライバーに、メッセージは、送信パイプラインを通じて送信アダプターに送信される前に送信されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプター フレームワーク ツールの使用](../core/using-the-adapter-framework-tools.md)  
  
-   [アダプターのメッセージ交換パターン](../core/adapter-message-exchange-patterns.md)  
  
-   [アダプター フレームワーク コンポーネント](../core/adapter-framework-components.md)  
  
-   [アダプターのホスト モデル](../core/adapter-hosting-model.md)  
  
-   [アダプター コンポーネント](../core/adapter-components.md)