---
title: BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ |Microsoft Docs
description: デザイン時および実行時に BizTalk の JD Edwards EnterpriseOne アダプター デザイン時および実行時、および送信イベント受信サービスを説明します。
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
ms.openlocfilehash: 9dc7992262731532f2c9df6b29896f48f5f74e5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359362"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a>BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ
Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne のビジネス関数へのアクセスを提供します。 JD Edwards EnterpriseOne は、独自のメッセージング JDENet と呼ばれるアーキテクチャを使用してクライアントとサーバーのマシン間で通信します。 JDENet は、Connector.jar および Kernel.jar という JAR ファイルを JD Edwards EnterpriseOne コネクタ クラスによって実装されます。 通信は、既定のポートは 6009 または 6010 トランスポート プロトコルとして TCP/IP を使用して実装されます。 この値を設定する場所の説明についてを参照してください[アーティファクトを BizTalk 管理コンソールに追加](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)します。  
  
 次の図は、BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャを示します。  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a>デザイン時に受信サービス  
  
-   、デザイン時にアダプターを選択して、および、ターゲットの JD Edwards EnterpriseOne サーバーへの接続に資格情報を指定するポートを作成します。 Visual Studio 開発環境では、このポートのデザイン時の情報を要求するためにアダプター フレームワークを呼び出します。 アダプターは、このポートに Browsingagent を使用します。  
  
-   デザイン時に、BizTalk Server は、アダプターを呼び出すことで情報を要求します。  
  
-   Browsingagent は、要求を JD Edwards EnterpriseOne のネイティブ コードに変換し、JD Edwards EnterpriseOne ThinNet API 接続 (Connector.jar および Kernel.jar で確立された) を介して要求を送信します。  
  
-   JD Edwards EnterpriseOne のモジュールの一覧が最初に返され、転送先に Visual Studio 開発環境、アダプター ウィザードに設定されます。  
  
-   ライブラリ名とモジュール名を表示することによって階層を展開できます。  
  
-   特定のモジュールを選択すると、モジュール内のすべての関数のスキーマを参照してください。 アダプターから JD Edwards EnterpriseOne では、必要な情報を取得し、browsingagent がスキーマを作成します。  
  
-   スキーマは、BizTalk Server プロジェクトのオーケストレーションに追加されます。  
  
## <a name="inbound-services-at-run-time"></a>実行時に受信サービス  
  
-   BizTalk Server では、特定のポートでメッセージを送信するアダプターを呼び出します。  
  
-   ランタイム エージェントは、XML を JDE のネイティブ コードに変換します。  
  
-   実行時のエージェントでは、送信ポートのトランスポートのプロパティで指定された JD Edwards EnterpriseOne システムを ThinNet を通じて要求を送信します。  
  
-   データだけでなく、成功または失敗を示す応答ドキュメントを生成し、JD Edwards EnterpriseOne システムでマスター ビジネス関数が実行されるビジネス関数によって返されるパラメーター。  
  
-   JD Edwards EnterpriseOne に送信されるメッセージは 1 つのメッセージ、単一応答のアーキテクチャです。 同時に複数のメッセージを処理できません。  
  
-   応答ドキュメントが ThinNet を経由で送信される、XML に変換され、BizTalk Server に送信します。  
  
## <a name="outbound-events-at-design-time"></a>デザイン時にイベントを送信  
  
-   イベント メタデータの体系的な作成はありません。  
  
-   イベント ドキュメントの複製は、スキーマを生成し、ターゲットの名前空間と共にプロジェクトに組み込むように Visual Studio を指定する必要があります。  
  
## <a name="outbound-events-at-run-time"></a>実行時にイベントを送信  
  
-   ファイル転送機構は、そのコンピューター上のターゲット ディレクトリに、イベントの完了によってトリガーされる結果の XML ドキュメントのトランスポートを JD Edwards EnterpriseOne サーバーで確立されます。  
  
-   BizTalk Server コンピューターには、EnterpriseOne サーバー上のディレクトリにマップされたドライブがあります。  
  
-   受信ポートのトランスポートのプロパティは、マップされたドライブに対して構成されます。 受信ポートは、EnterpriseOne サーバーによりディレクトリに送信されたが、メッセージを受信します。  
  
-   ターゲット名前空間の id によりに正しいメッセージがルーティングされるようになります、構成された受信ポート  
  
-   受信ポートは、BizTalk Server で XML ドキュメントを送信します。  
  
## <a name="more-good-stuff"></a>便利な機能
[BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[アプリケーション アイテムの作成](../core/developing-applications2.md)  
[インポート、JD Edwards EnterpriseOne のアプリ](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)  
[[トラブルシューティング]](../core/troubleshooting-jd-edwards-enterpriseone.md)  
