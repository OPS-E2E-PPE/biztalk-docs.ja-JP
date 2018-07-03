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
ms.openlocfilehash: 01c5dfe58f7b31bb5ef461249765d527f78d9264
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009059"
---
# <a name="common-errors"></a>一般的なエラー
ここでは、BizTalk マッパーを使用してマップを作成しているときによく発生するエラー メッセージを示します。  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a>日付の解析時にエラー イベント ID 324 が発生する  
  
### <a name="problem"></a>問題  
 データベースを使用すると**値抽出**日付フィールド、ドキュメントを抽出するマップの functoid には送信ドキュメント定義に対して検証が失敗します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] イベント ログに次のような検証エラーをログする可能性があります。  
  
 BizTalk Server のイベント ソース:  
  
 イベント カテゴリ: ドキュメントの処理  
  
 イベント ID: 324  
  
 説明:  
  
 BizTalk Server でエラーが発生しました。  
  
 詳細:  
  
 -----------------------------\-  
  
 XML ドキュメントには次の理由で検証が失敗した: '10/12/1995 の解析中にエラー' date データ型として。  
  
 保留キュー ID:"{A1127909-CA36-4359-B672-7CBA8B60BDAF}"  
  
### <a name="cause"></a>原因  
 (データ ソースから返された) 日付形式が、XML で規定されている ISO 8601 形式ではありません。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかの操作を行います。  
  
- 送信ドキュメント定義を編集して、date データ型ではなく string データ型を使用します。  
  
- カスタムを作成する[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**スクリプト**データベースの出力を変換する functoid**値抽出**functoid を ISO 8601 形式にします。  
  
  詳細については、サポート技術情報の記事を参照してください[278737](http://support.microsoft.com/kb/278737/en-us)します。  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a>マップのコンパイル時に内部コンパイラ エラー (アドレス 53624FD6 の 0xc0000005) が発生する  
  
### <a name="problem"></a>問題  
 大きなスキーマ、マップ、またはオーケストレーションで構成された単一の BizTalk プロジェクトをコンパイルした場合、次のようなエラーが発生する可能性があります。  
  
 内部コンパイラ エラー (アドレス 53624fd6 の 0xc0000005): 可能性の高い原因は 'CODEGEN'。  
  
### <a name="cause"></a>原因  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラには、単一のプロジェクトにおけるすべての文字列の合計サイズについて 16 MB の制限があります。 BizTalk プロジェクトをコンパイルしている間、コンパイラはアセンブリ作成のスキーマ、マップ、およびオーケストレーションをシリアル化し、これによってすべての文字列の合計サイズが増加し、制限を超える可能性があります。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、スキーマまたはマップを個別の BizTalk プロジェクトに分離します。  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a>BizTalk アイテムの型名についてのエラーが発生する  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトでは、ファイル名にマップを作成**System.btm**または**Microsoft.btm**します。 プロジェクトをビルドすると、BizTalk マッパーが次のようなエラーを生成します。  
  
-   "型名 'SerializableAttribute' が存在しません..."  
  
-   "型名 'NonSerializableAttribute' が存在しません..."  
  
-   "型名 'SerializableAttributeAttribute' が存在しません..."  
  
-   "型名 'XLANs' が存在しません..."  
  
### <a name="cause"></a>原因  
 **型名**で、**プロパティ**グリッド必要はありません予約 .NET 名前空間など**システム**、 **Microsoft**など。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかの対処方法を使用できます。  
  
-   マップの名前を、.NET の予約語ではない文字列に変更します。 既定では、BizTalk プロジェクト システムを作成、**型名**それぞれのアイテムの名前から。  
  
     例:: 名前の新しいマップを作成する**Map1.btm**設定、**型名**プロパティの値を**Map1**します。 ただし、既存の BizTalk アイテムは変更されません、**型名**します。  
  
-   BizTalk プロジェクトのアイテムのファイル名が .NET の予約された名前空間ではないことを確認してください。  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a>BizTalk アイテムのファイル名についてのエラーが発生する  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトをビルドすると、BizTalk マッパーが次のようなエラーを生成します。  
  
-   "ファイル\<filename\>が名前空間と型名のプロパティの値が重複します"。  
  
-   "名前空間\<名前\>'_' の定義が既に含まれています"。  
  
### <a name="cause"></a>原因  
 BizTalk プロジェクトでは、次のことが検査されます。  
  
-   複数のアイテムが同じファイル名を持っている。 例: **Map1.xsd**と**Map1.btm**します。  
  
-   特殊文字のみのファイル名で構成されます (**~**、 **!**、  **@** など。)。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかの対処方法を使用できます。  
  
-   ファイルの名前を変更します。 BizTalk プロジェクトのすべてのアイテムのファイル名が一意であることを確認します。  
  
-   BizTalk プロジェクトのすべてのアイテムの型名が一意であることを確認します。  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a>BizTalk マッパーを含む C# ワークフロー プロジェクトを構築すると、EnvDTE.dll のバージョンの競合に関する警告が表示されます。  
  
### <a name="problem"></a>問題  
 BizTalk マッパー アクティビティを含む C# ワークフロー プロジェクトを構築すると、EnvDTE.dll のバージョンの競合に関する次の警告が常に表示されます。  
  
 "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" と "EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" の間の競合を解決する方法がありません。 任意で "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" を選択します。  競合を解決して警告を消去するために、app.config でアセンブリ "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" をバージョン "7.0.3300.0" [] からバージョン "8.0.0.0" [C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] にマップし直してください。 C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): 警告 msb 3247: 同じ依存アセンブリの異なるバージョン間の競合が見つかりました。  
  
 WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe  
  
### <a name="cause"></a>原因  
 これは、マッパー アクティビティが参照している Microsoft.BizTalk.Mapper.OM.dll が原因で発生します。  
  
### <a name="resolution"></a>解決策  
 警告を無視してください。  
  
## <a name="see-also"></a>参照  
 [マップのトラブルシューティング](../core/troubleshooting-maps.md)