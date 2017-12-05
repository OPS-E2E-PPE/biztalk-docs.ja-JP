---
title: "BAM 定義 (監視モデル) コマンドの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dba1e1a4f54b3b33ebca8297cfe9beef7c4f868
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a>BAM 定義 (監視モデル) の展開コマンド
BAM 管理ユーティリティの展開コマンドを使用すると、定義を適用、変更、および削除することができます。  
  
-   展開すべて: BAM 定義を展開します。  
  
-   すべての更新: BAM 定義を更新します。  
  
-   すべてを削除します。 BAM 定義を削除します。  
  
-   更新 livedataworkbook: ライブ データ ブック内のデータベース接続情報を更新します。  
  
-   regenerate livedataworkbook: サーバーでライブ データ ブックを再生成します。  
  
> [!NOTE]
>  含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="deploy-all-command"></a>deploy-all コマンド  
 **使用方法**  
  
 **bm.exe 展開すべて-definitionfile:\<def ファイル\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def ファイル\>|展開する定義が格納されたファイルのパスおよび名前です。|  
|サーバー:\<サーバー\>|省略可能: 定義を展開するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 定義を配置するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定された BAM 定義 XML ファイルのすべてのアイテムを、指定されたサーバーおよびデータベースに展開します。 BAM 定義 XML が含まれたテキスト ファイルか、BAM Excel ブックのいずれかのファイルを使用できます。 定義ファイルに、既存のアイテムを含めることはできません。 既に展開済みのアイテムが格納されていた場合、展開は失敗し、エラーが報告されます。  
  
 **BAM 定義の展開に関する考慮事項**  
  
 警告サブスクリプションを展開する場合は、サブスクライバーのユーザー ID を domain\user 形式で指定する必要があります。  
  
 コンピューターに分散トランザクション コーディネーター (DTC) サービスが実行されている必要があります、**展開すべて**コマンドを発行します。  
  
 BAM 管理ユーティリティで定義を展開するとき、RTA (リアルタイム集計) ビューでサポートされるディメンション レベルは 14 レベルまでです。 それ以上のレベルを展開すると、"配置に失敗しました" というエラーが返されます。  
  
 言語設定がそれぞれ異なる複数のビューを定義し、単一言語のサーバーに対してソリューションを展開した場合、これらのビューは展開されません。 このシナリオがサポートされるのは、BAM 定義に、OLAP を必要とするスケジュール済みの集計が含まれない場合だけです。  
  
 BAM 管理ユーティリティでは、BAM 警告が有効な場合、展開できるアクティビティ ビューが 49 個に制限されます。 アクティビティ ビューの数は、各ビューに関連付けられた親アクティビティ数の総和として計算されます。  たとえば、2 つのアクティビティに基づくビューを 1 つ展開した場合、アクティビティ ビューは 2 つです。  また、一方は 2 つのアクティビティに、もう一方は単一のアクティビティに基づく 2 つのビューを展開した場合、アクティビティ ビューの数は 3 つということになります。  
  
 BAM 管理ユーティリティでは、同じ RTA およびキューブ名の組み合わせに対して複数の PivotTable レポートを定義し、それを BAM 定義に割り当てて展開することはできません。 Bm.exe によって展開作業が強制終了され、次のようなエラーが返されます。  
  
 ビューを展開しています...エラー: BAM 展開に失敗しました。  
  
 特定の RTA とキューブに対して定義できる PivotTable ビューは 1 つだけです。  
  
 次に示した名前は予約されています。使用すると定義の展開時にエラーが発生します。  
  
-   RecordID  
  
-   ActivityID  
  
-   可視  
  
-   IsComplete  
  
-   LastModified  
  
> [!NOTE]
>  展開中に bm.exe でエラーが発生した場合、展開は強制終了され、ビューやアクティビティに対する変更はロールバックされます。 ただし、OLAP はトランザクション配置に対応していないため、OLAP キューブに対する変更はロールバックされません。  
  
