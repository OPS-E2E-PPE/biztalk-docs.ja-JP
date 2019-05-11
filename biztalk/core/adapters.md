---
title: アダプター |Microsoft Docs
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
ms.openlocfilehash: 5d3e669f31f1050a0e2c37388cd8106a2386da45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361079"
---
# <a name="adapters"></a>アダプター
外部システム、アプリケーション、およびエンティティとメッセージを交換するのには、Microsoft BizTalk Server は、アダプターの概念を使用します。 *アダプター* com またはします。NET ベースのコンポーネントとビジネス エンドポイント (ファイル システム、データベース、カスタム ビジネス アプリケーションなど) のメッセージを転送するさまざまな通信プロトコルを使用します。  
  
 アダプターは送信で外部のエンティティとメッセージを交換し、操作を受信する BizTalk Server で使用します。  
  
-   送信 (または送信側) 操作は、情報が BizTalk Server によってアダプターによってサポートされるプロトコルを使用して外部エンティティに送信されるときに発生します。  
  
-   受信 (または受信側) 操作とは、アダプターは、外部エンティティから情報を受信し、BizTalk Server メッセージング エンジンに渡します。  
  
## <a name="the-adapter-framework"></a>アダプター フレームワーク  
 次の図は、アダプターとアダプター フレームワークが連携して、アプリケーションを BizTalk Server に接続する方法を示します。  
  
1. データは、指定されたアドレスで特定のプロトコルのメッセージをリッスンする受信場所を介して受信されます。 受信場所は、アダプターと受信パイプラインに関連付けられます。 アダプターとパイプライン コンポーネントがあらかじめ決められたプロトコルのメッセージで特定のロジックを実行するを構成することができます。  
  
2. 受信場所でメッセージを受信すると、メッセージは、アダプターは、新しい BizTalk Server メッセージを作成、データ ストリームをアタッチします (通常のメッセージのボディ部) のメッセージに、エンドポイント経由でに関するメタデータを追加する送信されデータが受信したが、メッセージング エンジンにそのメッセージを送信します。  
  
3. メッセージング エンジンは、場所データが XML に変換、メッセージの送信者の認証、メッセージを復号化、および XML の検証、受信パイプラインにメッセージを送信します。  
  
4. メッセージング エンジンは、メッセージ ボックスに、メッセージを発行します。 メッセージ ボックスは、処理するメッセージを格納している Microsoft SQL Server テーブルです。 両方のオーケストレーションおよび送信ポートは、メッセージ ボックス データベースにサブスクライブできます。  
  
5. メッセージング エンジンは、オーケストレーションまたは送信ポートのサブスクライバー、サブスクライバーのフィルターで一連の仕様に一致するメッセージ コンテキスト プロパティに基づいて、メッセージを送信します。  
  
6. オーケストレーションがサブスクライバーの場合は、メッセージを処理して、送信ポートを使用して送信されます。 送信ポートが、または唯一のサブスクライバーと、メッセージが、送信アダプターの送信パイプラインを通じて、ネットワーク経由で送信される前に渡します。  
  
   アダプター フレームワーク  
  
   ![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
## <a name="receive-adapters"></a>受信アダプター  
 受信アダプターはメッセージの本文に、ネットワーク/データ ソースのストリームを添付して新しい BizTalk Server メッセージを作成します。 また、どのデータを受信しましたが、そのメッセージをメッセージング エンジンに送信エンドポイントに関連するメタデータも追加します。  
  
 アダプターは、受信エンドポイントからデータを削除または BizTalk Server にデータが受け入れられたことを示すクライアントに適切な受信確認メッセージを送信します。  
  
## <a name="send-adapters"></a>送信アダプター  
 送信アダプターは BizTalk メッセージをその特定のトランスポート プロトコルを使用して、指定されたエンドポイントに送信します。  
  
 アダプターの詳細については、アダプター、およびカスタム アダプターの作成の構造を参照してください[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。  
  
## <a name="see-also"></a>参照  
 [アイテム](../core/artifacts.md)