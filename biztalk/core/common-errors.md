---
title: 一般的なエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57eb84b31082f6175f4a68b081130216be06b63e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528208"
---
# <a name="common-errors"></a>一般的なエラー
このトピックでは、一般的なエラー メッセージが BizTalk マッパーを使用してマップを作成するときに発生する可能性を示します。  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a>日付を解析するときにイベント ID 324 がエラーを受信します。  
  
### <a name="problem"></a>問題  
 データベースを使用すると**値抽出**日付フィールド、ドキュメントを抽出するマップの functoid には送信ドキュメント定義に対して検証が失敗します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] イベント ログに次のような検証エラーをログする可能性があります。  
  
 イベント ソース:BizTalk Server  
  
 イベント カテゴリ:ドキュメントの処理  
  
 イベント ID:324  
  
 説明:  
  
 BizTalk Server でエラーが発生しました。  
  
 詳細:  
  
 -----------------------------\-  
  
 XML ドキュメントには、次の理由で検証が失敗しました。'10/12/1995 の解析中にエラー' date データ型として。  
  
 保留キュー ID:"{A1127909-CA36-4359-B672-7CBA8B60BDAF}"  
  
### <a name="cause"></a>原因  
 (データ ソースから返された) 日付形式は XML で必要な形式は、ISO 8601 形式ではありません。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかを実行します。  
  
- Date データ型ではなく文字列データ型を使用して、送信ドキュメント定義を編集します。  
  
- カスタムを作成する[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**スクリプト**データベースの出力を変換する functoid**値抽出**functoid を ISO 8601 形式にします。  
  
  詳細については、サポート技術情報の記事を参照してください[278737](http://support.microsoft.com/kb/278737/en-us)します。  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a>内部コンパイラ エラー (アドレス 53624fd6 の 0xc0000005) をいつ受信する、マップのコンパイル  
  
### <a name="problem"></a>問題  
 大きなスキーマ、マップ、またはオーケストレーションで構成される 1 つの BizTalk プロジェクトをコンパイルするときに、コンパイラは、次のようなエラーを生成可能性があります。  
  
 内部コンパイラ エラー (アドレス 53624fd6 の 0xc0000005): 可能性の高い原因は 'CODEGEN'。  
  
### <a name="cause"></a>原因  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラには、単一のプロジェクトにおけるすべての文字列の合計サイズについて 16 MB の制限があります。 BizTalk プロジェクトをコンパイルしている間、コンパイラはアセンブリ作成のスキーマ、マップ、およびオーケストレーションをシリアル化し、これによってすべての文字列の合計サイズが増加し、制限を超える可能性があります。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、別の BizTalk プロジェクトにスキーマまたはマップを分離できます。  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a>BizTalk アイテムの型名に関するエラーが発生します。  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトでは、ファイル名にマップを作成**System.btm**または**Microsoft.btm**します。 プロジェクトをビルドすると、BizTalk マッパーには、次のいずれかのようなエラーが生成されます。  
  
-   「型名 'SerializableAttribute' が存在しません...」  
  
-   「型名 'NonSerializableAttribute' が存在しません...」  
  
-   「型名 'SerializableAttributeAttribute' が存在しません...」  
  
-   「型名 'XLANs' が存在しません...」  
  
### <a name="cause"></a>原因  
 **型名**で、**プロパティ**グリッド必要はありません予約 .NET 名前空間など**システム**、 **Microsoft**など。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、これらの回避策のいずれかに従うことができます。  
  
-   .NET の予約語ではない任意の文字列にマップの名前を変更します。 既定では、BizTalk プロジェクト システムを作成、**型名**それぞれのアイテムの名前から。  
  
     例。名前の新しいマップを作成する**Map1.btm**設定、**型名**プロパティの値を**Map1**します。 ただし、既存の BizTalk アイテムは変更されません、**型名**します。  
  
-   BizTalk プロジェクトの成果物のいずれかのファイル名は、.NET の予約された名前空間を確認します。  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a>BizTalk アイテムのファイル名に関するエラーが発生します。  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトをビルドすると、BizTalk マッパーには、次のいずれかのようなエラーが生成されます。  
  
-   "ファイル\<filename\>が名前空間と型名のプロパティの値が重複します"。  
  
-   "名前空間\<名前\>'_' の定義が既に含まれています"。  
  
### <a name="cause"></a>原因  
 BizTalk プロジェクトには、次を確認します。  
  
-   複数のアイテムでは、同じファイル名があります。 例: **Map1.xsd**と**Map1.btm**します。  
  
-   特殊文字のみのファイル名で構成されます (**~**、 **!**、  **@** など。)。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、これらの回避策のいずれかに従うことができます。  
  
-   ファイルの名前を変更します。 BizTalk プロジェクト内のすべての成果物のファイル名が一意で確認します。  
  
-   BizTalk プロジェクト内のすべてのアーティファクトが一意の型名を確認してください。  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a>BizTalk マッパーで c# ワークフロー プロジェクトを構築するとすると、EnvDTE.dll のバージョンの競合に関する警告が表示します。  
  
### <a name="problem"></a>問題  
 BizTalk マッパーで c# ワークフロー プロジェクトを構築するアクティビティは常に、EnvDTE.dll のバージョンの競合に関する次の警告を表示します。  
  
 間の競合を解決する方法はありません"EnvDTE, バージョン 8.0.0.0、カルチャを = = neutral, PublicKeyToken = b03f5f7f11d50a3a"と"EnvDTE, バージョン 7.0.3300.0、カルチャを = = neutral, PublicKeyToken = b03f5f7f11d50a3a"。 選択する"EnvDTE, バージョン 8.0.0.0、カルチャを = = neutral, PublicKeyToken = b03f5f7f11d50a3a"任意にします。  App.config のアセンブリの再割り当てを検討してください"EnvDTE, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a"バージョン「7.0.3300.0」からバージョン「8.0.0.0」[C:\Program Files (x86) \Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] から競合を解決し、警告を取り除きます。 C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): warning MSB3247:同じ依存アセンブリの異なるバージョン間の競合が見つかりました。  
  
 WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe  
  
### <a name="cause"></a>原因  
 これは、マッパー アクティビティを参照している Microsoft.BizTalk.Mapper.OM.dll が原因で発生します。  
  
### <a name="resolution"></a>解決策  
 警告を無視します。  
  
## <a name="see-also"></a>参照  
 [マップのトラブルシューティング](../core/troubleshooting-maps.md)