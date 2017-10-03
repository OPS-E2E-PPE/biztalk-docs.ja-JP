---
title: "JD Edwards OneWorld のアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1daee7d44152817da1ac536dd98cbaf898e2ac7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-jd-edwards-oneworld"></a>JD Edwards OneWorld のアーキテクチャ
Microsoft BizTalk Adapter for JD Edwards OneWorld を使用すると、JD Edwards OneWorld のビジネス関数にアクセスできます。 JD Edwards OneWorld は、JDENet と呼ばれる独自のメッセージング アーキテクチャを使用して、クライアント コンピューターとサーバー コンピューター間の通信を処理します。 JDENet は、JAR ファイルは、Connector.jar および Kernel.jar で JD Edwards OneWorld コネクタ クラスによって実装されます。 通信は、TCP/IP をトランスポート プロトコルとして使用して実装されており、既定のポートは 6009 または 6010 です。 この値を設定する場所の詳細についてを参照してください[JD Edwards OneWorld トランスポートのプロパティを設定する方法](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)です。  
  
 **BizTalk Adapter for JD Edwards OneWorld のアーキテクチャ**  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 JD Edwards OneWorld のビジネス関数を呼び出すには、2 つのメッセージが必要です。  
  
-   最初のメッセージは、ビジネス関数を処理するサーバーの場所を返します。 これを行うと呼ばれるテーブルのセットの検索を実行して*オブジェクト構成マッピング (OCM)*です。  
  
-   2 番目のメッセージでは、JD Edwards OneWorld から渡す引数または JD Edwards OneWorld に渡す引数が入ったフォーマット済みメッセージ バッファーを適切なサーバーに送信し、応答を待ちます。 バッファーは基になる C++ 構造体の Typedef に従ってフォーマットされます。  
  
## <a name="inbound-services-at-design-time"></a>デザイン時の受信サービス  
  
-   デザイン時に、ターゲットの JD Edwards OneWorld サーバーに接続するためのポートを作成し、アダプターを選択して、資格情報を指定します。 Visual Studio 開発環境は、アダプター フレームワークを呼び出して、このポートのデザイン時情報を要求します。 BizTalk Adapter for JD Edwards OneWorld ではこのポートに Browsingagent を使用します。  
  
-   BizTalk Server は、デザイン時にアダプターを呼び出して情報を要求します。  
  
-   Browsingagent は、要求を JD Edwards OneWorld のネイティブ コードに変換し、ThinNet API 接続 (Connector.jar および Kernel.jar で確立される) を経由して、変換した要求を JD Edwards OneWorld に送信します。  
  
-   カスタム ビジネス関数は BTSREL インストールによりインストール: マスター ビジネス関数を公開します。  
  
-   JD Edwards OneWorld のモジュールの一覧が最初に返され、Visual Studio に転送され、アダプター ウィザードに設定されます。  
  
-   階層を展開してライブラリ名とモジュール名を表示できます。  
  
-   特定のモジュールを選択すると、モジュール内のすべての関数のスキーマが表示されます。 アダプターは必要な情報を JD Edwards OneWorld から取得し、browsingagent がスキーマを作成します。  
  
-   スキーマは BizTalk Server プロジェクトのオーケストレーションに追加されます。  
  
## <a name="inbound-services-at-run-time"></a>実行時の受信サービス  
  
-   BizTalk Server は BizTalk Adapter for JD Edwards OneWorld を呼び出し、特定のポートでメッセージを送信します。  
  
-   ランタイム エージェントは XML を JD Edwards のネイティブ コードに変換します。  
  
-   ランタイム エージェントは、ThinNet を経由して、送信ポートのトランスポート プロパティで指定された JD Edwards エンタープライズ システムに要求を送信します。  
  
-   JD Edwards システムでマスター ビジネス関数が実行され、ビジネス関数が返すデータ パラメーターと成功または失敗を示す応答ドキュメントが生成されます。  
  
-   JD Edwards OneWorld に送信されるメッセージは、単一メッセージ、単一応答のアーキテクチャです。 複数のメッセージを同時に処理することはできません。  
  
-   応答ドキュメントが ThinNet を通じて返され、XML に変換されて、BizTalk Server に送られます。  
  
## <a name="outbound-events-at-design-time"></a>デザイン時の送信イベント  
  
-   イベント メタデータのシステム的な作成は利用できません。  
  
-   イベント ドキュメントの FAX を Visual Studio に提供し、スキーマを生成して、ターゲットの名前空間と共にプロジェクトに組み込めるようにする必要があります。  
  
## <a name="outbound-events-at-run-time"></a>実行時の送信イベント  
  
-   JD Edwards エンタープライズ サーバーにファイル転送機構が設定されます。イベントの完了により、生成された XML ドキュメントがそのサーバーのターゲット ディレクトリに転送されます。  
  
-   BizTalk Server コンピューターには、エンタープライズ サーバーのディレクトリに対して割り当てられたドライブがあります。  
  
-   受信ポートのトランスポート プロパティは、マップされたドライブに対して構成されます。 受信ポートではエンタープライズ サーバーによりディレクトリに送信されたメッセージを受信します。  
  
-   ターゲットの名前空間を識別することによって、構成されている受信ポートに正しいメッセージが確実にルーティングされます。  
  
-   受信ポートは、BizTalk Server の XML ドキュメントを送信します。  
  
## <a name="see-also"></a>参照  
 [JD Edwards OneWorld トランスポートのプロパティを設定する方法](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)   
 [計画とアーキテクチャ](../core/planning-and-architecture17.md)