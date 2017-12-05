---
title: "テスト用ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9b71f02-86df-4b03-bd2c-4d4d2014db02
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88bfee5d45cc1cc7bdc93d8dd50aeb1841e3a28
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="tools-for-testing"></a>テスト用ツール
次の表の運用の準備に関連付けられているテストの実行に使用できるツールが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
|Testing (テスト)|ツール|新しく使用する機能|  
|-------------|----------|---------|  
|**単位と機能テスト**|Microsoft Visual Studio|.NET コードの単体テストに使用されます。 Visual Studio で使用可能であるテスト機能の詳細については、次を参照してください。[アプリケーションのテスト](http://go.microsoft.com/fwlink/?LinkId=159595)(http://go.microsoft.com/fwlink/?LinkId=159595)。|  
||BizUnit|BizTalk ソリューションの自動テスト用に設計されたフレームワークです。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 <br /><br /> BizUnit の詳細については、次を参照してください。 [BizUnit - 自動テスト分散システムのためのフレームワーク](http://go.microsoft.com/fwlink/?LinkID=85168)(http://go.microsoft.com/fwlink/?LinkID=85168)。|  
||NUnit|.NET コードの単体テストに使用されます。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 <br /><br /> NUnit の詳細については、次を参照してください。 [Nunit](http://go.microsoft.com/fwlink/?LinkID=47931) (http://go.microsoft.com/fwlink/?LinkID=47931)。|  
|**コード カバレッジのテスト**|Visual Studio 2010 のコード カバレッジ|アプリケーションを介してすべての実行パスが適切に実行されたことを確認し、配信不能関数またはコード内のクラスを識別するために使用します。 一般に、到達できないか、実行されることはありませんは、コードを削除する必要があります。 Microsoft Visual Studio 2010 のコード カバレッジ機能の詳細については「[を使用してコード カバレッジを判断する方法よりコードがテストされている](http://go.microsoft.com/fwlink/?LinkId=210624)(http://go.microsoft.com/fwlink/?LinkId=210624).|  
|**パフォーマンス テスト**|ログ (PAL) のツールのパフォーマンス分析|パフォーマンス カウンター ログ ファイルを分析するためのツールです。<br /><br /> パフォーマンス分析のログ (PAL) ツールの詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) ツール](https://github.com/clinthuffman/PAL)です。|  
||Microsoft BizTalk LoadGen 2007 ツール|負荷生成ツールのパフォーマンスとストレス テストを実行するために使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。<br /><br /> ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)|  
||Visual Studio 2010 のロード テスト|Visual Studio 2010 Ultimate エディションで使用できるを使用すると、既定では、最大 250 個のユーザーとパックを使用して Visual Studio ロード テスト仮想ユーザー 250 以上のユーザーからの負荷をシミュレートできます。 Visual Studio でのロード テストの実行の詳細については、次を参照してください。[テスト アプリケーションのパフォーマンスとストレス](http://go.microsoft.com/fwlink/?LinkId=203129)(http://go.microsoft.com/fwlink/?LinkId=203129)。|  
||[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]オーケストレーションのプロファイラー|オーケストレーションの時間です。 指定した期間追跡データを表示するために使用オーケストレーションでのパフォーマンスのボトルネックの存在を確認するために便利です。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 <br /><br /> 詳細については、[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]オーケストレーション プロファイラー [BizTalk Server 2006 オーケストレーション プロファイラー](http://go.microsoft.com/fwlink/?LinkId=102209) (http://go.microsoft.com/fwlink/?LinkId=102209)。|  
|**Web サービス テスト**|soapUI|Web サービスをテストするために使用するオープン ソース ユーティリティ。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 <br /><br /> SoapUI の詳細については、次を参照してください。 [soapUI.org](http://go.microsoft.com/fwlink/?LinkId=102196) (http://go.microsoft.com/fwlink/?LinkId=102196)。|  
||Fiddler|""ですネットワーク上の HTTP トラフィックを表示するために役立ちます 詳細については、HTTP をデバッグするため、Fiddler ツールを使用して、次を参照してください。 [Fiddler PowerToy - 第 1 部: HTTP デバッグ](http://go.microsoft.com/fwlink/?LinkID=84796)(http://go.microsoft.com/fwlink/?LinkID=84796)。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 <br /><br /> Fiddler ツールからダウンロードできます。 [Introducing Fiddler](http://go.microsoft.com/fwlink/?LinkID=99357) (http://go.microsoft.com/fwlink/?LinkID=99357)。|  
|**デバッグ**|DebugView|カーネル モードおよび Win32 デバッグ出力用のローカルまたはリモートで監視するためのツールです。<br /><br /> DebugView の詳細については、次を参照してください。 [DebugView for Windows](http://go.microsoft.com/fwlink/?LinkId=102210) (http://go.microsoft.com/fwlink/?LinkId=102210)。|  
||BizTalk MsgBoxViewer|BizTalk メッセージ ボックス データベースとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む HTML レポートを生成します。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 <br /><br /> BizTalk MsgBoxViewer ツールをダウンロードできます。[ここで、ツールの最新バージョンをダウンロード BizTalk MsgBoxViewer -](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930)。|  
||ターミネータ|BizTalk MsgBoxViewer ツールによって、問題を解決します。 ターミネータ ツールが、BizTalk MsgBoxViewer ツールと統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk のターミネータを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 <br /><br /> ターミネータ ツールからダウンロードできます。[ターミネータ](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。|  
||BizTalk Server ベスト プラクティス アナライザー|BizTalk Server のベスト プラクティス アナライザーは、BizTalk Server の展開を調査し、ベスト プラクティスの標準に関連する問題の一覧を生成します。 このツールは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集することによって構成レベルの検証を実行します。 データは展開構成の評価に使用されます。 ツールを読み取りますをレポートのみ、そのシステム設定を変更しませんし、自己調整ツールではありません。<br /><br /> BizTalk Server のベスト プラクティス アナライザー ツールをダウンロードできます。 [BizTalk Server のベスト プラクティス アナライザー](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。|  
  
## <a name="see-also"></a>参照  
 [チェックリスト: 運用準備のテスト](~/technical-guides/checklist-testing-operational-readiness.md)