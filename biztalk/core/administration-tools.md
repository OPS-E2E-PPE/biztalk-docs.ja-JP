---
title: 管理およびパフォーマンス ツール |Microsoft ドキュメント
description: タスク、パフォーマンス、および BizTalk Server でのトレースを管理する一般的なツール
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 932814f7-2ab3-45cb-8bbc-eaf00fcb24a0
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 100b72949cd5fc6ab4da2dd90469f924db27963d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006579"
---
# <a name="administrative-and-performance-tools"></a>管理およびパフォーマンス ツール 

## <a name="tools-list"></a>ツールの一覧
次のツールを使用して、取引先との対話を BizTalk Server のステータスを監視する、BizTalk Server アプリケーションを展開する、BizTalk Server グループを管理する、BizTalk ServerBizTalk サーバーを管理することができます。  
  
-   **BizTalk Server 管理コンソール**です。 BizTalk Server 管理コンソールは、BizTalk Server の主要な管理ツールです。 この管理コンソールでは、BizTalk アプリケーションのすべての展開操作を実行するためのグラフィカル ユーザー インターフェイスを提供します。 たとえば、アプリケーションのアイテムを追加および削除したり、その他の変更をアプリケーションに加えたりするだけでなく、インポート ウィザード、インストール ウィザード、エクスポート ウィザードなどを起動することもできます。  
  
     BizTalk Server 管理コンソールを使用して、ライブまたはアーカイブ済みのメッセージ イベントまたはサービス インスタンス データの表示を使用して、BizTalk Server の実装の状態を追跡、ボトルネックを特定および BizTalk Server 環境を監視します。 特定のオーケストレーション、パイプライン、またはメッセージ インスタンスに関する技術的な詳細情報だけでなく、システムで受け取った特定のメッセージのメッセージ フローを表示することもできます。  
  
     BizTalk Server 管理コンソールを使用する方法の詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。  
  
-   **BTSTask コマンド ライン ツール**です。 BTSTask を使用すると、コマンド ラインから多くの管理タスクを実行できます。 詳細については、BTSTask を使用して、次を参照してください。 [BTSTask コマンドライン リファレンス](../core/btstask-command-line-reference.md)です。  
  
-   **スクリプトとプログラミング Api**です。 Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
     WMI オブジェクト モデルは、管理 API を公開および簡素化します。 すべての管理 API は、管理対象のすべてのオブジェクトに対して、作成、列挙、変更、および削除操作のいくつかを公開します。 WMI は、この機能をすべての WMI オブジェクトに対して一貫した方法で公開します。  
  
-   **ビジネス アクティビティの監視 (BAM)。** BAM では、Microsoft Office Excel ブックを使用して、ビジネス ユーザーがビジネス プロセスのリアルタイムの包括的なビューを表示する方法を提供します。 BAM の詳細については、次を参照してください。[を使用したビジネス アクティビティ監視](../core/using-business-activity-monitoring.md)です。  


-   [**BizTalk Health Monitor**](http://blogs.msdn.com/b/biztalkhealthmonitor/ "BizTalk Health Monitor")テーブルの使用法、既知の問題など、BizTalk 環境に関する情報を収集する BizTalk サポート チームが作成されました。 潜在的な問題領域が強調表示されている、レポートが生成されます。 このツールを実行して、BizTalk 環境を維持するために定期的に出力を確認することを検討してください。 これには、BizTalk MsbBox ビューアーが置き換えられます。

-   [**BizTalk 終端記号ツール**](https://www.microsoft.com/download/en/details.aspx?id=2846 "BizTalk 終端記号ツール")通常 BizTalk MsgBox ビューアーの出力にある、一般的なデータベース整合性の問題を解決するのには、BizTalk サポート チームによって作成されました。 一般的なタスクには、インスタンスを削除して、大きなテーブルの削除が含まれます。 BizTalk 終端記号ツールの詳細についてを参照してください[この投稿](http://blogs.msdn.com/b/biztalkcpr/archive/2011/02/10/using-biztalk-terminator-to-resolve-issues-identified-by-biztalk-msgboxviewer.aspx)BizTalk エンジニアのブログを 1 つにします。

-   [**Microsoft BizTalk LoadGen 2007** ](https://www.microsoft.com/download/details.aspx?id=14925)パフォーマンスと、Microsoft BizTalk Server アプリケーションのストレス テストを実行するメッセージ転送の負荷を生成し、パフォーマンス カウンターのパフォーマンスの監視を提供しますBizTalk Server を実行するインフラストラクチャ。

-   [**BizTalk Server のベスト プラクティス アナライザー**](https://www.microsoft.com/downloads/details.aspx?FamilyID=93d432fe-1370-4b6d-aaa8-a0c43c30f5ab "BizTalk Server のベスト プラクティス アナライザー")読み取りのみレポートを作成して構成レベルの検証を実行します。 ベスト プラクティス アナライザーは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集します。 ベスト プラクティス アナライザーでは、データを使用して、展開の構成を評価します。 ベスト プラクティス アナライザーは、任意のシステム設定は変更されず、自己調整ツールではありません。

-   [**パフォーマンス分析のログ (PAL)** ](https://github.com/clinthuffman/PAL)強力なツールのパフォーマンス モニター カウンター ログ (任意の既知形式) を読み取り、(提供) が、複雑で、既知のしきい値を使用して分析します。 このツールでは、視覚的に重要なパフォーマンス カウンターをグラフ化し、しきい値を超えたときにアラートをスローする HTML ベース レポートを生成します。

-   [**DebugView for Windows** ](https://docs.microsoft.com/sysinternals/downloads/debugview)は、アプリケーションをデバッグ出力をローカル システムまたは TCP/IP 経由でアクセスできるネットワーク上のコンピューターを監視することができます。 デバッガーのアプリケーションまたはデバイス ドライバーを生成するデバッグ出力をキャッチする必要はありません、カーネル モードと Win32 デバッグ出力の両方を表示できます。 また非標準のデバッグ出力の Api を使用するには、アプリケーションまたはドライバーを変更する必要があります。

-   [**ログ パーサー 2.2** ](https://www.microsoft.com/download/details.aspx?id=24659) 、強力な多様なツール、イベント ログなどの Windows オペレーティング システムでキーのデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータにユニバーサル クエリ アクセスを提供するは、レジストリ、ファイル システム、および Active Directory です。

-   [**エクスプ ローラーの処理**](https://docs.microsoft.com/sysinternals/downloads/process-explorer)は DLL バージョンの問題、またはハンドルのリークを追跡するために役立ちますし、Windows の方法とアプリケーションの作業を理解できるようにします。

-   [**TCP トレース**](http://www.pocketsoap.com/tcptrace/ "TCP トレース")クライアントとサーバー間でテキスト ベースのネットワーク トラフィックを監視するために使用します。 トラベル ネットワーク経由でメッセージを表示する SOAP、HTTP、POP3 などのようにアダプターを使用しているときに便利です。

-   [**DTCPing** ](https://www.microsoft.com/download/details.aspx?id=2868) BizTalk のマルチ サーバー展開でわかります多くの場合、Microsoft DTC ファイアウォール問題のトラブルシューティングに役立つよう設計されています。

  
## <a name="see-also"></a>参照  
 [アプリケーションの展開および管理のツール](../core/application-deployment-and-management-tools.md)