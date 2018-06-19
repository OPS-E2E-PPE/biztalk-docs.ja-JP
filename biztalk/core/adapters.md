---
title: アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- adapters
- send adapters
- adapters, about adapters
- send adapters, about send adapters
- receive adapters, about receive adapters
- adapters, adapter framework
- receive adapters
- adapters, send adapters
ms.assetid: 7803a806-3396-4662-877f-eae11cb5e3e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a7f58a9d67b9702cfbb7b21788f751717ac61e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230098"
---
# <a name="adapters"></a>アダプタ
Microsoft BizTalk Server では、外部のシステム、アプリケーション、およびエンティティとメッセージを交換するために、アダプターの概念を使用します。 *アダプター* com またはします。NET ベースのコンポーネントとビジネス エンドポイント (ファイル システム、データベース、カスタム ビジネス アプリケーションなど) からメッセージを転送するさまざまな通信プロトコルを使用します。  
  
 BizTalk Server では、送受信操作において外部のエンティティとメッセージを交換するためにアダプターを使用します。  
  
-   送信 (送信側) 操作とは、アダプターでサポートされているプロトコルを使用して、BizTalk Server が外部エンティティに情報を送信することをいいます。  
  
-   受信 (受信側) 操作とは、アダプターが外部エンティティから情報を受信し、BizTalk Server メッセージング エンジンにその情報を渡すことをいいます。  
  
## <a name="the-adapter-framework"></a>アダプター フレームワーク  
 次の図は、アダプターとアダプター フレームワークがどのように連動してアプリケーションを BizTalk Server に接続するかを示しています。  
  
1.  データは、指定したアドレスで特定のプロトコルのメッセージをリッスンしている受信場所を介して受信されます。 受信場所は、アダプターと受信パイプラインに関連付けられています。 あらかじめ決められたプロトコルを持つメッセージに対して特定のロジックを実行するように、アダプター コンポーネントとパイプライン コンポーネントの両方を構成することができます。  
  
2.  受信場所でメッセージが受信されると、メッセージがアダプターに送信され、そこで新しい BizTalk Server メッセージが作成されます。アダプターは、データ ストリームをメッセージ (通常はメッセージのボディ部内) に添付し、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージをメッセージング エンジンに送信します。  
  
3.  メッセージング エンジンが受信パイプラインにメッセージを送信すると、そこでデータが XML に変換され、メッセージの送信者が認証されます。さらに、メッセージの解読および XML の検証が行われます。  
  
4.  メッセージング エンジンは、メッセージをメッセージ ボックスに公開します。 メッセージ ボックスとは、処理するメッセージが含まれている Microsoft SQL Server テーブルです。 オーケストレーションと送信ポートの両方が、メッセージ ボックスをサブスクライブできます。  
  
5.  メッセージング エンジンは、サブスクライバーのフィルターの仕様セットに一致するメッセージ コンテキストのプロパティに基づいて、メッセージをオーケストレーションまたは送信ポートのサブスクライバーにメッセージを送信します。  
  
6.  オーケストレーションがサブスクライバーの場合、処理されたメッセージは送信ポートを使用して送信されます。 送信ポートにメッセージが到達した場合、または送信ポートが唯一のサブスクライバーの場合、メッセージは回線で送信される前に送信パイプラインを通じて送信アダプターに渡されます。  
  
 アダプター フレームワーク  
  
 ![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
## <a name="receive-adapters"></a>受信アダプター  
 受信アダプターは、ネットワーク/データ ソース ストリームをメッセージのボディ部に添付して新しい BizTalk Server メッセージを作成します。 また、どのデータを受信しましたが、メッセージング エンジンにそのメッセージを送信するエンドポイントに関連するすべてのメタデータを追加します。  
  
 アダプターは、受信エンドポイントからデータを削除したり、適切な確認メッセージをクライアントに送信して、データが BizTalk Server で受理されたことを示します。  
  
## <a name="send-adapters"></a>送信アダプター  
 アダプターは、特定のトランスポート プロトコルを使用して、指定されたエンドポイントに BizTalk メッセージを送信するために送信します。  
  
 アダプターの詳細については、アダプター、およびカスタム アダプターの作成の構造を参照してください[カスタム アダプターの開発](../core/developing-custom-adapters.md)です。  
  
## <a name="see-also"></a>参照  
 [成果物](../core/artifacts.md)