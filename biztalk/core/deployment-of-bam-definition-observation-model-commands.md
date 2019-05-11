---
title: BAM 定義 (監視モデル) コマンドの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506b563136fec86fdde9aebab31ad9bb4435736b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351740"
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a>BAM 定義 (監視モデル) コマンドの配置
BAM 管理ユーティリティの展開コマンドを使用すると、適用、変更、および定義を削除できます。  
  
-   すべてを展開します。BAM 定義をデプロイします。  
  
-   すべての更新プログラム。BAM 定義を更新します。  
  
-   すべて削除します。BAM 定義を削除します。  
  
-   更新プログラム-livedataworkbook:ライブ データ ブック内のデータベース接続情報を更新します。  
  
-   再生成 livedataworkbook:サーバーでライブ データ ブックを再生成します。  
  
> [!NOTE]
>  含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="deploy-all-command"></a>deploy-all コマンド  
 **使用方法**  
  
 **bm.exe deploy-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|DefinitionFile:\<def ファイル\>|パスとデプロイには、定義を含むファイルの名前。|  
|サーバー:\<サーバー\>|省略可能:定義を展開する先のサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:定義を配置するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定した BAM 定義 XML ファイルから、指定されたサーバーとデータベースへのすべての成果物をデプロイします。 ファイルは、BAM 定義 XML または BAM Excel ブックを含むテキスト ファイルであることができます。 定義ファイルには、新しい成果物のみを含める必要があります。 ファイルに既にデプロイされている成果物が含まれている場合、デプロイは失敗し、エラーを報告します。  
  
 **BAM 定義の展開に関する考慮事項**  
  
 警告のサブスクリプションを展開する場合は、domain \user 形式で、サブスクライバーのユーザー Id を指定してください。  
  
 コンピューターに、分散トランザクション コーディネーター (DTC) サービスを実行する必要があります、**展開すべて**コマンドを発行します。  
  
 定義を展開するときに、BAM 管理ユーティリティにより、ディメンション レベルは 14 がリアルタイム集計 (RTA) ビューでのみサポートします。 追加レベルを展開するには、配置に失敗しましたエラーが返されます。  
  
 別の言語設定を使用し、1 つの言語を使用するサーバーに、ソリューションを配置する複数のビューを定義する場合、ビューは展開されません。 このシナリオは、BAM 定義の一部として OLAP を必要とするスケジュール済みの集計の必要がないケースでのみサポートされます。  
  
 BAM 管理ユーティリティは、49 展開されたアクティビティ ビューに BAM 警告を有効にするように制限されます。 アクティビティ ビューの数は合計として計算されますの総和は親アクティビティの数を掛けた値します。  たとえば、2 つのアクティビティに基づいているビューを展開する場合に、2 つのアクティビティ ビューを取得します。  うちの 1 つは、2 つのアクティビティおよびその他の 1 つのアクティビティに基づくにまたがる、2 つのビューを展開する場合は、3 つのアクティビティ ビューが。  
  
 複数のピボット テーブルが BAM 定義の BAM 管理ユーティリティのブロックの展開では、同じ RTA およびキューブ名の組み合わせで定義されているを報告します。 Bm.exe が配置を終了し、次のエラーが返されます。  
  
 ビューを展開しています.ERROR:BAM の展開に失敗しました。  
  
 1 つのピボット テーブル ビューは、特定の RTA とキューブを定義できます。  
  
 名の次の一覧は、予約されていますし、定義の展開に失敗すると。  
  
-   RecordID  
  
-   ActivityID  
  
-   可視  
  
-   完了  
  
-   LastModified  
  
> [!NOTE]
>  Bm.exe には、展開中にエラーが発生するは、展開が終了し、ビューとアクティビティへの変更はロールバックされます。 OLAP はトランザクション配置をサポートするいないとしているために、OLAP キューブへの変更はロールバックされません。  
  
> [!NOTE]
>  1 つのロケール設定を使用してコンピューター上に作成された BAM 定義は、別のロケール設定で構成されているコンピューターに展開できません。 たとえば、EN のロケール設定で構成されているコンピューターに Microsoft Excel の英語バージョンを使用して生成された BAM 定義は、日本語、日本のロケール設定を使用して構成されているコンピューターに展開できません。  
  
 **使用例**  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a>update-all コマンド  
 **使用方法**  
  
 **bm.exe update-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|DefinitionFile:\<def ファイル\>|パスと、更新プログラムを実行する定義が格納されたファイルの名前。|  
|サーバー:\<サーバー\>|省略可能:定義の更新を展開するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:定義の更新を展開するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 BAM 定義 XML に基づいて特定のアイテムを更新します。 ファイルは、BAM 定義 XML または BAM Excel ブックを含むテキスト ファイルであることができます。 更新プログラムでは、現在の定義ファイルに記述されていないアイテムは削除されません。 活動に新しいチェックポイントを追加することができますが、展開済みのアクティビティからチェックポイントを削除することはできません。 更新プログラムはチェックポイントの名前も、チェックポイントのプロパティを変更します。  
  
 アクティビティを展開した後は、アクティビティに対して実行できる操作が制限されます。 特に、アクティビティから項目を削除するには、管理者に依頼して BAM のアクティビティとビュー セット全体を展開解除し、再展開してもらう必要があります。 このとき、管理者がデータのバックアップと復元を行わないと、データが失われたり、表示できなくなったりすることがあります。  
  
> [!NOTE]
>  このコマンドを使用して、既存のビューに新しいアクティビティを追加することはできません。 アクティビティにビューを追加するには、新しいアクティビティを含む新しいビューを作成する必要があります。 できますが、元のビューを展開解除し、OLAP データの履歴が失われることに注意してください。  
  
 **使用例**  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a>remove-all コマンド  
 **使用方法**  
  
 **bm.exe remove-all DefinitionFile:\<def file\> [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|DefinitionFile:\<def ファイル\>|パスと、削除する定義を含むファイルの名前。|  
|サーバー:\<サーバー\>|省略可能:定義の削除元となるサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:定義の削除元となるデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 BAM 定義 XML ファイルで指定されたすべての成果物を削除します。 ファイルは、BAM 定義 XML または BAM Excel ブックを含むテキスト ファイルであることができます。 各成果物の定義では、展開に使用された元の定義を正確に一致する必要があります。  
  
 **使用例**  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a>update-livedataworkbook コマンド  
 **使用方法**  
  
 **bm.exe update-livedataworkbook -Name:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|名前:\<livedata ブック\>|更新する既存のライブ ブックの名前。|  
|サーバー:\<サーバー\>|省略可能:ブックが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ブックが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定された BAM ライブ データ ブックで BAM プライマリ インポート データベースの接続情報を更新します。  
  
> [!NOTE]
>  新しい接続文字列を構成するときに、サービスが、変更を認識していることを確認する TDDS サービスを再起動する必要があります。 TDDS サービスの詳細については、次を参照してください。 [BAM イベント バス サービス ストアド プロシージャ](../core/bam-event-bus-service-stored-procedures.md)します。  
  
 **使用例**  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a>regenerate-livedataworkbook コマンド  
 **使用方法**  
  
 **bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|WorkbookName:\<livedata ブック ファイル名\>|更新するブックの名前。|  
|サーバー:\<サーバー\>|省略可能:ブックが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ブックが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 BAM ライブ データ ブックを生成しますが、ブックを配置しません。  
  
 使用例  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)