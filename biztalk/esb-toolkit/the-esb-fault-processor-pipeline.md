---
title: "ESB フォールト Processor パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a57752b1-8bca-4534-9e5b-7ce721a9490a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd9a6cecf5353ab72cea0d67b06f3402fc1716a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-fault-processor-pipeline"></a>ESB フォールト Processor パイプライン
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ALL という名前の送信ポートをインストールします。例外、ESBFaultProcessor を使用する送信パイプラインです。 図 1 は、すべてのプロパティを示します。例外は、ポートを送信します。  
  
 ![すべての例外の送信ポート](../esb-toolkit/media/ch4-allexceptionssendport.gif "Ch4 AllExceptionsSendPort")  
  
 **図 1**  
  
 **すべての構成。例外の送信ポート、ESBFaultProcessor パイプラインの使用を含む**  
  
 ESBFaultProcessor パイプラインには、次のパイプライン コンポーネントが含まれています: ESB 例外エンコーダー、ESB ビジネス アクティビティ監視 (BAM) 追跡ツールおよび ESB を変換します。  
  
 ALL です。例外の送信ポートは、ESB のすべてのエラー メッセージを BizTalk 失敗のメッセージのルーティング メカニズムによって生成されるすべてのメッセージをサブスクライブしています。 図 2 は、すべてのプロパティの設定、フィルターを示します。例外は、ポートを送信します。  
  
 ![送信ポートのフィルター処理](../esb-toolkit/media/ch4-filtersendport.gif "Ch4 FilterSendPort")  
  
 **図 2**  
  
 **すべてのフィルター プロパティ。例外の送信ポートをポートのサブスクリプションを定義します**  
  
## <a name="the-fault-processor-pipeline-exception-encoder-component"></a>フォールト プロセッサ パイプライン例外エンコーダー コンポーネント  
 ESB 例外エンコーダー パイプライン コンポーネントは、ESB 失敗オーケストレーション例外ルーティング機構と ESB 例外の報告に準拠する正規のメッセージに BizTalk 失敗のメッセージのルーティング メカニズムで生成されるエラー メッセージを正規化しますスキーマです。  
  
 オーケストレーションの例外のルーティングの失敗の例外のコンポーネントが拡充され、すべてのエラー メッセージのプロパティ、XLANG メッセージ、コンテキスト プロパティをシリアル化および**System.Exception**については、XML メッセージにします。  
  
 メッセージのルーティングの失敗の例外のコンポーネントは、アプリケーションの名前とその他のアンビエント プロパティを追加することで、データを拡充し、スキーマの名前空間、送信 XML メッセージの内容に適用されます。  
  
 必要に応じて、ESB 例外エンコーダー パイプライン コンポーネントは、Microsoft InfoPath 処理命令、送信メッセージにも適用できます。 InfoPath 命令を変更するには、デザイン ビューで、パイプライン コンポーネントのプロパティを設定します。 次の 3 つの設計時のプロパティでは、ESB 例外エンコーダー パイプライン コンポーネントの実行時の動作に影響します。  
  
-   **EscapeCDATA です。** このプロパティは、コンポーネントがいずれかがエスケープされるかどうかを決定**CDATA**のセクションにはメッセージが永続化 InfoPath が正しく表示できるようにします。  
  
-   **FaultDocumentNamespace です。** このプロパティは、既定値は**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**です。 永続化されたメッセージのカスタムの送信名前空間を使用するように変更できます。  
  
-   **ProcessingInstruction です。** このプロパティは、フォールトの ESB 例外レポート スキーマに準拠している任意の InfoPath 処理命令を含めることができます。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の処理命令に準拠している InfoPath テンプレートが含まれています。  
  
    ```  
    <?mso-infoPathSolution solutionVersion="1.0.0.346" productVersion="11.0.6565"  
    PIVersion="1.0.0.0"   
    href=file:///\\localhost\publish\Microsoft.Practices.ESB.ExceptionHandling.InfoPath.Reporting.xsn  
    name="urn:schemas-microsoft-com:office:infopath:  
    Microsoft-Practices-ESB-ExceptionHandling-InfoPath-Reporting:  
    http---schemas-microsoft-biztalk-practices-esb-com-exceptionhandling"  
    language="en-us" ?><?mso-application progid="InfoPath.Document"?>  
    ```  
  
