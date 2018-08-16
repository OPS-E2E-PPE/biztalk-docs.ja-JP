---
title: ESB エラー プロセッサ パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a57752b1-8bca-4534-9e5b-7ce721a9490a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eb33c091c064c8a94939a8b9f2f0ee37f75881b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015430"
---
# <a name="the-esb-fault-processor-pipeline"></a>ESB エラー プロセッサ パイプライン
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]という名前のすべての送信ポートをインストールします。例外、ESBFaultProcessor を使用する送信パイプラインです。 図 1 は、すべてのプロパティを示します。例外は、ポートを送信します。  
  
 ![すべての例外の送信ポート](../esb-toolkit/media/ch4-allexceptionssendport.gif "Ch4 AllExceptionsSendPort")  
  
 **図 1**  
  
 **すべての構成。例外の送信ポート、ESBFaultProcessor パイプラインの使用を含む**  
  
 ESBFaultProcessor パイプラインには、次のパイプライン コンポーネントが含まれています: ESB 例外エンコーダー、ESB ビジネス アクティビティ監視 (BAM) 追跡ツール、および ESB を変換します。  
  
 すべて。例外は、ポートをサブスクライブするすべての ESB エラー メッセージと BizTalk 失敗のメッセージのルーティング メカニズムによって生成されたすべてのメッセージを送信します。 図 2 は、すべてのプロパティの設定、フィルターを示します。例外は、ポートを送信します。  
  
 ![送信ポートのフィルター処理](../esb-toolkit/media/ch4-filtersendport.gif "Ch4 FilterSendPort")  
  
 **図 2**  
  
 **すべてのフィルター プロパティ。例外の送信ポートは、ポートのサブスクリプションを定義します。**  
  
## <a name="the-fault-processor-pipeline-exception-encoder-component"></a>エラー プロセッサ パイプライン例外エンコーダー コンポーネント  
 ESB 例外エンコーダー パイプライン コンポーネントは、ESB 失敗オーケストレーションの例外ルーティング メカニズムと ESB 例外レポートに準拠する標準のメッセージに BizTalk 失敗のメッセージのルーティング メカニズムで生成されたエラー メッセージを正規化します。スキーマです。  
  
 オーケストレーションの例外ルーティングの失敗の例外では、コンポーネントが拡充し、すべてのエラー メッセージのプロパティ、XLANG メッセージ、コンテキストのプロパティをシリアル化と**System.Exception**情報を XML メッセージにします。  
  
 メッセージをルーティングできませんでした例外では、コンポーネントは、アプリケーション名と、その他のアンビエント プロパティを追加することで、データを強化し、スキーマ名前空間、送信 XML メッセージの内容に適用します。  
  
 必要に応じて、ESB 例外エンコーダー パイプライン コンポーネントは、Microsoft の InfoPath 処理命令、送信メッセージにも適用できます。 InfoPath の命令を変更するには、デザイン ビューで、パイプライン コンポーネントのプロパティを設定します。 次の 3 つのデザイン時プロパティでは、ESB 例外エンコーダー パイプライン コンポーネントの実行時の動作に影響します。  
  
- **EscapeCDATA します。** このプロパティは、コンポーネントが、エスケープがかどうかを決定します**CDATA**のセクションでは、InfoPath が正しく表示にできるようにメッセージが永続化します。  
  
- **FaultDocumentNamespace します。** このプロパティの既定値を持つ **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**します。 永続化されたメッセージのカスタムの送信の名前空間を使用するように変更できます。  
  
