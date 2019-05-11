---
title: アクティビティ管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dc32b005d0a6492fbdce87a1149c23c5a13442e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361674"
---
# <a name="activity-management-commands"></a>アクティビティ管理コマンド
BAM 管理ユーティリティのアクティビティ管理コマンドを使用すると、展開済みのアクティビティを使用できます。  
  
-   get アクティビティ:展開済みアクティビティの一覧を取得します。  
  
-   削除アクティビティ:アクティビティを削除します。  
  
-   get activitywindow:アクティビティの期間を取得します。  
  
-   セット activitywindow:アクティビティのアクティビティ期間を設定します。  
  
-   get インデックス:インデックスの一覧を取得します。  
  
-   インデックスの作成:新しいインデックスを作成します。  
  
-   -インデックスを削除します。インデックスを削除します。  
  
-   get アーカイブ:アーカイブ済みアクティビティの動作を取得します。  
  
-   セット-アーカイブ:アーカイブ済みアクティビティの動作を設定します。  
  
> [!NOTE]
>  含めることによって任意の BAM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BAM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="get-activities-command"></a>get-activities コマンド  
 **使用方法**  
  
 **bm.exe の取得活動 [-ビュー:\<ビュー名\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|名前:\<アクティビティ名\>|削除するアクティビティの名前。|  
|サーバー:\<サーバー\>|省略可能:アクティビティの一覧の取得元のサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティの一覧の取得元のデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 コマンドを実行するコンピューターに展開されているアクティビティを一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a>remove-activity コマンド  
 **使用方法**  
  
 **bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|名前:\<アクティビティ名\>|削除するアクティビティの名前。|  
|サーバー:\<サーバー\>|省略可能:元のアクティビティを削除するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:元のアクティビティを削除するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定したアクティビティを BAM プライマリ インポート データベースから削除します。 アクティビティに依存するビューがある場合は、コマンドが失敗し、エラーを報告します。 Remove-view コマンドを使用して、依存するすべてのビューを削除し、remove-activity コマンドを再度実行します。  
  
 **使用例**  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a>get-activitywindow コマンド  
 **使用方法**  
  
 **bm.exe の get activitywindow-アクティビティ:\<アクティビティ名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|.Activity の名前。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定されたアクティビティの期間を表示します。 コマンドは、期間と期間の測定単位の長さを返します。  
  
 **使用例**  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a>set-activitywindow コマンド  
 **使用方法**  
  
 **bm.exe のセット activitywindow-アクティビティ:\<アクティビティ名\>- TimeLength:\<整数\>- TimeUnit: 月&#124;日&#124;時間&#124;分 [-サーバー:\<server\> ][-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|アクティビティの名前。|  
|TimeLength:\<整数\>|アクティビティの期間です。|  
|TimeUnit:Month&#124;日&#124;時間&#124;分|期間の単位。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定したアクティビティの期間を設定します。  
  
 **使用例**  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a>get-index コマンド  
 **使用方法**  
  
 **bm.exe の get インデックス-アクティビティ:\<アクティビティ名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|アクティビティの名前。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定したアクティビティ用に作成されたすべてのインデックスを一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a>create index コマンド  
 **使用方法**  
  
 **bm.exe インデックスの作成-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>-チェックポイント:\<チェックポイント 1\>[、\<チェックポイント 2\>...][-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|IndexName:\<インデックス名\>|新しいインデックスの名前。|  
|アクティビティ:\<アクティビティ名\>|インデックスを作成するアクティビティの名前。|  
|チェックポイント:\<チェックポイント 1\>[、\<チェックポイント 2\>...]|インデックスのチェックポイントのコンマ区切りのリスト。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定したチェックポイントを使用して、指定したアクティビティのインデックスを作成します。  
  
 **使用例**  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a>delete-index コマンド  
 **使用方法**  
  
 **bm.exe インデックスを削除-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|IndexName:\<インデックス名\>|削除するインデックスの名前。|  
|アクティビティ:\<アクティビティ名\>|インデックスが削除されるアクティビティの名前。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 指定したアクティビティから、指定した名前の指定したインデックスを削除します。  
  
 **使用例**  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a>set-archive コマンド  
 **使用方法**  
  
 **bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|動作を表示するアクティビティの名前。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 アーカイブのパッケージは orpurge アクティビティ データをアーカイブするかどうかは、指定されたアクティビティのアーカイブ パッケージの動作を取得します。  
  
 **使用例**  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a>set-archive コマンド  
 **使用方法**  
  
 **bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|アクティビティ:\<アクティビティ名\>|動作を表示するアクティビティの名前。|  
|ShouldArchive:True|True に設定すると、アクティビティに移動されますアーカイブ DB します。 場合は、アクティビティを False に設定は消去されます。|  
|サーバー:\<サーバー\>|省略可能:アクティビティが存在するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:アクティビティが存在するデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 アクティビティ データがアーカイブ DB に移動されるように指定されたアクティビティのアーカイブ パッケージの動作を設定します。 既定では、この動作は、展開されている新しいアクティビティに対して設定されます。  
  
 **使用例**  
  
 BAM アクティビティ データを削除するには、次の手順を実行します。  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 BAM アクティビティ データを BAMArchive データベースに移動するには次の手順を実行します。  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)