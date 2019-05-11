---
title: JD Edwards OneWorld のアーキテクチャ |Microsoft Docs
description: デザイン時および実行時に BizTalk の JD Edwards OneWorld アダプター デザイン時および実行時、および送信イベント受信サービスを説明します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e98b7196077d0754ef067d01a51b49b96dc8f9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358987"
---
# <a name="architecture-of-jd-edwards-oneworld"></a>JD Edwards OneWorld のアーキテクチャ
Microsoft の BizTalk Adapter for JD Edwards OneWorld では、JD Edwards OneWorld ビジネス関数へのアクセスを提供します。 JD Edwards OneWorld は、独自のメッセージング JDENet と呼ばれるアーキテクチャを使用してクライアントとサーバーのマシン間で通信します。 JDENet は、Connector.jar および Kernel.jar という JAR ファイルを JD Edwards OneWorld コネクタ クラスによって実装されます。 通信は、既定のポートは 6009 または 6010 トランスポート プロトコルとして TCP/IP を使用して実装されます。 この値を設定する場所の説明についてを参照してください[アーティファクトを BizTalk 管理コンソールに追加](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)します。  
  
 **BizTalk Adapter for JD Edwards OneWorld のアーキテクチャ**  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 JD Edwards OneWorld ビジネス関数の呼び出しでは、2 つのメッセージが必要です。  
  
-   最初のメッセージは、ビジネス関数を処理するサーバーの場所で応答します。 これと呼ばれるテーブルのセットでルックアップを実行することによって実現*オブジェクト構成マッピング (OCM)* します。  
  
-   2 番目のメッセージは、JD Edwards OneWorld との間を適切なサーバーに渡す引数を含む書式設定されたメッセージ バッファーを送信し、応答を待機します。 バッファーは、基になるの typedef に従って書式設定C++構造体。  
  
## <a name="inbound-services-at-design-time"></a>デザイン時に受信サービス  
  
-   デザイン時にには、アダプターを選択、および、ターゲットの JD Edwards OneWorld サーバーへの接続に資格情報を指定のポートを作成します。 Visual Studio 開発環境では、このポートのデザイン時の情報を要求するためにアダプター フレームワークを呼び出します。 BizTalk Adapter for JD Edwards OneWorld では、このポートに対して Browsingagent を使用します。  
  
-   デザイン時に、BizTalk Server は、アダプターを呼び出すことで情報を要求します。  
  
-   Browsingagent は、要求を JD Edwards OneWorld のネイティブ コードに変換し、(コネクタと Kernel.jar で確立された)、ThinNet API 接続を JD Edwards OneWorld に要求を送信します。  
  
-   カスタム ビジネス関数は BTSREL インストールを通じてインストールされます。 マスター ビジネス関数を公開します。  
  
-   JD Edwards OneWorld のモジュールの一覧が最初に返され、転送先に Visual Studio で、アダプター ウィザードに設定されます。  
  
-   ライブラリ名とモジュール名を表示する階層を展開することができます。  
  
-   特定のモジュールを選択すると、モジュール内のすべての関数のスキーマを参照してください。 アダプターは、JD Edwards OneWorld から、必要な情報を取得し、browsingagent がスキーマを作成します。  
  
-   スキーマは、BizTalk Server プロジェクトのオーケストレーションに追加されます。  
  
## <a name="inbound-services-at-run-time"></a>実行時に受信サービス  
  
-   BizTalk Server は、BizTalk Adapter for JD Edwards OneWorld の特定のポートでメッセージの送信を呼び出します。  
  
-   ランタイム エージェントは、XML を JD Edwards のネイティブ コードに変換します。  
  
-   ランタイム エージェントは、送信ポートのトランスポートのプロパティで指定された JD Edwards エンタープライズ システムに ThinNet を通じて要求を送信します。  
  
-   データだけでなく、成功または失敗を示す応答ドキュメントを生成し、JD Edwards システムでマスター ビジネス関数が実行されるビジネス関数によって返されるパラメーター。  
  
-   JD Edwards OneWorld に送信されるメッセージは 1 つのメッセージ、単一応答のアーキテクチャです。 同時に複数のメッセージを処理できません。  
  
-   応答ドキュメントが ThinNet を経由で送信される、XML に変換され、BizTalk Server に送信します。  
  
## <a name="outbound-events-at-design-time"></a>デザイン時にイベントを送信  
  
-   イベント メタデータの体系的な作成はありません。  
  
-   イベント ドキュメントの複製は、スキーマを生成し、ターゲットの名前空間と共にプロジェクトに組み込むように Visual Studio を指定する必要があります。  
  
## <a name="outbound-events-at-run-time"></a>実行時にイベントを送信  
  
-   ファイル転送機構は、そのサーバー上のターゲット ディレクトリに、イベントの完了によってトリガーされる結果の XML ドキュメントのトランスポートを JD Edwards エンタープライズ サーバーで確立されます。  
  
-   BizTalk Server コンピューターには、エンタープライズ サーバー上のディレクトリにマップされたドライブがあります。  
  
-   受信ポートのトランスポートのプロパティは、マップされたドライブに対して構成されます。 受信ポートは、エンタープライズ サーバーによりディレクトリに送信されたメッセージを受信します。  
  
-   ターゲット名前空間 id によりに正しいメッセージがルーティングされる受信ポートが構成されています。  
  
-   受信ポートは、BizTalk Server に XML ドキュメントを送信します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [計画および設計](../core/planning-and-architecture17.md)