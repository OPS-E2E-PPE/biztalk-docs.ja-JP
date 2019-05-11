---
title: パイプライン サポート コンポーネントを使用して |Microsoft Docs
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
ms.openlocfilehash: 3645649bb7c284fe4ab486a9851b2e680de70f8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396386"
---
# <a name="using-the-pipeline-support-components"></a>パイプライン サポート コンポーネントを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のパイプライン コンポーネントが含まれています。  
  
-   **ESB スケジュール セレクター**します。 (受信パイプライン) の受信側でこのコンポーネントを使用すると、メッセージを次のサーバー側の旅行プランを選択します。 詳細については、次を参照してください。 [ESB スケジュール セレクター コンポーネント](../esb-toolkit/the-esb-itinerary-selector-component.md)します。  
  
-   **ESB 行程**します。 このコンポーネントは、SOAP ヘッダーから ESB メタデータ プロパティをメッセージ コンテキストに昇格させる (受信パイプライン) の受信側で使用できます。 詳細については、次を参照してください。 [ESB スケジュール コンポーネント](../esb-toolkit/the-esb-itinerary-component.md)します。  
  
-   **ESB スケジュール フォワーダー**します。 詳細については、次を参照してください。 [ESB スケジュール フォワーダー コンポーネント](../esb-toolkit/the-esb-itinerary-forwarder-component.md)します。  
  
-   **ESB スケジュール キャッシュ**します。 このコンポーネントを使用してキャッシュをスケジュールし、送信請求-応答送信ポートで受信した応答メッセージを再適用できます。 詳細については、次を参照してください。 [ESB スケジュール コンポーネント](../esb-toolkit/the-esb-itinerary-component.md)します。  
  
-   **ESB JMS デコーダー**します。 このコンポーネントは、IBM JMS (MQRFH2) ヘッダーを解析し、コンテキスト プロパティとして保持するために (受信場所) では、オーケストレーションや送信ポートの受信側で使用できます。 これらのコンテキスト プロパティにアクセスし、その他の BizTalk コンテキスト プロパティと同じ方法で変更できます。 詳細については、次を参照してください。 [、ESB JMS エンコーダーとデコーダー コンポーネント](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)します。  
  
-   **ESB JMS エンコーダー**します。 このコンポーネントは、メッセージに IBM JMS (MQRFH2) ヘッダーを書き込む送信ポートで使用できます。 詳細については、次を参照してください。 [、ESB JMS エンコーダーとデコーダー コンポーネント](../esb-toolkit/the-esb-jms-encoder-and-decoder-components.md)します。  
  
-   **ESB 追加 Namespace**します。 受信場所または送信ポートのいずれかでこのコンポーネントを使用して、XML ドキュメントに名前空間を追加することができます。 詳細については、次を参照してください。 [、ESB 追加 Namespace と Namespace コンポーネントの削除](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)します。  
  
-   **ESB 削除 Namespace**します。 受信場所または送信ポートのいずれかでこのコンポーネントを使用して、XML ドキュメントから名前空間を削除することができます。 詳細については、次を参照してください。 [、ESB 追加 Namespace と Namespace コンポーネントの削除](../esb-toolkit/the-esb-add-namespace-and-remove-namespace-components.md)します。  
  
-   **ESB 例外エンコーダー**します。 このコンポーネントを使用して、Microsoft InfoPath の場合、または Microsoft SharePoint、ファイル システムにエラー メッセージを送信することができます。 このコンポーネントは、ESB 例外処理機構の一部とそれを正規化し、送信ポートによって処理されるすべての例外を拡充します。 すべてのメッセージが含まれているように、正規の形式にシリアル化 (埋め込みの永続化されたメッセージとコンテキストのプロパティを含む) の例外情報をコンポーネント例外自体があるとします。  
  
-   **ESB 変換**します。 このコンポーネントを使用して、BizTalk マップを指定することで、1 つの形式から別のメッセージを変換することができます。  
  
-   **ESB BAM の追跡ツール**します。 このコンポーネントを使用して、ESB 例外のエンコーダーから生成されたエラー メッセージをインターセプトし、メッセージで (パイプラインの BAM イベント Stream を使用して) BAM プライマリ インポート テーブルにデータを挿入することができます。 このコンポーネントは、ESB 例外処理メカニズムの一部です。  
  
-   **ESB ディスパッチャー**します。 受信場所 (受信パイプライン) でこのコンポーネントを使用すると、送信メッセージのエンドポイントの場所のプロパティを動的に設定します。 スケジュール オンランプ メッセージング サービスを実行するのに、送信パイプラインでこのコンポーネントを使用することもできます。 詳細については、次を参照してください。 [ESB ディスパッチャー コンポーネント](../esb-toolkit/the-esb-dispatcher-component.md)します。  
  
-   **ESB ディスパッチャー逆アセンブル**します。 受信場所 (受信パイプライン) でこのコンポーネントを使用すると、送信メッセージのエンドポイントの場所のプロパティを動的に設定します。 結果メッセージを変換する点を除いて、このコンポーネントの動作は、ESB ディスパッチャー コンポーネントに似ています (の値を指定する場合、 **MapName**プロパティ)。 メッセージは、プロパティとメッセージの種類を促進する、XML 逆アセンブラーを通過します。 ESB ディスパッチャー逆アセンブル コンポーネントには、複数のメッセージをさまざまなエンドポイントのバッチのディスパッチもサポートしています。 詳細については、次を参照してください。 [、ESB ディスパッチャー逆アセンブル コンポーネント](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)します。