---
title: BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ |Microsoft ドキュメント
description: デザイン時および実行時に BizTalk の JD Edwards EnterpriseOne アダプター デザイン時および実行時に、および送信イベント受信サービスを説明します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b495ee9a34cf464bd5cc11caed53c5df54948a49
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013761"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a>BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ
Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を使用すると、JD Edwards EnterpriseOne のビジネス関数にアクセスできます。 JD Edwards EnterpriseOne は、JDENet と呼ばれる独自のメッセージング アーキテクチャを使用して、クライアント コンピューターとサーバー コンピューター間の通信を処理します。 JDENet は、Connector.jar および Kernel.jar という JAR ファイルにある JD Edwards EnterpriseOne コネクタ クラスによって実装されています。 通信は、TCP/IP をトランスポート プロトコルとして使用して実装されており、既定のポートは 6009 または 6010 です。 この値を設定する場所の詳細についてを参照してください[アイテムを BizTalk 管理コンソールに追加](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)です。  
  
 次の図は、BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャを示しています。  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a>デザイン時の受信サービス  
  
-   デザイン時に、ターゲットの JD Edwards EnterpriseOne サーバーに接続するためのポートを作成し、アダプターを選択して、資格情報を指定します。 Visual Studio 開発環境は、アダプター フレームワークを呼び出して、このポートのデザイン時情報を要求します。 アダプターはこのポートに対して Browsingagent を使用します。  
  
-   BizTalk Server は、デザイン時にアダプターを呼び出して情報を要求します。  
  
-   Browsingagent は、要求を JD Edwards EnterpriseOne のネイティブ コードに変換し、ThinNet API 接続 (Connector.jar および Kernel.jar で確立される) を経由して、変換した要求を JD Edwards EnterpriseOne に送信します。  
  
-   JD Edwards EnterpriseOne のモジュールの一覧が最初に取得され、Visual Studio 開発環境に送信されて、アダプター ウィザードに設定されます。  
  
-   ライブラリ名を表示し、次にモジュール名を表示して階層を展開できます。  
  
-   特定のモジュールを選択すると、モジュール内のすべての関数のスキーマが表示されます。 アダプターは必要な情報を JD Edwards EnterpriseOne から取得し、browsingagent がスキーマを作成します。  
  
-   スキーマは BizTalk Server プロジェクトのオーケストレーションに追加されます。  
  
## <a name="inbound-services-at-run-time"></a>実行時の受信サービス  
  
-   BizTalk Server は特定のポートでアダプターを呼び出してメッセージを送信します。  
  
-   ランタイム エージェントは XML を JDE のネイティブ コードに変換します。  
  
-   ランタイム エージェントは ThinNet を経由して、送信ポートのトランスポート プロパティで指定された JD Edwards EnterpriseOne システムに要求を送信します。  
  
-   データだけでなく、成功または失敗を示す応答ドキュメントを生成する、JD Edwards EnterpriseOne システムでマスター ビジネス関数が実行されるビジネス関数によって返されるパラメーター。  
  
-   JD Edwards EnterpriseOne に送信されるメッセージは、単一メッセージ、単一応答のアーキテクチャです。 複数のメッセージを同時に処理することはできません。  
  
-   応答ドキュメントが ThinNet を通じて返され、XML に変換されて、BizTalk Server に送られます。  
  
## <a name="outbound-events-at-design-time"></a>デザイン時の送信イベント  
  
-   イベント メタデータのシステム的な作成は利用できません。  
  
-   イベント ドキュメントの FAX を Visual Studio に提供し、スキーマを生成して、ターゲットの名前空間と共にプロジェクトに組み込めるようにする必要があります。  
  
## <a name="outbound-events-at-run-time"></a>実行時の送信イベント  
  
-   ファイル トランスポート機構がそのコンピューター上のターゲット ディレクトリに、イベントの完了によってトリガーされる結果の XML ドキュメントのトランスポートを JD Edwards EnterpriseOne サーバーで確立されます。  
  
-   BizTalk Server コンピューターには、EnterpriseOne サーバー上のディレクトリに対して割り当てられたドライブがあります。  
  
-   受信ポートのトランスポート プロパティは、マップされたドライブに対して構成されます。 受信ポートでは EnterpriseOne サーバーによりディレクトリに送信されたメッセージを受信します。  
  
-   ターゲット名前空間の識別に正しいメッセージがルーティングされることを確認、構成された受信ポート  
  
-   受信ポートは BizTalk Server に XML ドキュメントを送信します。  
  
## <a name="more-good-stuff"></a>便利な機能
[BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[アプリケーションのアイテムを作成します。](../core/developing-applications2.md)  
[インポート、JD Edwards EnterpriseOne アプリケーション](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)  
[[トラブルシューティング]](../core/troubleshooting-jd-edwards-enterpriseone.md)  
