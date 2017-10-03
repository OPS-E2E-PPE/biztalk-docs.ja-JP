---
title: "アダプター フレームワークについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 648c22a52e543b24458daa73146836e1e3a5463e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-adapter-framework"></a>アダプター フレームワークについて
BizTalk Server アダプター フレームワークは、すべてのアダプターで実装するための、または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージング エンジンによる作業にアクセスするための、安定したオープンなメカニズムを提供します。 説明されているインターフェイス、 **Microsoft.BizTalk.Adapter.Framework**名前空間には、構成のプロパティ ページを変更する手段を提供するアダプターが有効にします。 これは、サービスやスキーマを BizTalk プロジェクトにインポートする手段でもあります。  
  
 次の図は、アダプターとアダプター フレームワークがどのように連動してアプリケーションを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に接続するかを示しています。  
  
 ![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
 次の手順では、この図に示されている一連の手順を説明します。  
  
1.  データの受信は、指定のアドレスで特定のプロトコルのメッセージを待ち受けている受信場所で行われます。 受信場所は、アダプターと受信パイプラインに関連付けられています。 あらかじめ決められたプロトコルのメッセージに対して特定のロジックを実行するように、アダプター コンポーネントとパイプライン コンポーネントの両方を構成することができます。  
  
2.  受信場所でメッセージが受信されると、メッセージがアダプターに送信され、そこで新しい BizTalk メッセージが作成されます。アダプターは、データ ストリームをメッセージ (通常はメッセージのボディ部内) に添付し、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージをメッセージング エンジンに送信します。  
  
3.  メッセージング エンジンが受信パイプラインにメッセージを送信すると、そこでデータが XML に変換され、メッセージの送信者が認証されます。さらに、メッセージの解読および XML の検証が行われます。  
  
4.  メッセージング エンジンは、メッセージをメッセージ ボックス データベースに公開します。 メッセージ ボックスとは、処理するメッセージが含まれている Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] テーブルです。 オーケストレーションと送信ポートの両方が、メッセージ ボックスをサブスクライブできます。  
  
5.  メッセージング エンジンは、サブスクライバーのフィルターの仕様セットに一致するメッセージ コンテキストのプロパティに基づいて、メッセージをオーケストレーションまたは送信ポートのサブスクライバーにメッセージを送信します。  
  
6.  オーケストレーションがサブスクライバーの場合、処理されたメッセージは送信ポートを通じて送信されます。 サブスクライバーが送信ポートの場合、メッセージは回線で送信される前に送信パイプラインを通じて送信アダプターに渡されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプター フレームワーク ツールを使用します。](../core/using-the-adapter-framework-tools.md)  
  
-   [アダプターのメッセージ交換パターン](../core/adapter-message-exchange-patterns.md)  
  
-   [アダプター フレームワーク コンポーネント](../core/adapter-framework-components.md)  
  
-   [アダプターのホスト モデル](../core/adapter-hosting-model.md)  
  
-   [アダプター コンポーネント](../core/adapter-components.md)