> [!NOTE]
>  BAM 定義を作成するコンピューターと、その展開先のコンピューターは、ロケール設定が一致している必要があります。 たとえば、ロケール設定が EN のコンピューターで、英語版の Microsoft Excel を使って作成された BAM 定義を、ロケール設定が JA (日本語) のコンピューターに展開することはできません。  
  
 **使用例**  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a>update-all コマンド  
 **使用方法**  
  
 **すべての bm.exe 更新-definitionfile:\<def ファイル\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def ファイル\>|更新に使用する定義が格納されたファイルのパスおよび名前です。|  
|サーバー:\<サーバー\>|省略可能: 定義の更新を展開するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 定義の更新を展開するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 BAM 定義 XML に基づいて特定のアイテムを更新します。 BAM 定義 XML が含まれたテキスト ファイルか、BAM Excel ブックのいずれかのファイルを使用できます。 更新時、現在の定義ファイルに記述されていないアイテムは削除されません。 アクティビティに新しいチェックポイントを追加することはできますが、展開済みのアクティビティからチェックポイントを削除することはできません。 更新中にチェックポイントの名前を変更したり、チェックポイントのプロパティを変更したりすることはできません。  
  
 アクティビティを展開した後は、アクティビティに対して実行できる操作が制限されます。 特に、アクティビティから項目を削除するには、管理者に依頼して BAM のアクティビティとビュー セット全体を展開解除し、再展開してもらう必要があります。 このとき、管理者がデータのバックアップと復元を行わないと、データが失われたり、表示できなくなったりすることがあります。  
  
> [!NOTE]
>  このコマンドを使って、既存のビューに新しいアクティビティを追加することはできません。 ビューをアクティビティに追加するには、新しいアクティビティを含んだビューを新規作成する必要があります。 古いビューはその後で展開解除できますが、その場合、OLAP のデータ履歴は失われます。  
  
 **使用例**  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a>remove-all コマンド  
 **使用方法**  
  
 **すべての bm.exe 削除 DefinitionFile:\<def ファイル\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def ファイル\>|削除する定義が格納されたファイルのパスおよび名前です。|  
|サーバー:\<サーバー\>|省略可能: 定義の削除元となるサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 定義の削除元となるデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 BAM 定義 XML ファイルに指定されている、すべてのアイテムを削除します。 BAM 定義 XML が含まれたテキスト ファイルか、BAM Excel ブックのいずれかのファイルを使用できます。 各アイテムの定義は、元の (展開時の) 定義と完全に一致している必要があります。  
  
 **使用例**  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a>update-livedataworkbook コマンド  
 **使用方法**  
  
 **bm.exe 更新 livedataworkbook-名前:\<livedata ブックのファイル名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|[名前]:\<livedata ブック\>|更新する既存のライブ ブックの名前。|  
|サーバー:\<サーバー\>|省略可能: ブックが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ブックが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 指定された BAM ライブ データ ブックを対象に、BAM プライマリ インポート データベースの接続情報を更新します。  
  
> [!NOTE]
>  新しい接続文字列を構成するときには TDDS サービスを再起動して、変更がサービスから確実に認識されるようにする必要があります。 TDDS サービスの詳細については、次を参照してください。 [BAM イベント バス サービス Stored Procedures](../core/bam-event-bus-service-stored-procedures.md)です。  
  
 **使用例**  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a>regenerate-livedataworkbook コマンド  
 **使用方法**  
  
 **bm.exe を再生成 livedataworkbook WorkbookName:\<livedata ブックのファイル名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|WorkbookName:\<livedata ブックのファイル名\>|更新するブックの名前です。|  
|サーバー:\<サーバー\>|省略可能: ブックが存在するサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: ブックが存在するデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 BAM ライブ データ ブックを生成します。ただし、ブックは展開されません。  
  
 使用例  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)