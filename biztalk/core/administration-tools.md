---
title: 管理およびパフォーマンス ツール |Microsoft Docs
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
ms.openlocfilehash: 7066dd3a0c3ff571bd6cba879f4d7d730f4184ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359453"
---
# <a name="administrative-and-performance-tools"></a>管理およびパフォーマンス ツール 

## <a name="tools-list"></a>ツールの一覧
取引先との対話を BizTalk Server の状態を監視するのに、BizTalk Server アプリケーションを展開するのに、BizTalk Server グループを管理するのに、BizTalk ServerBizTalk サーバーの管理には、次のツールを使用できます。  
  
- **BizTalk Server 管理コンソール**します。 BizTalk Server 管理コンソールは、BizTalk Server の主要な管理ツールです。 この管理コンソールでは、BizTalk アプリケーションのすべての展開操作を実行するためのグラフィカル ユーザー インターフェイスを提供します。 たとえば、アプリケーションのアイテムを追加および削除したり、その他の変更をアプリケーションに加えたりするだけでなく、インポート ウィザード、インストール ウィザード、エクスポート ウィザードなどを起動することもできます。  
  
   BizTalk Server 管理コンソールを使用して、BizTalk Server の実装の正常性の追跡、ボトルネックの特定、および BizTalk Server 環境を監視するライブまたはアーカイブ済みのメッセージ イベントまたはサービス インスタンス データの表示を使用できます。 特定のオーケストレーション、パイプライン、またはメッセージ インスタンスに関する技術的な詳細情報だけでなく、システムで受け取った特定のメッセージのメッセージ フローを表示することもできます。  
  
   BizTalk Server 管理コンソールの使用方法の詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。  
  
- **BTSTask コマンド ライン ツール**します。 BTSTask を使用すると、コマンド ラインから多くの管理タスクを実行できます。 詳細については、BTSTask を使用して、次を参照してください。 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)します。  
  
- **スクリプトとプログラミング Api**します。 Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
   WMI オブジェクト モデルは、管理 API を公開および簡素化します。 すべての管理 API は、管理対象のすべてのオブジェクトに対して、作成、列挙、変更、および削除操作のいくつかを公開します。 WMI は、この機能をすべての WMI オブジェクトに対して一貫した方法で公開します。  
  
- **ビジネス アクティビティを監視 (BAM)。** BAM では、Microsoft Office Excel ブックを使用して、ビジネス ユーザーがビジネス プロセスのリアルタイムの包括的なビューを表示する方法を提供します。 BAM の詳細については、次を参照してください。[ビジネス アクティビティの監視を使用して](../core/using-business-activity-monitoring.md)します。  


- [**BizTalk Health Monitor**](http://blogs.msdn.com/b/biztalkhealthmonitor/ "BizTalk Health Monitor")テーブルの使用法、既知の問題など、BizTalk 環境に関する情報を収集する BizTalk サポート チームによって作成されました。 レポートを強調表示されている潜在的な問題の領域が生成されます。 このツールを実行して、BizTalk 環境を維持するために定期的に出力の確認を検討してください。 これには、BizTalk MsbBox ビューアーが置き換えられます。

- [**BizTalk 終端記号ツール**](https://www.microsoft.com/download/en/details.aspx?id=2846 "BizTalk 終端記号ツール")通常 BizTalk MsgBox ビューアー出力にある、一般的なデータベース整合性の問題を解決するのには、BizTalk のサポート チームによって作成されました。 一般的なタスクには、インスタンスを削除して、大きなテーブルの削除が含まれます。 BizTalk 終端記号のツールの詳細についてを参照してください[この投稿](http://blogs.msdn.com/b/biztalkcpr/archive/2011/02/10/using-biztalk-terminator-to-resolve-issues-identified-by-biztalk-msgboxviewer.aspx)BizTalk エンジニアのブログの 1 つにします。

- [**Microsoft BizTalk LoadGen 2007** ](https://www.microsoft.com/download/details.aspx?id=14925)パフォーマンスと、Microsoft BizTalk Server アプリケーションのストレス テストを実行するメッセージ転送の負荷を生成し、パフォーマンス カウンターのパフォーマンスを監視を提供しますBizTalk Server を実行するインフラストラクチャ。

- [**BizTalk Server のベスト プラクティス アナライザー**](https://www.microsoft.com/downloads/details.aspx?FamilyID=93d432fe-1370-4b6d-aaa8-a0c43c30f5ab "BizTalk Server のベスト プラクティス アナライザー")読み取って報告するだけで構成レベルの検証を実行します。 ベスト プラクティス アナライザーは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集します。 ベスト プラクティス アナライザーでは、データを使用して、展開の構成を評価します。 ベスト プラクティス アナライザーは、任意のシステム設定は変更されませんし、自己調整ツールではありません。

- [**パフォーマンス分析のログ (PAL)** ](https://github.com/clinthuffman/PAL)はパフォーマンス モニター カウンター ログ (任意の既知形式) を読み取り、分析、複雑なが既知のしきい値 (提供) を使用して強力なツールです。 ツールでは、視覚的に重要なパフォーマンス カウンターをグラフし、しきい値を超えた場合にアラートをスローする HTML ベースのレポートを生成します。

- [**Windows の DebugView** ](https://docs.microsoft.com/sysinternals/downloads/debugview)アプリケーション デバッグ出力をローカル システムまたは TCP/IP 経由でアクセスできるネットワーク上のコンピューターを監視することができます。 デバッガーが、アプリケーションやデバイス ドライバーを生成するデバッグ出力をキャッチする必要はありませんので、カーネル モードと Win32 のデバッグ出力の両方を表示することも非標準のデバッグ出力 Api を使用するには、アプリケーションやドライバーを変更する必要があります。

- [**ログイン Parser 2.2** ](https://www.microsoft.com/download/details.aspx?id=24659)イベント ログなど、Windows オペレーティング システムの主要なデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータへの汎用クエリ アクセスを提供する強力な多目的ツールには、レジストリ、ファイル システム、および Active Directory。

- [**プロセス エクスプ ローラー** ](https://docs.microsoft.com/sysinternals/downloads/process-explorer)は DLL バージョンの問題またはハンドルのリークを追跡するために役立ちますし、Windows の方法とアプリケーションのしくみを把握します。

- [**TCP トレース**](http://www.pocketsoap.com/tcptrace/ "TCP トレース")クライアントとサーバー間のテキスト ベースのネットワーク トラフィックを監視するために使用します。 旅行、ネットワーク経由でメッセージを表示する SOAP、HTTP、POP3 などのようなアダプターの使用時に便利です。

- [**DTCPing** ](https://www.microsoft.com/download/details.aspx?id=2868)は BizTalk のマルチ サーバー展開でわかります多くの場合、Microsoft DTC ファイアウォール問題のトラブルシューティングを支援するために設計されています。

  
## <a name="see-also"></a>参照  
 [アプリケーションの展開および管理のツール](../core/application-deployment-and-management-tools.md)