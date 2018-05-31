---
title: サポートのパイプライン コンポーネントを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df0346ea-15d4-49c5-98d8-f9ec06f4e036
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6313a337e8527f3fb275f7c15745a5a7f6552151
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295602"
---
# <a name="using-the-pipeline-support-components"></a>パイプラインのサポート コンポーネントを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のパイプライン コンポーネントが含まれています。  
  
-   **ESB Itinerary セレクター**です。 (受信パイプライン) の受信側でこのコンポーネントを使用すると、メッセージに従ってをサーバー側の日程を選択します。 詳細については、次を参照してください。 [ESB 行程セレクター コンポーネント](../esb-toolkit/the-esb-itinerary-selector-component.md)です。  
  
-   **ESB 行程**です。 (受信パイプライン) の受信側でこのコンポーネントを使用すると、SOAP ヘッダーの ESB メタデータ プロパティをメッセージ コンテキストに昇格します。 詳細については、次を参照してください。 [ESB 行程コンポーネント](../esb-toolkit/the-esb-itinerary-component.md)です。  
  
-   **ESB Itinerary フォワーダー**です。 詳細については、次を参照してください。 [ESB 行程フォワーダー コンポーネント](../esb-toolkit/the-esb-itinerary-forwarder-component.md)です。  
  
-   **ESB Itinerary キャッシュ**です。 キャッシュの日程をこのコンポーネントを使用し、送信請求-応答送信ポートで受信した応答メッセージを再適用できます。 詳細については、次を参照してください。 [ESB 行程コンポーネント](../esb-toolkit/the-esb-itinerary-component.md)です。  
  
-   **ESB JMS デコーダー**です。 このコンポーネントを IBM JMS (MQRFH2) ヘッダーを解析し、それらを保持するコンテキスト プロパティとしてオーケストレーションまたは送信ポートの受信側 (受信場所) 内で使用できます。 これらのコンテキスト プロパティにアクセスし、その他の BizTalk コンテキスト プロパティと同じ方法でこれらを変更できます。 詳細については、次を参照してください。 [、ESB JMS エンコーダーおよびデコーダー コンポーネント](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)です。  
  
-   **ESB JMS エンコーダー**です。 このコンポーネントは、メッセージに IBM JMS (MQRFH2) ヘッダーを書き込む送信ポートで使用できます。 詳細については、次を参照してください。 [、ESB JMS エンコーダーおよびデコーダー コンポーネント](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)です。  
  
-   **ESB 追加 Namespace**です。 受信場所または送信ポートのいずれかでこのコンポーネントを使用して、XML ドキュメントに名前空間を追加することができます。 詳細については、次を参照してください。 [、ESB 追加 Namespace と Namespace コンポーネントの削除](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)です。  
  
-   **ESB 削除 Namespace**です。 受信場所または送信ポートのいずれかでこのコンポーネントを使用して、XML ドキュメントから名前空間を削除することができます。 詳細については、次を参照してください。 [、ESB 追加 Namespace と Namespace コンポーネントの削除](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)です。  
  
-   **ESB 例外エンコーダー**です。 このコンポーネントを使用すると、ファイル システム、Microsoft InfoPath の場合、または Microsoft SharePoint にフォールト メッセージを送信します。 このコンポーネントは、ESB 例外処理メカニズムの一部で、それを正規化し、送信ポートによって処理されるすべての例外を拡充します。 すべてのメッセージが含まれているように正規の形式にシリアル化 (埋め込みの永続化されたメッセージとコンテキスト プロパティを含む) の例外情報をコンポーネント自体は、例外があるとします。  
  
-   **ESB 変換**です。 このコンポーネントを使用して、BizTalk マップを指定することで 1 つの形式から別のメッセージを変換することができます。  
  
-   **ESB BAM の追跡ツール**です。 このコンポーネントを使用して、ESB 例外エンコーダーから生成されたエラー メッセージをインターセプトし、BAM プライマリ インポート テーブル (ストリームを使用して、BAM イベント パイプラインの) メッセージにデータを挿入することができます。 このコンポーネントは、ESB 例外処理メカニズムの一部です。  
  
-   **ESB ディスパッチャー**です。 受信場所 (受信パイプライン) でこのコンポーネントを使用すると、送信メッセージのエンドポイントの場所のプロパティを動的に設定します。 送信パイプラインでこのコンポーネントを使用して、itinerary メッセージング サービスを実行することができますも。 詳細については、次を参照してください。 [ESB ディスパッチャー コンポーネント](../esb-toolkit/the-esb-dispatcher-component.md)です。  
  
-   **ESB ディスパッチャーを逆アセンブル**です。 受信場所 (受信パイプライン) でこのコンポーネントを使用すると、送信メッセージのエンドポイントの場所のプロパティを動的に設定します。 結果にメッセージを変換する点を除いて、このコンポーネントの動作は、ESB ディスパッチャー コンポーネントに似ています (値を指定する場合、 **MapName**プロパティ)。 メッセージは、プロパティおよびメッセージの種類を昇格する XML 逆アセンブラーを通過します。 ESB ディスパッチャーの逆アセンブル コンポーネントには、異なるエンドポイントへの複数のメッセージのバッチのディスパッチもサポートしています。 詳細については、次を参照してください。 [ESB ディスパッチャーを逆アセンブル コンポーネント](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)です。