## <a name="the-fault-processor-pipeline-bam-tracker-component"></a>フォールト プロセッサ パイプライン BAM の追跡ツール コンポーネント  
 ESB BAM の追跡ツールのパイプライン コンポーネントは、ESB 例外エンコーダー コンポーネントからメッセージを受信し、ESB 例外管理フレームワークのインストール中に作成された BAM プライマリ インポート テーブルを選択したエラーのデータを書き込みます。  
  
 ESB BAM の追跡ツール コンポーネントを使用して、 **GetEventStream** BAM プライマリ インポート データベースにアクティビティのレコードと、次のフィールドを追加するパイプラインのコンテキストのメソッド。  
  
-   **アプリケーション**  
  
-   **Description**  
  
-   **FaultSeverity**  
  
-   **サービス名**  
  
-   **ErrorType**  
  
-   **FaultCode**  
  
-   **MachineName**  
  
-   **メッセージ Id**  
  
-   **DateTime**  
  
-   **FaultDescription**  
  
-   **スコープ**  
  
-   **FailureCategory**  
  
-   **FaultGenerator**  
  
-   **ServiceInstanceID**  
  
 ESB BAM の追跡ツール コンポーネントが、メッセージ識別子を使用して (、 **MessageID**プロパティ)、ESB エラー メッセージの BAM アクティビティの ID として値 ESB BAM の追跡ツールのコンポーネントは、設定、実行時動作を変更できる 2 つのデザイン時プロパティを公開します。  
  
-   **有効になります。** このプロパティは、コンポーネントはメッセージを処理し、BAM データベースに書き込むかどうかを判断します。 設定すると**False**コンポーネントは、パイプラインの次のコンポーネントにメッセージを送信するだけです。  
  
-   **FaultDocumentNamespace です。** このプロパティは、既定値は**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**です。  
  
## <a name="the-fault-processor-pipeline-transform-component"></a>フォールト Processor パイプライン コンポーネントを変換します。  
 ESB フォールト プロセッサ パイプラインは、BizTalk SQL アダプター (ExceptionSql.xsd) のスキーマに一致する形式にエンコードされた ESB フォールト メッセージを変換する BizTalk マップを実行するのに、ESB 変換パイプライン コンポーネントを使用します。 コンポーネントは、変換後のメッセージを SQL アダプター、ESB フォールト メッセージ データベースに挿入、ESB 管理ポータルに渡します。  
  
 ESB の変換のパイプライン コンポーネントは、実行時動作を変更する変更可能な 3 つのデザイン時プロパティを公開します。  
  
-   **有効になります。** このプロパティは、有効またはコンポーネントを無効にします。  
  
-   **検証します。** このプロパティは、メッセージが検証に使用する必要があるかどうかを指定します。  
  
-   **MapName です。** このプロパティには、記憶域、管理ポータルの ESB データベースのメッセージを変換するために実行する必要があります、マップの名前が含まれています。 既定値を次に示します。  
  
    ```  
    Microsoft.Practices.ESB.ExceptionHandling.Maps.FaultMessage_to_ExceptionSql,  
    Microsoft.Practices.ESB.ExceptionHandling.Maps,  
    Version=2.0.0.0,  
    Culture=neutral,  
    PublicKeyToken=c2c8b2b87f54180a  
    ```  
  
 すべてのパイプライン コンポーネントにより、実行が完了、BizTalk SQL Server データベース アダプターは、ESB 管理ポータルのデータベースに、エラー メッセージを挿入します。