- **ProcessingInstruction します。** このプロパティは、フォールトの ESB 例外レポート スキーマに準拠している任意の InfoPath 処理命令を含めることができます。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の処理命令に準拠している InfoPath テンプレートが含まれています。  
  
  ```  
  <?mso-infoPathSolution solutionVersion="1.0.0.346" productVersion="11.0.6565"  
  PIVersion="1.0.0.0"   
  href=file:///\\localhost\publish\Microsoft.Practices.ESB.ExceptionHandling.InfoPath.Reporting.xsn  
  name="urn:schemas-microsoft-com:office:infopath:  
  Microsoft-Practices-ESB-ExceptionHandling-InfoPath-Reporting:  
  http---schemas-microsoft-biztalk-practices-esb-com-exceptionhandling"  
  language="en-us" ?><?mso-application progid="InfoPath.Document"?>  
  ```  
  
## <a name="the-fault-processor-pipeline-bam-tracker-component"></a>エラー プロセッサ パイプライン BAM の追跡ツール コンポーネント  
 ESB BAM の追跡ツールのパイプライン コンポーネントは、ESB 例外エンコーダー コンポーネントからメッセージを受信し、ESB 例外管理フレームワークのインストール中に作成された BAM プライマリ インポート テーブルを選択したエラーのデータを書き込みます。  
  
 ESB BAM の追跡ツール コンポーネントを使用して、 **GetEventStream** BAM プライマリ インポート データベースにアクティビティのレコードと、次のフィールドを追加するパイプラインのコンテキストのメソッド。  
  
- **アプリケーション**  
  
- **[説明]**  
  
- **FaultSeverity**  
  
- **サービス名**  
  
- **ErrorType**  
  
- **FaultCode**  
  
- **MachineName**  
  
- **メッセージ Id**  
  
- **DateTime**  
  
- **FaultDescription**  
  
- **Scope**  
  
- **FailureCategory**  
  
- **FaultGenerator**  
  
- **ServiceInstanceID**  
  
  ESB BAM の追跡ツール コンポーネントがメッセージ id を使用して (、 **MessageID**プロパティ) として BAM アクティビティの id ESB エラー メッセージの値。 ESB BAM の追跡ツールのコンポーネントは、実行時の動作を変更するために設定できます 2 つのデザイン時プロパティを公開します。  
  
- **有効。** このプロパティは、コンポーネントは、メッセージを処理し、BAM データベースに書き込むかどうかを決定します。 設定すると**False**コンポーネントは、パイプラインの次のコンポーネントにメッセージを送信するだけです。  
  
- **FaultDocumentNamespace します。** このプロパティの既定値を持つ **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**します。  
  
## <a name="the-fault-processor-pipeline-transform-component"></a>エラー プロセッサ パイプライン コンポーネントを変換します。  
 ESB エラー プロセッサ パイプラインでは、ESB の変換のパイプライン コンポーネントを使用して、BizTalk SQL アダプター (ExceptionSql.xsd) のスキーマに一致する形式でエンコードされた ESB エラー メッセージに変換する BizTalk マップを実行します。 コンポーネントは、ESB 管理ポータルのデータベースに、ESB エラー メッセージを挿入する SQL アダプターにし、変換後のメッセージを渡します。  
  
 ESB の変換のパイプライン コンポーネントは、実行時の動作を変更するのには変更可能な 3 つのデザイン時プロパティを公開します。  
  
- **有効。** このプロパティは、有効またはコンポーネントを無効にします。  
  
- **検証します。** このプロパティは、メッセージを検証する必要かどうかを指定します。  
  
- **MapName します。** このプロパティには、ESB 管理ポータルのデータベース内のストレージは、メッセージを変換するために実行する必要がありますマップの名前が含まれています。 既定値は、次のとおりです。  
  
  ```  
  Microsoft.Practices.ESB.ExceptionHandling.Maps.FaultMessage_to_ExceptionSql,  
  Microsoft.Practices.ESB.ExceptionHandling.Maps,  
  Version=2.0.0.0,  
  Culture=neutral,  
  PublicKeyToken=c2c8b2b87f54180a  
  ```  
  
  すべてのパイプライン コンポーネントの実行が完了した後、BizTalk SQL Server データベース アダプターは、ESB 管理ポータルのデータベースに、エラー メッセージを挿入します。